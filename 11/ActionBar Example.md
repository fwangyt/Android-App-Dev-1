## ActionBar Example

1. Create a new Android project. Open *activity_main.xml* and select design mode.

2. To show or hide the ActionBar on visual design window

   - View Options -> Check or uncheck **Show Layout Decorations**.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_1.png" alt="action_bar_example_1" style="zoom: 67%;" />

3. Let’s change the style of the ActionBar. Because the default ActionBar is managed by the application theme, we have to modify the app theme to change the style of the ActionBar. We will learn how to customize the app bar with ToolBar in next week.

4. Open res -> values -> styles.xml

   - Modify the string shown below. Let’s just change it to NoActionBar.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_2.png" alt="action_bar_example_2" style="zoom: 67%;" />

5. Run the app, there is no ActionBar anymore.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_3.png" alt="action_bar_example_3" style="zoom: 50%;" />

6. Back to activity_main.xml, click on Theme for preview.

7. Select different themes and take a look. Notice that this is just a preview. Click on MoreThemes... and select *AppCompat.Light.DarkActionBar*.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_4.png" alt="action_bar_example_4" style="zoom:67%;" />

8. Run the app, the ActionBar was not changed, and neither the app theme.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_5.png" alt="action_bar_example_5" style="zoom: 67%;" />

9. Open styles.xml again. Modify the app theme value.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_6.png" alt="action_bar_example_6" style="zoom:61%;" />

10. Run the app again. Now it’s changed.

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_7.png" alt="action_bar_example_7" style="zoom: 67%;" />

11. Let’s take a look at ActionBar’s methods.

    - To get ActionBar object in MainActivity.java, use getSupportActionBar.
    - Then, set the title and the subtitle of the ActionBar.

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_8.png" alt="action_bar_example_8" style="zoom:61%;" />

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_example_9.png" alt="action_bar_example_9" style="zoom:67%;" />