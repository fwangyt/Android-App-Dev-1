## Button And Event 



1. **Create an Android App, and name it ButtonAndEvent.**

2. **Open activity_main.xml file, and delete the existing TextView.**

3. **Drag a TextView and a Button onto the Design View as shown below.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_3.png" style="zoom:67%;" />



4. **Select the TextView, change ID to result_tv, and delete words in text.** 

   ID will be required for subsequent Java code to obtained the UI created in XML file through a call to the ```findViewById()``` method in the activity. Like the following.

   ```java
   final EditText editText = findViewById(R.id.editText);
   ```

   As discussed before, the resources like IDs, layouts, and colors are compiled into a class named *R.*

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_4.png" style="zoom:67%;" />



5. **Select the Button, change ID to btn1, and text to Button1.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_5.png" style="zoom:67%;" />



6. **Click on Infer Constraints button at the top, and the position of the UI will be have constraints.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_6.png" style="zoom:67%;" />



7. **Back to MainActivity.java file, and the following fields definition to the class, and obtain them in the onCreate method through a call to the ```findViewById()``` method.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_7.png" style="zoom:67%;" />



8. **Now it’s t the time to add click events for the button. Add a OnClickListener and a OnLongClickListener onto button1 by adding the following code. The run the app.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_8.png" style="zoom:67%;" />



9. **You will notice that the code in onClick method and onLongClick Method will execute, when user press the button or press the button and hold it with a certain time**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_9_0.png" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_9_1.png" style="zoom:50%;" />



10. **Now, change the return value in onLongClick method to false. Then run the App again.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_10.png" style="zoom:67%;" />



11. **Long press the button and release it. You will see the code in onLongClick is executed, and then the code in onClick is executed. If the return value in onLongClick is true, it means the callback consumed the long click, onClick will not be called. If it is false, the code in onClick callback method will continue to be executed.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_11_0.png" style="zoom:67%;" />

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_11_1.png" style="zoom:67%;" />

12. **There are other 2 ways to add the click event for button. Go to activity_main.xml, and drag a button below the existing one, and set the ID to btn2 and text to Button2. Then set btn2Click to onClick property. Then add constraint onto it.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_12.png" style="zoom:67%;" />



13. **Back to MainActivity.java. Add the following method to MainActivity class. Then run the App.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_13.png" style="zoom:67%;" />



14. **When Button2 is clicked, the code in btn2Click is executed.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_14.png" style="zoom:50%;" />



15. **Go to activity_main.xml, and drag another button, set ID to btn3, and text to Button3. Then add the constraint for it.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_15.png" style="zoom:67%;" />



16. **Back to MainActivity.java, add filed for button3, and get button3 reference by id. Then let the MainActivity its self implements OnClickListener. Add the following code.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_16.png" style="zoom:67%;" />



17. **Run the App again, press Button3, it will show like the following.**

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Example_Button%20and%20Event/img_17.png" style="zoom:50%;" />