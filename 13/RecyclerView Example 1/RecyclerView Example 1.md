## RecyclerView Example 1

Example Code: [code](https://github.com/fwangyt/Android-App-Dev-1/raw/master/13/RecyclerView%20Example%201/RecyclerViewDemo1.zip)

1.  Create an Android App with Empty Activity, and name it RecyclerViewDemo1.

2.  Go to activity_main.xml file, delete the existing TextView. Click on the download button aside the
    RecyclerViewto add the RecyclerViewsupport Library.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_01.png)

    Note: To add the RecyclerViewsupport Library, it can also be achieve by adding the line of code to app’s
    build.gradlefile.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_02.png" style="zoom:50%;" />

3.  Drag a RecyclerViewto the Design View with constraints, just keep the existing ID.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_03.png)

4.  Right click on layout under res, then click on New and Layout recourse file. Add file name as food_item,
    and change Root element to LinearLayout. Then click on OK.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_04.png)

5.  To try a different way, this time we add the UI by code. Go to Text mode in food_item.xml file. Change the
    root layout_heightto wrap_content. And then add the following code.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_05.png" style="zoom:33%;" />

6.  Go back to Design mode, we can notice that one item template has been created. This is just how each item
    will look like. Note: the text on the TextViewdoesn’t matter, it is just for effect and placeholder, and will be
    changed later by code.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_06.png)

7.  Create a Food class to contain the information for food. Right click on the package name, and click New,
    then Java Class. Enter Food as class Name, then click on OK.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_07.png)

8.  Add the following fields, getters, setters and constructors to the Food class in Food.java.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_08.png" style="zoom:33%;" />

9.  Now, it is the time to create a data bridge for the RecyclerView. Create a class named
    MyRecyclerViewAdapterand let it extend RecyclerView.Adapter.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_09.png" style="zoom:33%;" />

10.  Put the mouse cursor on the class definition with red line. Then the right bulb will pop up, then click on
     Implement method. Then click on OK.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_10.png)

11.  Add a List of Food type to the adapter as well as the constructor. This is used for storing all the food data.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_11.png)

12.  Create a ViewHolderclass extends RecyclerView.ViewHolderinsideMyRecyclerViewAdapter, the
     ViewHolderclass is used for containing all the UI for each item. Then find each UI with the ID on the item.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_12.png)

13.  The onCreateViewHolderis used for creating the ViewHolderclass, it is usually created by inflating from
     the item.xml file using LayoutInflater. Add the following code to onCreateViewHoldermethod.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_13.png" style="zoom:50%;" />

14.  The onBindViewHoldermethod is used for setting the data value for each item UI. Add the following
     code to onBindViewHoldermethod. ViewHolderclass is the ViewHolderthat we have created in
     onCreateViewHoldermethod which contains all the UI. And iis the index of the current item.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_14.png" style="zoom:50%;" />

15.  The getItemCountreturn the number of items. Simply return the size of foodList.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_15.png" style="zoom:50%;" />

16.  Go the MainActivity.java file, create a food data, the adapter, and set the adapter for the RecyclerView.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_16.png" style="zoom:50%;" />

17.  Run the App, but we cannot see anything. This is because, there is no food in the food list.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_17.png" style="zoom:33%;" />

18.  Now, let’s add some data to the food list.

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_18.png" style="zoom:50%;" />

19.  Run the App again, we can notice that the three food added to the food list have been reflected on

     <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%201/img_19.png" style="zoom:33%;" />