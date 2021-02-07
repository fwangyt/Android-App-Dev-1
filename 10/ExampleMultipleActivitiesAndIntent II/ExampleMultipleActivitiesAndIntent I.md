## Example MultipleActivitiesAndIntent II

1.  Create an Android Studio project with Empty Empty.

2.  Create a new Activity, and name it LoginActivity. Make sure Launcher Activity is selected.

    Img_01

    Img_02

3.  Go to AndroidManifest.xml file, we can notice that an intent-filter has been added, which mean the LoginActivityis going to be started first when the App launches. But it has also been added to MainActivityas default. To solve the conflict, simply delete the intent-filter on MainActivity.

    Img_03

    Img_04

4.  Go to activity_login.xml file. Drag an EditTextwith Plain Text type onto it, add ID as username_et, delete the text on it, and add hint as Please Enter Username.

    Img_05

5.  Drag an EditTextwith password type onto it, and put it under Username EditText. Add ID as password_et, and add hint as Please Enter Password.

    img_06

6.  Drag a Button onto it, and place it under the Password EditText. Set the ID to lgoin_btn, and set text as Login. 

    Img_07

7.  Before going to next step, add the constraints on these UI.

    Img_08

8.  Go to activity_main.xml file, and set ID to result_tvfor the existing TextView.

    Img_09

9.  Go to LoginActivity.java file, add the following code.

    img_10

10.  Go to MainActivity.java file, add the following code.

     img_11

11.  Run the App, for now, it is very much like we did in the previous example.

     Img_12

     Img_13

12.  Now it is the time to add register functions. Go to activity_login.xml file, and drag another Button under the Login Button. Change the ID to register_btnand set the text attribute to Register. Also add constraint for it.

     Img_14

13.  Create another Activity named RegisterActivity.

     img_15

14.  Go to activity_regesterlxmlfile. Drag a normal EditTextonto it. Set the ID to username_et, delete the text on it, and set hint to Please Enter Username.

     img_16

15.  Drag a password EditTextonto it, and place it under the Username EditText. Set the ID to password_et, and set hint to Please Enter Password.

     img_17

16.  Drag another password EditTextonto it, and place it under the Password EditText. Set the ID to repeat_password_et, and set hint to Please Repeat Password.

     img_18

17.  Drag a Button onto it, and place it under the Repeat Password EditText. Set the ID to finish_btn, and set text as Finish. 

     img_19

18.  Before going to next step, add the constraints on these UI.

     img_20

19.  Go to RegisterActivity.java file, and add the following code.

     img_21

20.  Go to Login.java file, and add the following code.

     img_22

     Img_23

21.  Run the App, and click on the Register Button. Enter some information and click on the Finish Button. It will first go back to Login Activity, and then go to Main Activity automatically.

     Img_24

     Img_25