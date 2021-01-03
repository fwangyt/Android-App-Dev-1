## Switch Example

### Switch

1. A Switch is a two-state toggle switch widget that can select between two options.
2. User may drag the "thumb" back and forth to choose the selected option, or simply tap to toggle as if it were a checkbox.
3. The checked property with type of Boolean on the Switch is used to indicated whether the switch is "On" or "Off".

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_1.png" alt="switch_example_1" style="zoom: 33%;" />

### Text on Switch

1. Sometimes, there is text associated with the Switch.

2. The text property controls the text displayed in the label for the switch, as illustrated below.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_2.png" alt="switch_example_2" style="zoom: 33%;" />

### Text on Thumb

1. There could also be the text on the thumb.
2. The textOn and textOff properties control the text on the thumb separately.
3. To make this work, the showText property on the Switch should be set to true.
4. Also, the feature requires the minimum SDK version of 21. It can compile, and run on devices under 21, but this feature will not work.

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_3.png" alt="switch_example_3" style="zoom:33%;" />

### Change minimum SDK Version

To change the minimum support android version:

1. Go to app build.gradle file.

2. Change minSdkVersion to whatever needed.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_4.png" alt="switch_example_4" style="zoom: 50%;" />

### Check Change Listener

1. Switch has a OnCheckedChangeListener property that can be used to notify developer there a check changes on the Switch.
2. Note: the OnClickListener can also be added to the Switch for listening the changes. But there is a drawback on it, the callback will not send the new state of check. And the check state value can be acquired by calling isCheck method on it.

### Switch Example

1. Create a Android project with Empty Activity, and name it Switch Example.

2. Go to activity_mail.xml file, delete the existing TextView, and drag a Switch to the center of the screen with constraints. And set ID to my_switch.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_5.png" alt="switch_example_5" style="zoom: 67%;" />

3. Set text property to This is a Switch!, set textOn property to on, and set textOff property to off.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_6.png" alt="switch_example_6" style="zoom: 67%;" />

4. Since the showText property could be hard to find, there is an easy to make it. Go to Text mode, and add the following line of code.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_7.png" alt="switch_example_7" style="zoom:67%;" />

5. Go back to Design mode, and place anther TextView under the Switch with constraints and set the ID to result_tv.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_8.png" alt="switch_example_8" style="zoom: 67%;" />

6. Go to MainActivity.java, and add the following code.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_9.png" alt="switch_example_9" style="zoom:67%;" />

7. Run the App, on click the Switch. It will also display some information in the Logcat.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_10.png" alt="switch_example_10" style="zoom: 67%;" />

8. Click on the Switch again.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_example_11.png" alt="switch_example_11" style="zoom:67%;" />