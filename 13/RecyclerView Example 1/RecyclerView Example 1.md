## RecyclerView Example 1

Example Code:

1.  Create an Android App with Empty Activity, and name it RecyclerViewDemo1.

2.  Go to activity_main.xml file, delete the existing TextView. Click on the download button aside the
    RecyclerViewto add the RecyclerViewsupport Library.

    Img_01

    Note: To add the RecyclerViewsupport Library, it can also be achieve by adding the line of code to app’s
    build.gradlefile.

    Img_02

3.  Drag a RecyclerViewto the Design View with constraints, just keep the existing ID.

    Img_03

4.  Right click on layout under res, then click on New and Layout recourse file. Add file name as food_item,
    and change Root element to LinearLayout. Then click on OK.

    Img_04

5.  To try a different way, this time we add the UI by code. Go to Text mode in food_item.xml file. Change the
    root layout_heightto wrap_content. And then add the following code.

    Img_05

6.  Go back to Design mode, we can notice that one item template has been created. This is just how each item
    will look like. Note: the text on the TextViewdoesn’t matter, it is just for effect and placeholder, and will be
    changed later by code.

    Img_06

7.  Create a Food class to contain the information for food. Right click on the package name, and click New,
    then Java Class. Enter Food as class Name, then click on OK.

    Img_07

8.  Add the following fields, getters, setters and constructors to the Food class in Food.java.

    Img_08

9.  Now, it is the time to create a data bridge for the RecyclerView. Create a class named
    MyRecyclerViewAdapterand let it extend RecyclerView.Adapter.

    Img_09

10.  Put the mouse cursor on the class definition with red line. Then the right bulb will pop up, then click on
     Implement method. Then click on OK.

     Img_10

11.  Add a List of Food type to the adapter as well as the constructor. This is used for storing all the food data.

     Img_11

12.  Create a ViewHolderclass extends RecyclerView.ViewHolderinsideMyRecyclerViewAdapter, the
     ViewHolderclass is used for containing all the UI for each item. Then find each UI with the ID on the item.

     Img_12

13.  The onCreateViewHolderis used for creating the ViewHolderclass, it is usually created by inflating from
     the item.xml file using LayoutInflater. Add the following code to onCreateViewHoldermethod.

     Img_13

14.  The onBindViewHoldermethod is used for setting the data value for each item UI. Add the following
     code to onBindViewHoldermethod. ViewHolderclass is the ViewHolderthat we have created in
     onCreateViewHoldermethod which contains all the UI. And iis the index of the current item.

     Img_14

15.  The getItemCountreturn the number of items. Simply return the size of foodList.

     Img_15

16.  Go the MainActivity.java file, create a food data, the adapter, and set the adapter for the RecyclerView.

     Img_16

17.  Run the App, but we cannot see anything. This is because, there is no food in the food list.

     Img_17

18.  Now, let’s add some data to the food list.

     Img_18

19.  Run the App again, we can notice that the three food added to the food list have been reflected on

     Img_19