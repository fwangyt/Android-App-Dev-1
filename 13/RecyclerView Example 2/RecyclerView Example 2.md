## RecyclerView Example 1



#### RecyclerView Data Change

-   Most of the time, the dataset binding to RecyclerViewshould not be static, which means we need to
    dynamically make the changes on the dataset.
-   These operations could involve add, delete and modify a piece of data on the dataset.



The steps for adding a piece of data to RecyclerView:

1.  Add the data to the container class, like ArrayList.
2.  Make a call to notifyDataSetChangedor notifyItemInsertedmethod on the Adapter.

Note:
The differences between notifyDataSetChangedand notifyItemInsertedmethod

1.  Both of them can make the RecyclerViewreact to the changes on the dataset.
2.  notifyItemInsertedmethod requires another parameter to specify the index of the data inserted.
3.  The RecyclerViewwill not have insertion animation if notifyDataSetChangedmethod is call, but will
    have animation if notifyItemInsertedmethod on the Adapter is called.



#### Example

Example code: [code](https://github.com/fwangyt/Android-App-Dev-1/raw/master/13/RecyclerView%20Example%202/RecyclerViewDemo2.zip)



1.  This example is based on RecyclerViewDemo1, you can make a copy of it, and change the name to
    RecyclerViewDemo2, or directly make changes on RecyclerViewDemo1.

2.  In MyRecyclerViewAdapter.java class, add a method which accept a Food variable and name it addFood.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_02.png)

3.  Add the food to the food list, and then call notifyDataSetChangedwith the following code.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_03.png)

4.  Let’s try to add a menu to the Activity for adding the food. Right click on res, New, and then Android
    Resource File. Enter file name as menu_main, and change Resource type to Menu, then click on OK.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_04、.png)

5.  In menu_main.xml, in design view, add a Menu Item, set ID to action_add, set title to Add, and set
    showAsActionto always.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_05.png)

6.  Go to MainActivity.java file, add the following code to create the options menu.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_06.png)

7.  Add the following code to make the Activity response to options item selected events.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_07.png)

8.  In order to add food, we need another Activity for entering some food information. Create a new Activity,
    and name it AddFoodActivity.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_08.png)

9.  Go to activity_add_food.xml file, drag a EditTextwith Plain Text, put it center horizontally. Set ID to
    food_name_et, delete the text on it, and set hint to Please Enter Food Name.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_09.png)

10.  Drag another EditTextwith decimal number type, and put it under food name EditText. Then set ID to
     food_price_et, and set hint to Please Enter Food Price.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_10.png)

11.  Put a Button it under food price EditText. Then set ID to finish_btn, and set text to Finish.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_11.png)

12.  Before going to next step, don’t forget to add constraints to these UI.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_12.png)

13.  Go to AddFoodActivity.java file, add the following code to get the reference to the widgets created in the
     xml file.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_13.png)

14.  Set an onClickListenerfor the button. In the onClickevent, get the value of the of the EditTexts, and
     create the food, then use Intent to send the new created food data back to last Activity. However, notice there
     is an error on putExtramethod.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_14.png)

15.  This is because, the object you create must implements Serializable interface in order to be put in the
     Intent object. Go to Food.java file, and let it implements Serializable interface. Then the error will go away.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_15.png)

16.  Then go to MainAcitivity.java file, add the following code to start the AddFoodActivity, to get the food
     data.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_16.png)

17.  Then override the onActivityResultmethod, get the data sent back, and add it to the Adapter.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_17.png)

18.  Run the App, click on Add Button, then enter some food information, and click on Finish. The food will
     be added.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_18.png)

19.  Change the following code in MyRecyclerViewAdapterclass to make the insertion animatable. However
     it may not be very evident since it is added to the last one of the Recycler View, and the animation to close
     the AddFoodActivitywill overlap some of the animation here. But don’t worry, we can feel more animation
     effects when delete the item.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_19.png)

20.  Now it is the time to do the deletion function. Go to MyRecyclerViewAdapter.java file, add a deleteFood
     method to remove last object in food list, then call notifyDataSetChangedmethod.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_20.png)

21.  Go to menu_mail.xml file, add another Menu Item, set ID to action_delete, set title to Delete, and set
     showAsActionto always.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_21.png)

22.  Go to MainActivity.java file, make a call to deleteFoodmethod on the Adapter with the following code.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_22.png)

23.  Run the App, and click on Delete Button, the last item will be deleted.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_23.png)

24.  Go to MyRecyclerViewAdapter.java file, and make the change on the deleteFoodmethod to see some
     animations.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_24.png)

     Note: the animation may not be too much when deleting the last item. To see more effect, try to delete the last
     second item with the following changes in the code.

     ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView%20Example%202/img_25.png)