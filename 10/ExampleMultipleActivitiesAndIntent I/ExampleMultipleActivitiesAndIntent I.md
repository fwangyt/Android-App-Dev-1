## Example: MultipleActivitiesAndIntent I

1.  Create a new Android project with Empty Activity, and name it MultipleActivityExample1.

2.  Click on File -> Activity -> Empty Activity to create a new Activity.

    Img_01

3.  In the New Android Activity window, change the Activity Name to SecondActivity. Make sure Generate Layout File is selected and click on Finish. The new Activity will be created.

    Img_02

    Img_03

4.  In the meanwhile, the Android Studio automatically register the new created Activity to the AndroidManifext.xml file.

    -   This is necessary for the new Activity to launch.

    -   If we copy Activity source file from other place, this may not be done automatically. We must add it manually in order for the Activity to be started successful.

    Img_04

    Img_05

5.  In activity_secondfile, drag a TextViewto the center of the screen with constraints, and change the Text on it to Second Activity.

    Img_06

6.  Go to activity_main.xml file, delete the existing TextViewand then drag a button to the center of the screen with constraints. Change the text on it to Start New Activity. Also, change the ID to start_new_activity_btn.

    Img_07

7.  Go to MainActivity.java file, and add the following code.

    Img_08

8.  Run the App, and click on the Start New Activity Button. Then the Second Activity will be launched. 

    Img_09

    Img_10

9.  It’s time to try to pass data through the activities. Go to activity_main.xml file, and drag EditTextabove the Start New Activity button. Add appropriate constraints to it. And change ID to name_et.

    Img_11

    img_12

10.  Delete the Text on it, and add the Please Enter Your Name as the hint.

     img_13

11.  Go to activity_second.xml file, change the ID of the TextViewto result_tv.

     img_14

12.  Go to MainActivity.java file, add the following code.

     Img_15

13.  Go to SecondActivity.java file, add the following code.

     Img_16

14.  Run the App again, enter some text into the EditTextand click on the Start New Activity Button. Then the Second Activity will be launched with some Text. 

     img_17

     img_18

