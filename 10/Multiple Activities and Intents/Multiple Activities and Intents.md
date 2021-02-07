## Multiple Activities and Intents



### Multiple Activities

#### 1.1 Activity Overview

-   Recall: an Activity represents a single screen with a user interface.

-   Real-world Android apps are multiple activities app.

-   Example: 3 activities to a simple user account management.
    -   Login screen
    -   Signup screen
    -   Reset password screen



#### 1.2 Create a New Activity

-   In the Project window, right-click the app folder and select New > Activity > Empty Activity. 

    Img_01

-   In the Configure Activity window, enter Activity Name. Leave all other properties set to their defaults and click Finish.

    img_02

-   Android Studio automatically does three things: Creates the nameActivityfile. Creates the layout file activity_name.xml, which corresponds with the nameActivityfile. Adds the required <activity> element in AndroidManifest.xml.

    Img_03



### Intent

An Intent is an object that provides runtime binding between separate components, such as two activities.



#### 1.1 Forms

-   **Explicit Intents** have specified a component (via `setComponent(ComponentName)` or `setClass(Context, Class)`), which provides the exact class to be run. Often these will not include any other information, simply being a way for an application to launch various internal activities it has as the user interacts with the application.

    ``` java
    // 1. Create an intent by its constrctor
    Intent intent = new Intent(this, SecondActivity.class);  
    startActivity(intent);
    ```

    ``` java
    // 2. setComponent method
    Intent intent = new Intent();    
    intent.setClass(this, SecondActivity.class);          
    startActivity(intent); 
    ```

    ``` java
    // 3. setClass / setClassName
    Intent intent = new Intent();    
    intent.setClass(this, SecondActivity.class);  
    //	intent.setClassName(this, "com.example.app.SecondActivity");  
    //	intent.setClassName(this.getPackageName(),"com.example.app.SecondActivity");            
    startActivity(intent); 
    ```

    

-   **Implicit Intents** have not specified a component; instead, they must include enough information for the system to determine which of the available components is best to run for that intent



