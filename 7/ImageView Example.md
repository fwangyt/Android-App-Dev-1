## ImageView Example

### Overview

1. ImageView widget is ued to display a single image from image resources, for example Bitmap or Drawable resources in Android.

2. It is also used to apply tints to an image and handle image scaling.

3. The following is an example of image view.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_1.png" alt="image_view_example_1" style="zoom: 50%;" />

### Example

1. Create a project with Empty Activity and name it ImageViewDemo.

2. Go to activity_main.xml file, and delete the existing TextView.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_2.png" alt="image_view_example_2" style="zoom:50%;" />

3. Expend resources folder, then expend drawable folder. Drag two images name tiger1.jpg and tiger2.jpg into it. Select drawable folder, and the click on OK. Click OK again for the next pop-up window named Copy.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_3.png" alt="image_view_example_3" style="zoom:50%;" />

4. Then the images have been added to the project as resources. The difference between drawable and deawable-v24 is that the later one is used for Android Version later than 24 (Android 7.0), but drawable can be used for universal Android Version.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_4.png" alt="image_view_example_4" style="zoom:75%;" />

5. Back to the layout and drag an ImageView onto the center of the design view. In the resources select view, expend the project, and select tiger1. Then click on OK.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_5.png" alt="image_view_example_5" style="zoom:50%;" />

6. Position the ImageView to the center of the screen by adding constraints, and do some adjustment on the constraints.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_6.png" alt="image_view_example_6" style="zoom:50%;" />

7. The ImageView is a little bit large, change the width and height to 200dp to make it smaller.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_7.png" alt="image_view_example_7" style="zoom:50%;" />

8. Run the simulator, it will display tiger1.jpg at the center of the screen.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_8.png" alt="image_view_example_8" style="zoom:75%;" />

9. Next, add a button under the ImageView, and add the following constraints to it.

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_9.png" alt="image_view_example_9" style="zoom:50%;" />

10. Change the text on the button to Change Image, and add btnClick onto the onClick attribute.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_10.png" alt="image_view_example_10" style="zoom:50%;" />

11. Back to MainActivity.java, and add the following code. 

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_11.png" alt="image_view_example_11" style="zoom:75%;" />

12. Run the simulator again, when click on Change Image button, the image in the ImageView will be changed to tiger2.jpg.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_example_12.png" alt="image_view_example_12" style="zoom:50%;" />