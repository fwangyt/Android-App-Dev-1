## Example MultipleActivitiesAndIntent II

1.  Create an Android Studio project with Empty Empty.

2.  Create a new Activity, and name it LoginActivity. Make sure Launcher Activity is selected.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_01.png)

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_02.png)

3.  Go to AndroidManifest.xml file, we can notice that an intent-filter has been added, which mean the LoginActivityis going to be started first when the App launches. But it has also been added to MainActivityas default. To solve the conflict, simply delete the intent-filter on MainActivity.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_03.png)

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_04.png)

4.  Go to activity_login.xml file. Drag an EditTextwith Plain Text type onto it, add ID as username_et, delete the text on it, and add hint as Please Enter Username.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_05.png)

5.  Drag an EditTextwith password type onto it, and put it under Username EditText. Add ID as password_et, and add hint as Please Enter Password.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_06.png)

6.  Drag a Button onto it, and place it under the Password EditText. Set the ID to lgoin_btn, and set text as Login. 

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_07.png)

7.  Before going to next step, add the constraints on these UI.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_08.png)

8.  Go to activity_main.xml file, and set ID to result_tvfor the existing TextView.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_09.png)

9.  Go to LoginActivity.java file, add the following code.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_10.png)

10.  Go to MainActivity.java file, add the following code.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_11.png)

11.  Run the App, for now, it is very much like we did in the previous example.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_12.png"  style="zoom:50%;" />

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_13.png" style="zoom:50%;" />

12.  Now it is the time to add register functions. Go to activity_login.xml file, and drag another Button under the Login Button. Change the ID to register_btnand set the text attribute to Register. Also add constraint for it.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_14.png)

13.  Create another Activity named RegisterActivity.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_15.png)

14.  Go to activity_regesterlxmlfile. Drag a normal EditTextonto it. Set the ID to username_et, delete the text on it, and set hint to Please Enter Username.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_16.png)

15.  Drag a password EditTextonto it, and place it under the Username EditText. Set the ID to password_et, and set hint to Please Enter Password.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_17.png)

16.  Drag another password EditTextonto it, and place it under the Password EditText. Set the ID to repeat_password_et, and set hint to Please Repeat Password.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_18.png)

17.  Drag a Button onto it, and place it under the Repeat Password EditText. Set the ID to finish_btn, and set text as Finish. 

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_19.png)

18.  Before going to next step, add the constraints on these UI.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_20.png)

19.  Go to RegisterActivity.java file, and add the following code.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_21.png)

20.  Go to Login.java file, and add the following code.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_12.png" style="zoom:50%;" />

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_23.png" />

21.  Run the App, and click on the Register Button. Enter some information and click on the Finish Button. It will first go back to Login Activity, and then go to Main Activity automatically.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_24.png" style="zoom:50%;" />

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20II/img_23.png" style="zoom:50%;" />