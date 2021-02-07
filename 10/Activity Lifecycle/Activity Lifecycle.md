## Activity Lifecycle



### 1. Android Process Management

-   Each running Android application is a separate process 
-   If the system identifies that resources on the device are reaching capacity it will take steps to terminate processes to free up memory
-   When making a determination as to which process to terminate, the system considers both the priority and state of all currently running processes, combining these factors to create what is referred to by Google as an importance hierarchy
-   Processes are then terminated starting with the lowest priority and working up the hierarchy until sufficient resources have been liberated for the system to function

Img_01

Within an Android system, the current state of a process is defined by the highest-ranking active component within the application that it hosts. A process can be in one of the following five states at any given time:

**Foreground Process:** these processes are assigned the highest level of priority. At any one time, there are unlikely to be more than one or two foreground processes active and these are usually the last to be terminated by the system. A foreground process must meet one or more of the following criteria:

-   Hosts an activity with which the user is currently interacting

-   Hosts a Service connected to the activity with which the user is interacting

-   Hosts a Service that has indicated, via a call to *startForeground()*, that termination would be disruptive to the user experience.

-   Hosts a Service executing either its *onCreate()*, *onResume()*or *onStart() *callbacks

-   Hosts a Broadcast Receiver that is currently executing its *onReceive()* method

**Visible Process**: a process containing an activity that is visible to the user but is not the activity with which the user is interacting. This is typically the case when an activity in the process is visible to the user, but another activity, such as a partial screen or dialog, is in the foreground. A process is also eligible for visible status if it hosts a Service that is, itself, bound to a visible or foreground activity.

**Service Process**: Processes that contain a Service that has already been started and is currently executing.

**Background Process:** a process that contains one or more activities that are not currently visible to the user, and does not host a Service that qualifies for Service Process status. Processes that fall into this category are at high risk of termination when additional memory needs to be freed for higher priority processes. Android maintains a dynamic list of background processes, terminating processes in chronological order such that processes that were the least recently in the foreground are killed first.

**Empty Process:** Empty processes no longer contain any active applications and are held in memory ready to serve as hosts for newly launched applications. This is somewhat analogous to keeping the doors open and the engine running on a bus in anticipation of passengers arriving. Such processes are, obviously, considered the lowest priority and are the first to be killed to free up resources.



### 2. Activity Lifecycle

#### 2.1 Activity Stack

Img_02



The state of an Android process is determined largely by the status of the activities and components that make up the App that it hosts. These activities also transition through different states during the execution lifetime of an App. The current state of an activity is determined partly by its position in something called the Activity Stack.

-   For each application running on an Android device, the runtime system maintains an Activity Stack:

-   When an application is launched, the first of the application’s activities to be started is placed onto the stack

-   When a second activity is started, it is placed on the top of the stack and the previous activity is pushed down. The activity at the top of the stack is referred to as the active (or running) activity

-   When the active activity exits, it is popped off the stack by the runtime and the activity located immediately beneath it in the stack becomes the current active activity

-   The activity at the top of the stack might simply exit because the task for which it is responsible has been completed

-   Alternatively, the user may have selected a “Back” button on the screen to return to the previous activity, causing the current activity to be popped off the stack by the runtime system and therefore destroyed

-   The Activity Stack is referred to in programming terminology as a Last-In-First



#### 2.2 **Activity States**

An activity can be in one of a number of different states during the course of its execution within an application:

-   **Active / Running** –The activity is at the top of the Activity Stack, is the foreground task visible on the device screen, has focus and is currently interacting with the user. This is the least likely activity to be terminated in the event of a resource shortage.

-   **Paused**–The activity is visible to the user but does not currently have focus (typically because this activity is partially obscured by the current active activity). Paused activities are held in memory, remain attached to the window manager, retain all state information and can quickly be restored to active status when moved to the top of the Activity Stack.

-   **Stopped**–The activity is currently not visible to the user (in other words it is totally obscured on the device display by other activities). As with paused activities, it retains all state and member information, but is at higher risk of termination in low memory situations.

-   **Killed** –The activity has been terminated by the runtime system in order to free up memory and is no longer present on the Activity Stack. Such activities must be restarted if required by the application.



#### **2.3 Activity Lifecycle Methods**

Activity class contain a number of lifecycle methods which act as event handlers when the state of an instance changes. The primary methods supported by the Android Activity and Fragment class are as follows:

-   **onCreate(Bundle savedInstanceState)** –Called when the activity is first created and the ideal location for most initialization tasks to be performed. The method is passed an argument in the form of a *Bundle* object that may contain dynamic state information (typically relating to the state of the user interface) from a prior invocation of the activity.

-   **onRestart()** –Called when the activity is about to restart after having previously been stopped by the runtime system.
-   **onStart()** –Called immediately after the call to the *onCreate()* or *onRestart()* methods, this method indicates to the activity that it is about to become visible to the user. This call will be followed by a call to onResume() if the activity moves to the top of the activity stack, or onStop() in the event that it is pushed down the stack by another activity.
-   **onResume()** –Indicates that the activity is now at the top of the activity stack and is the activity with which the user is currently interacting.
-   **onPause()** –Indicates that a previous activity is about to become the foreground activity. Steps may be taken within this method to store *persistent state* information not yet saved by the app. To avoid delays in switching between activities, time consuming operations such as storing data to a database or performing network operations should be avoided within this method. This method should also ensure that any CPU intensive tasks such as animation are stopped.

-   **onStop()** –The activity is now no longer visible to the user. The two possible scenarios that may follow this call are a call to *onRestart()* in the event that the activity moves to the foreground again, or *onDestroy()* if the activity is being terminated.

-   **onDestroy()** –The activity is about to be destroyed, either voluntarily because the activity has completed its tasks and has called the *finish()* method or because the runtime is terminating it either to release memory or due to a configuration change (such as the orientation of the device changing). It is important to note that a call will not always be made to *onDestroy()* when an activity is terminated.

-   **onConfigurationChanged()** –Called when a configuration change occurs for which the activity has indicated it is not to be restarted. The method is passed a Configuration object outlining the new device configuration and it is then the responsibility of the activity to react to the change.

There are two methods intended specifically for saving and restoring the *dynamic state* of an activity:

-   **onRestoreInstanceState(Bundle savedInstanceState)** –This method is called immediately after a call to the *onStart()* method in the event that the activity is restarting from a previous invocation in which state was saved. As with *onCreate(),* this method is passed a Bundle object containing the previous state data. This method is typically used in situations where it makes more sense to restore a previous state after the initialization of the activity has been performed in *onCreate()* and *onStart()*.

-   **onSaveInstanceState(Bundle outState)** –Called before an activity is destroyed so that the current *dynamic state* (usually relating to the user interface) can be saved. The method is passed the Bundle object into which the state should be saved and which is subsequently passed through to the *onCreate()* and *onRestoreInstanceState()* methods when the activity is restarted. Note that this method is only called in situations where the runtime ascertains that dynamic state needs to be saved.

When overriding the lifecycle methods, it is necessary to include a call to the corresponding method in the super class with the exception of *onRestoreInstanceState()* and *onSaveInstanceState()*.

-   For example, the following method overrides the *onCreate()* method but also includes a call to the super class instance of the method:

    ``` java
    protected void onCreate () {
      super.onCreate();
      Log.i("TAG_onCreate", "onCreate");
    }
    ```

    

**Activity Lifecycle States and Lifetimes** 

Img_03

-   Created (not visible yet)
    -   **onCreate(Bundle savedInstanceState)**—static initialization

-   Started (visible)

    -   **onStart()**—when Activity (screen) is becoming visible

    -   **onRestart()**—called if Activity was stopped (calls onStart())

-   Resume (visible)
    -   **onResume()**—start to interact with user

-   Paused(partially invisible)
    -   **onPause()**—about to resume PREVIOUS Activity

-   Stopped (hidden)
    -   **onStop()**—no longer visible, but still exists and all state info preserved

-   Destroyed (gone from memory)
    -   **onDestroy()**—final call before Android system destroys Activity



**Activity Lifetimes** 

Img_04

-   An activity will transition some lifetimes through execution including *entire*, *visible* and *foreground* lifetimes.

-   An activity may pass through the *foreground* and *visible* lifetimes multiple times during the course of the *entire* lifetime.

**Entire Lifetime** –The term “entire lifetime” is used to describe everything that takes place between the initial call to the *onCreate()* method and the call to *onDestroy()* prior to the object terminating*.*

**Visible Lifetime** –Covers the periods of execution between the call to *onStart()* and *onStop()*. During this period the activity is visible to the user, though may not be the object with which the user is currently interacting.

**Foreground Lifetime** –Refers to the periods of execution between calls to the *onResume()* and *onPause()* methods.



#### **2.4 Activity Lifecycle Example**

1.  Create an Empty Activity project and name it ActivityLifecycleExample.

2.  Add following code to MainActivity.java file.

    Img_05

    Img_06

3.  Go to Logcat, and add “Lifecycle” to the filter.

    Img_07

4.  Run the App, it will display the following log in the LogCat.

    Img_08

5.  Click on Clear logcat button to clean up the current logs.

    Img_09

    Img_10

6.  Click on home button, it will display the following log in the LogCat.

    Img_11

    Img_12

7.  Clear the log again, then go back to the App by clicking on the App lists button, add select ActivityLifecycleExampleApp.

    Img_13

    Img_14

8.  Then it will display the following log in the LogCat.

    img_15

9.  Clear the Logcat again, then click on the back button. And it will display the following log in the LogCat.

    Img_16

    Img_17







