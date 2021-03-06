## Toast

Toasts are transient notifications that don’t steal focus, cannot be interacted with, and are non-modal; they appear, show a brief message, and then disappear. 

Given these limitations, they should only be used to confirm a user’s action immediately after it occurs, or for system-level messages. They should only be displayed when your app has an active Activity visible. It is usually when displaying some information. For example, in an App that requires authentication, a toast can be used to display some information like the credentials are not right.

 ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/Toast/img_01.png)



The Toast class includes a static makeText method that creates a standard Toast display window.

To construct a new Toast, pass the current Context, the text to display, and the length of time to display it (```LENGTH_SHORT``` or ```LENGTH_LONG```) into the makeText method. After creating a Toast, you can display it by calling show method.

``` java
Context context = this;
String msg = "To health and happiness!";
int duration = Toast.LENGTH_SHORT;
Toast toast = Toast.makeText(context, msg, duration);
toast.show();
```



### Example

Example code: [code](https://github.com/fwangyt/Android-App-Dev-1/raw/master/13/Toast/ToastExample.zip)



1.  Create an Android Studio project with Empty Activity, and name it ToastExample

2.  Go to activity_main.xml file, delete the existing TextView.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/Toast/img_02.png)

3.  Drag a Button to the center of the screen with constraints, set ID to short_toast_btn, and set text to Display a Short Toast

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/Toast/img_03.png)

4.  Drag another Button and place it below the previous Button, and add constraints to it. Then set ID to long_toast_btn, and set text to Display a Long Toast.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/Toast/img_04.png)

5.  Go to MainActivity.java file, and add the following code.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/Toast/img_05.png)

6.  Run the App, and click on each Button to feel the difference between the time durationg of the two toasts

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/Toast/img_06.png)