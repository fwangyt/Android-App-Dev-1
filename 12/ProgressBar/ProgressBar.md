## ProgressBar

A good App should give user some feedbacks while doing some time-intensive task, like

- Connecting to backend API to do authentication

- Downloading a file
- Fetching data from database



At this time, a ProgressBar is need to give user information that the App is still running, please be patient... Or user may think the App is not responsible, which is not a good User Experience. They may even kill the App.



**ProgressBar** is a user interface element that indicates the progress of an operation. Progress bar supports two modes to represent progress: determinate, and indeterminate. Display progress bars to a user in a non- interruptive way.



**Indeterminate Progress**

Use indeterminate mode for the progress bar when you do not know how long an operation will take.

Indeterminate mode is the default for progress bar and shows a cyclic animation without a specific amount of progress indicated.

![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_01.png)



**Determinate Progress**

Use determinate mode for the progress bar when you want to show that a specific quantity of progress has occurred.

For example:

- the percent of a file being retrieved
- the amount records in a batch written to database 
- the progress of an audio file that is playing

![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_02.png)



To indicate determinate progress, you need to set the style of the progress bar to R.style.Widget.AppCompat.ProgressBar.Horizontal and set the amount of progress.

The following example shows a determinate progress bar that is 25% complete both in Design View and code (ether is OK):

![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_03.png)

![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_04.png)



**Change Progress**

In order to give some feedback information to users, it is necessary to update the progress value of the ProgressBar in determinate mode.

You can update the percentage of progress displayed by using the setProgress(int) method or by calling incrementProgressBy(int) to increase the current progress completed by a specified amount.

By default, the maximum value of the ProgressBar is 100, and the minimum value is 0. And these two values can be changed by setting the android:max and android:min attribute.



- By default, the progress bar is full when the progress value reaches 100.

- The overall percentage can be calculated by the following formula: 

  - 𝑃𝑒𝑟𝑐𝑒𝑛𝑡𝑎𝑔𝑒 = 𝑝𝑟𝑜𝑔𝑟𝑒𝑠𝑠 − 𝑚𝑖𝑛 / 𝑚𝑎𝑥 − 𝑚𝑖𝑛

- The following figure shows a ProgressBar with max value of 150, and min value of -50, and the progress is set to 80, which should have percentage of 65%.

  ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_05.png)

- Note: The progress of the ProgressBar in indeterminate mode can also be changed, but nothing will be reflected on the ProgressBar, it will still be the cyclic animation.



**Display and Hide ProgressBar**

We may not always want to display the ProgressBar. Instead, display it when a task starts, which some information need to be presented to the user. And hide it, when the task is done.

To hide a ProgressBar, set the *android:visibility* attribute in xml file to *gone* or *invisible*, or call the *setVisibility* method on it and pass *View.GONE* or *View.INVISIBLE* as the parameter.

To display a ProgressBar, set the *android:visibility* attribute in xml file to *visible*, or call the *setVisibility* method on it and pass *View.VISIBLE* as the parameter.



**Example 1**

Example Code: [Code](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/ProgressBarExample1.zip)

1. Let try an example for ProgressBar in determinate mode. Create an empty Activity Android project, and name it ProgressBarExample1.

2. Go to activity_main.xml file, delete the existing TextView, and drag a ProgressBar into the center of the screen with constraints.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_06.png)

3. Typically, it is better to hide the ProgressBar, and display when necessary. Change the visibility attribute to invisible.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_07.png)

4. Drag a button, and put it under the center of the screen (it is same as the center of the hidden ProgressBar). Set ID to display_progress_bar_btn, and text to Display.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_08.png)

5. Drag a button, and put it aside the Display Button. Set ID to hide_progress_bar_btn, and text to Hide.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_09.png)

6. Add constraints for the two buttons, it is better to do a chain for the two buttons.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_10.png)

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_11.png)

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_12.png)

7. Go to MainActivity.java file, and the following code to get the references for the 3 widgets.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_13.png)

8. Add the OnClickListener for Display Button to let the ProgressBar be displayed.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_14.png)

9. Add the OnClickListener for Hide Button to let the ProgressBar be hidden.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_15.png)

10. Run the App, click on Display Button, then the ProgressBar will display. Click on Hide Button, the ProgressBar will disappear.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_16.png)

    

**Example 2**

Example Code: [Code](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/ProgressBarExample2.zip)

0. Let’s try another example for ProgressBar with determinate mode. And it is based on the ProgressBarExample1. If you like, you can make a copy, and change it to ProgressBarExample2 to continue.

1. Go to aitivity_main.xml file, select the ProgressBar, and change the style to Widget.AppCompat.ProgressBar.Horizontal. The ProgressBar has now been changed to determinate mode.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_17.png)

   Note: It is also possible directly drag a ProgressBar in determinate mode from the Palette.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_18.png)

2. However, the ProgressBar looks so small. To solve this, change the width of it to 200dp.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_19.png)

3. Drag another button, and put it under the existing 2 buttons and center horizontally with constraints. Set ID to add_progress_btn and text to Add Progress.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_20.png)

4. Go to MainActivity.java file, add the following code to get reference to the new added Button.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_21.png)

5. Add the OnClickListener for the Button to increate the progress value for the ProgressBar when it is clicked.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_22.png)

6. Run the App, and display the Progress Bar. The progress will increase when the Add Progress Button is clicked.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_23.png)

   Note: To increate the progress value, it can be achieved by calling incrementProgressBy method.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/ProgressBar/img_24.png)