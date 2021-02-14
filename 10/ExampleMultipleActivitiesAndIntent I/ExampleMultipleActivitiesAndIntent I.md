## Example: Multiple Activities And Intent I

1.  Create a new Android project with Empty Activity, and name it MultipleActivityExample1.

2.  Click on File -> Activity -> Empty Activity to create a new Activity.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_01.png)

3. In the New Android Activity window, change the Activity Name to SecondActivity. Make sure Generate Layout File is selected and click on Finish. The new Activity will be created.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_02.png" style="zoom:50%;" />

   

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_03.png" style="zoom:50%;" />

   

4.  In the meanwhile, the Android Studio automatically register the new created Activity to the AndroidManifext.xml file.

    -   This is necessary for the new Activity to launch.

    -   If we copy Activity source file from other place, this may not be done automatically. We must add it manually in order for the Activity to be started successful.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_04.png" style="zoom:67%;" />

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_05.png" style="zoom:60%;" />

5.  In activity_secondfile, drag a TextViewto the center of the screen with constraints, and change the Text on it to Second Activity.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_06.png)

6.  Go to activity_main.xml file, delete the existing TextViewand then drag a button to the center of the screen with constraints. Change the text on it to Start New Activity. Also, change the ID to start_new_activity_btn.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_07.png)

7.  Go to MainActivity.java file, and add the following code.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_08.png)

8.  Run the App, and click on the Start New Activity Button. Then the Second Activity will be launched. 

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_09.png" style="zoom:50%;" />

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_10.png" style="zoom:50%;" />

9.  It’s time to try to pass data through the activities. Go to activity_main.xml file, and drag EditTextabove the Start New Activity button. Add appropriate constraints to it. And change ID to name_et.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_11.png" style="zoom:50%;" />

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_12.png)

10.  Delete the Text on it, and add the Please Enter Your Name as the hint.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_13.png)

11.  Go to activity_second.xml file, change the ID of the TextViewto result_tv.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_14.png)

12.  Go to MainActivity.java file, add the following code.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_15.png" style="zoom:50%;" />

13.  Go to SecondActivity.java file, add the following code.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_16.png" style="zoom:50%;" />

14.  Run the App again, enter some text into the EditTextand click on the Start New Activity Button. Then the Second Activity will be launched with some Text. 

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_17.png" style="zoom:50%;" />

     

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/ExampleMultipleActivitiesAndIntent%20I/img_18.png" style="zoom:50%;" />