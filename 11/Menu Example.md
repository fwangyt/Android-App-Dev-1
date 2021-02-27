## Menu Example

### Menu

- The Menu (also referred to as the options menu) is a menu that is accessible to the user from the device display and allows the developer to include other application options beyond those included in the user interface of the application.
- The location of the Menu is dependent upon the version of Android that is running on the device.
- With the Android 4.0 release and later, the Menu button is located in the top right-hand corner in the action toolbar represented by the stack of three squares.

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_1.png" alt="menu_example_1" style="zoom: 40%;" />

### Creating Menu

- The items in a menu can be declared within an XML file, which is then inflated and displayed to the user on demand.

- This involves the use of the <menu> element, containing an <item> sub-element for each menu item.

- The following XML, for example, defines a menu consisting of two menu items relating to color choices:

  ```xml
  <menu xmlns:android="http://schemas.android.com/apk/res/android"
  xmlns:app="http://schemas.android.com/apk/res-auto"
  xmlns:tools="http://schemas.android.com/tools"
  tools:context=".MainActivity">
      <item
          android:id="@+id/menu_red"
          android:orderInCategory="1"
          app:showAsAction="never"
          android:title="RED" />
      <item
          android:id="@+id/menu_green"
          android:orderInCategory="2"
          app:showAsAction="never"
          android:title="GREEN" />
  </menu>
  ```

- In the previous XML, the title property controls what text will be displayed on the menu item.

- The android:orderInCategory property dictates the order in which the menu items will appear within the menu when it is displayed. The item will smaller value will display first. This property should be set to the integer values, but may not be continuous. For example, setting this value for menu items to 1, 2, 5, 8… is fine.

- The app:showAsAction property, on the other hand, controls the conditions under which the corresponding item appears as an item within the action bar itself.

- If set to *never*, the item will be put in the drop-down list.

- If set to *ifRoom*, the item will appear in the action bar if there is enough room.

- The following for example shows the effect of setting this property to *ifRoom* for both menu items:

  ```xml
  <menu>
      <item
          android:id="@+id/menu_red"
          android:orderInCategory="1"
          app:showAsAction="ifRoom"
          android:title="RED" />
      <item
          android:id="@+id/menu_green"
          android:orderInCategory="2"
          app:showAsAction="ifRoom"
          android:title="GREEN" />
  </menu>
  ```

  <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_2.png" alt="menu_example_2" style="zoom:35%;" />

### Displaying Menu

- An Menu is created by overriding the *onCreateOptionsMenu**()* method of the corresponding activity and then inflating the menu’s XML file. For example, the following code creates the menu contained within a menu XML file named *menu_main*:

  ```java
  @Override
  public boolean onCreateOptionsMenu(Menu menu) {
      getMenuInflater().inflate(R.menu.menu_main, menu);
      return true;
  }
  ```

- As with the menu XML file, Android Studio will already have overridden this method in the main activity of a newly created Android application project. In the event that an Menu is not required in your activity, either remove or comment out this method.

### Responding to Menu Item Selections

- Once a menu has been implemented, the question arises as to how the application receives notification when the user makes menu item selections.

- All that an activity needs to do to receive menu selection notifications is to override the *onOptionsItemSelected()* method.

- Passed as an argument to this method is a reference to the selected menu item. The *getItemId**()* method may then be called on the item to obtain the ID which may, in turn, be used to identify which item was selected. 

  ```java
  @Override
  public boolean onOptionsItemSelected(MenuItem item) {
  	switch (item.getItemId()) {
  	case R.id.menu_red:
          // Red item was selected
          return true;
  	case R.id.menu_green:
          // Green item was selected
          return true;
  	default:
  		return super.onOptionsItemSelected(item);
  	}
  }
  ```

### Example

1. Create an Android Studio project with Empty Activity, and name it OptionsMenuExample.

2. Right click on app or res folder, go to New, then select Android Resource File.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_3.png" alt="menu_example_3" style="zoom: 67%;" />

3. In the New Resource File dialog, enter File name as nemu_main, and change Resource type to Menu. Then click on OK button, the menu resource file will be created. 

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_4.png" alt="menu_example_4" style="zoom: 67%;" />

4. Add the following code to menu_main.xml file.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_5.png" alt="menu_example_5" style="zoom: 67%;" />

5. Go to MainActivity.java file, and add the following code.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_6.png" alt="menu_example_6" style="zoom: 50%;" />

6. Run the App, and click on the top-right 3 dots, it will display as following.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_7.png" alt="menu_example_7" style="zoom: 60%;" />

7. Go to activity_main.xml file, and set the ID to result_tv for the existing TextView.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_8.png" alt="menu_example_8" style="zoom: 67%;" />

8. Go to MainActivity.java file, and add the following code.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_9.png" alt="menu_example_9" style="zoom: 50%;" />

9. Run the App again, click on each menu item, the text on TextView will be changed.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/menu_example_10.png" alt="menu_example_10" style="zoom:60%;" />