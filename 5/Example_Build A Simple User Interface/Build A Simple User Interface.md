## **Build A Simple User Interface**

1. **Open Android Studio, create a new Project with Empty Activity, and name FirstUIExample.**

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_1_0.png" style="zoom:67%;" />

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_1_1.png" style="zoom:67%;" />

   

2. **Open activity_main.xml file, delete Hello World TextView by selecting it and hit delete button.**

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_2.png" style="zoom:67%;" />

   

3. **Drag a EditText, a Button, a TextView From Palette onto the Design View. The EditText can be found at Palette->Text->Plain Text. Click on Infer Constrains then it will show like the following.**

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_3.png" style="zoom:67%;" />

   

4. **Select Edit Text, change ID to name_et, change hint to "Please Enter You name", and delete the word in the text.**

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_4.png" style="zoom:67%;" />

   

5. **Select Button, change ID to name_btn, and change text to Click Me!**

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_5.png" style="zoom:67%;" />

   

6. **Select TextView, change ID to result_tv, and delete the word in text.** 

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_6.png" style="zoom:67%;" />

   

7. **Go back to MainActivity.java, and add the following fields to the class. You may need to import the class. Typically it will be done by the auto complete, but if is not, you can achieve this by click ALT + ENTER.** 

   ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_7.png)

   

8. **Add the following code in onCreate Method after the existing code.** 

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_8.png" style="zoom:67%;" />

   

9. **Run the App, by clicking the Run button. And launch the simulator. Enter your name like "Mike", and click on the button. The result will show below.** 

   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Build%20A%20Simple%20User%20Interface/img_9.png" style="zoom:67%;" />