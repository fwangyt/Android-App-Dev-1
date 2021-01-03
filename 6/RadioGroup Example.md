## Radio Button and Radio Group

### Radio Button

1. A radio button is a two-states button that can be either checked or unchecked.

2. When the radio button is unchecked, the user can press or click it to check it.

3. However, a radio button cannot be unchecked by the user once checked.

4. Radio buttons are normally used together in a *RadioGroup*.

5. When several radio buttons live inside a radio group, checking one radio button unchecks all the others.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_1.png" alt="radio_group_example_1" style="zoom: 50%;" />

### Radio Group

1. Used to create a multiple-exclusion scope for a set of radio buttons.
2. Checking one radio button that belongs to a radio group unchecks any previously checked radio button within the same group.
3. Initially, all of the radio buttons are unchecked.
4. While it is not possible to uncheck a particular radio button, the radio group can be cleared to remove the checked state.

### Example

1. Create a project with Empty Activity and name it RadioGroupDemo.

2. Go to activity_main.xml file, and delete the existing TextView.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_2.png" alt="radio_group_example_2" style="zoom: 50%;" />

3. Drag a RadioGroup in Buttons category within the Palette onto Design View and position it at the center of the screen.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_3.png" alt="radio_group_example_3" style="zoom: 67%;" />

4. Drag three RadioButtons into RadioGroup, and they will be automatically set the id to radioButton1, radioButton2 and radioButton3 separately. (id can be adjusted manually later)

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_4.png" alt="radio_group_example_4" style="zoom:67%;" />

5. Change the text on the radio buttons to Choice 1, Choice 2, Choice 3 separately by selecting the radio button and change text attribute.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_5.png" alt="radio_group_example_5" style="zoom:67%;" />

6. Add the id for the radio group, which will be used to get the reference of the view in Java code later. This time, select the RadioGroup, and set it to radio_group.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_6.png" alt="radio_group_example_6" style="zoom:67%;" />

7. Then add a TextView under the radio group, and change ID to result_tv.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_7.png" alt="radio_group_example_7" style="zoom:67%;" />

8. Click on the Radio Group and all four constraints for it. In order to make it look nice, we can constraint it at the center of the screen. Select Radio Group, and drag the four circle to the corresponding border.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_8.png" alt="radio_group_example_8" style="zoom:67%;" />

9. Also constraint the TextView make it center horizontally, and be positioned 80dp under the Radio Group. This can also be done by selecting the Text View add click on the 3 "+" buttons. Then adjust the constraint values in as following.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_9.png" alt="radio_group_example_9" style="zoom: 67%;" />

10. Run it on the simulator. It is obvious that if one radio button is selected, the previous checked button will be unchecked.

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_10.png" alt="radio_group_example_10" style="zoom: 50%;" />

11. Now, we should continue to make some response when radio button is checked. Back to the Java code, add the following code to crate a Radio group and a TextView, then make them reference to the view created previously.

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_11.png" alt="radio_group_example_11" style="zoom:67%;" />

12. Next step is to add Listener for the Radio Group to let it respond to check changed. Add an OnCheckedChangeListener for it with the following code.

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_12.png" alt="radio_group_example_12" style="zoom:67%;" />

13. This time, when each Radio Button is checked, it will display some text in TextView.

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_group_example_13.png" alt="radio_group_example_13" style="zoom: 50%;" />