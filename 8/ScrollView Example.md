## ScrollView Example

1. Create a new Android Studio project.

2. Res -> values -> styles.xml

   - AppTheme: change to NoActionBar

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_1.png" alt="scrollview_example_1" style="zoom: 67%;" />

3. In layout editor, delete the default "hello world" TextView.

4. Palette -> Containers -> ScrollView and drag it into the visual design editor

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_2.png" alt="scrollview_example_2" style="zoom:67%;" />

5. Add constraints to the ScrollView.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_3.png" alt="scrollview_example_3" style="zoom: 67%;" />

6. Click on LinearLayout under ScrollView in Component Tree. It shows a dash line, which means there is no child view within the LinearLayout because the height of it is "wrap_content".

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_4.png" alt="scrollview_example_4" style="zoom:80%;" />

7. Drag and drop a button within the LinearLayout. 

8. Or drag a button and drop it under the ScrollView -> LinearLayout in Component Tree.

   - Drop a button within the LinearLayout.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_5.png" alt="scrollview_example_5" style="zoom: 67%;" />

   - Drop a button outside of the LinearLayout.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_6.png" alt="scrollview_example_6" style="zoom: 67%;" />

9. Fix the button’s attributes.

   - Layout_marginStart = 100dp
   - Layout_marginTop = 50
   - Layout_marginEnd = 100dp
   - Layout_marginBottom = 50dp

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_7.png" alt="scrollview_example_7" style="zoom:80%;" />

10. Set the background color on both ScrollView and LinearLayout.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_8.png" alt="scrollview_example_8" style="zoom:80%;" />

11. Run the app and there is no scroll effect.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_9.png" alt="scrollview_example_9" style="zoom:75%;" />

12. Now, let’s copy the button and paste it 6 times. 

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_10.png" alt="scrollview_example_10" style="zoom:80%;" />

13. A part of ScrollView is not showing on the visual design.

14. Use the scroll wheel on your mouse to scroll up/down the ScrollView. Or use two figures touch control for laptops.

15. You can also customize the size of the visual design.

    - By clicking on at the lower-right corner of the visual design.

      <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_11.png" alt="scrollview_example_11" style="zoom: 50%;" />

16. Now, run the app.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scrollview_example_12.png" alt="scrollview_example_12" style="zoom: 67%;" />