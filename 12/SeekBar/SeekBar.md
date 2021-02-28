## SeekBar



A SeekBar is an extension of ProgressBar that adds a draggable thumb.

![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/img_00.png)

There are 2 ways to change the progress value of the SeekBar:

- Touch the thumb and drag left or right to set the current progress level
- Just click on the slider at the position where the desired progress level locates



Clients of the SeekBar can attach a SeekBar.OnSeekBarChangeListener interface to be notified of the user's actions. And it has 3 callback method

- ```onProgressChanged(SeekBar seekBar, int progress, boolean fromUser)```
  - Notification that the progress level has changed. Clients can use the fromUser parameter to distinguish user-initiated changes from those that occurred programmatically.

- ```onStartTrackingTouch(SeekBar seekBar)```
  - Notification that the user has started a touch gesture. Clients may want to use this to disable advancing the seekbar.

- ```onStopTrackingTouch(SeekBar seekBar)```
  - Notification that the user has finished a touch gesture. Clients may want to use this to re-enable advancing the seekbar.



**SeekBar Example**

Example Code: [Code](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/SeekBarExample.zip)

1. Create an project with Empty Activity, and name it SeekBarExample.

2. Go to activity_main.xml file, delete the existing TextView, and drag a SeekBar into the center of the

   screen with constrains.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/img_01.png)

3. We can notice that the SeekBar is too small, change the width of it to 200dp to make it larger.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/img_02.png)

4. Drag a TextView under the SeekBar, and put it center horizontally with constraints. Set ID to progress_tv, and delete the existing text on it.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/img_03.png)

5. Go to MainActivity.java file, add the following code to get the references to the widgets.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/img_04.png)

6. Add the following code to set the OnSeekBarChangeListener for the SeekBar to listen to the progress change, and make the value reflect on the TextView.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/img_05.png)

7. Run the App, and drag the SeekBar, the progress value will be displayed on the TextView.

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/12/SeekBar/img_06.png)

