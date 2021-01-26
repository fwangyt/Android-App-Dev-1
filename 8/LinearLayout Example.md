## LinearLayout Example

### LinearLayout

- LinearLayout is a view group that aligns all children in a single direction, vertically or horizontally.
- The layout direction can be specified with the android:orientation attribute—"horizontal" for a row, "vertical" for a column.
- The android:gravity attribute can be used to specify how an object should position its content, on both the X and Y axes, within its own bounds.

### Example

1. Create a new project with Empty Activity and name it LinearLayoutExample.

2. Go to activity_main.xml file, try to delete the existing ConstraintLayout and the TextView under it.

3. You may notice that the outer most ConstratintLayout is not deletable, because there must exist a layout manager.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_1.png" alt="linear_layout_example_1" style="zoom: 67%;" />

4. Right click on ConstraintLayout and select Convert view button.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_2.png" alt="linear_layout_example_2" style="zoom:75%;" />

5. Select LinearyLayout and click on Apply.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_3.png" alt="linear_layout_example_3" style="zoom:75%;" />

   Note: the LinearLayout can also be added by selecting Layouts in Palette, and dragging a LinearLayout onto the design view or the Component Tree. This may not work for the outer most layout, but can be used to add a layout inside another layout.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_4.png" alt="linear_layout_example_4" style="zoom:75%;" />

6. Drag a TextView and 2 Buttons under the LinearLayout. The 3 widgets will be aligned horizontally with same width.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_5.png" alt="linear_layout_example_5" style="zoom: 75%;" />

   Note: Initially, when the LinearLayout is in horizontal mode, the widgets added to it will have wrap_content for both layout_width and layout_height. However, the layout_weight attribute has been added by default, which will make the widgets to fill up the horizontal space and the width fill be distributed proportional to the layout_weight value. This is much like the weighted chain in ConstratintLayout.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_6.png" alt="linear_layout_example_6" style="zoom:75%;" />

7. Change the layout_weight for the TextView and the second Button to 2. Now it is obvious that TextView and the second Button takes more width than the first Button, but not exactly twice.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_7.png" alt="linear_layout_example_7" style="zoom: 50%;" />

8. To fix this, set all the layout_width for the widgets to 0dp. Now the width for the TextView and second Button will be exactly twice as the height for the first Button.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_8.png" alt="linear_layout_example_8" style="zoom: 50%;" />

9. Select the LinearLayout, and change the orientation to vertical. The widgets will now be aligned vertically. But it looks a little bit weird since all the widgets disappear. This is because the both have 0dp for the width.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_9.png" alt="linear_layout_example_9" style="zoom: 50%;" />

10. This can be fixed by deleting all the widgets, and drag them again. And this time, for the LinearyLayout in vertical mode, the widget added to it has match_parent for layout_width and wrap_content for layout_height, with no layout_weight added.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_10.png" alt="linear_layout_example_10" style="zoom:50%;" />

11. Select the second Button, add 20dp top and left margin. Then the second Button will have 20dp distance to the left and its top will have 20dp distance to the first Button.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_11.png" alt="linear_layout_example_11" style="zoom:50%;" />

12. Select the fist Button, and add 20dp for the top padding. It will now have 20dp space for the top part inside the widget. The difference between margin and padding is that the margin adding the space outside the widget, but padding adding the space inside the widget.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/linear_layout_example_12.png" alt="linear_layout_example_12" style="zoom: 67%;" />

