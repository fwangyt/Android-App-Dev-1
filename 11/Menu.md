## Menu

### Overview

- Interface for managing the items in a menu (app bar or ActionBar). 

- Usage

  ```java
  import android.view.Menu;
  ```

  <img src="C:\Users\LSY\Desktop\安卓课\安卓1\Android-App-Dev-1\11\images\menu_1.png" alt="menu_1" style="zoom:75%;" />

### Creation

- Defining a Menu in XML

  - right click on res directory

  - New -> Android Resources File

  - Enter the file name, select Resource type as Menu, and click on OK.

  <img src="C:\Users\LSY\Desktop\安卓课\安卓1\Android-App-Dev-1\11\images\menu_2.png" alt="menu_2" style="zoom: 67%;" />

- Add MenuItem to the Menu. MenuItem is an interface for direct access to a previously created menu item.

  - Drag and drop through palette window

  - Or write XML directly

  <img src="C:\Users\LSY\Desktop\安卓课\安卓1\Android-App-Dev-1\11\images\menu_3.png" alt="menu_3" style="zoom:67%;" />

- In the activity file (i.e. MainActivity.java), override onCreateOptionsMenu() method to specify the options menu for an activity. In this method, you can inflate your menu resource (defined in XML) into the Menu provided in the callback.

  <img src="C:\Users\LSY\Desktop\安卓课\安卓1\Android-App-Dev-1\11\images\menu_4.png" alt="menu_4" style="zoom: 70%;" />

### MenuItem: XML Attributes and Methods

- Sets how this item should display in the presence of an Action Bar.

  ```java
  abstract void setShowAsAction(int actionEnum);
  ```

- Sets whether the menu item is enabled. Disabling a menu item will not allow it to be invoked via its shortcut. The menu item will still be visible.

  ```java
  abstract MenuItem setEnabled (boolean enabled);
  ```

- Control whether this item can display a check mark.

  ```java
  abstract MenuItem setCheckable (boolean checkable);
  ```

- •[https://developer.android.com/reference/android/view/MenuItem#public-methods_1](https://developer.android.com/reference/android/view/MenuItem)

### Menu: Activity Callback Methods

- This hook is called whenever an item in your options menu is selected.

  ```java
  boolean onOptionsItemSelected(MenuItem item);
  ```

- This hook is called whenever the options menu is being closed (either by the user canceling the menu with the back/menu button, or when an item is selected).

  ```java
  void onOptionsMenuClosed(Menu menu);
  ```

- Initialize the contents of the Activity's standard options menu.

  ```java
  boolean onCreateOptionsMenu(Menu menu);
  ```

- Prepare the Screen's standard options menu to be displayed....

  ```java
  boolean onPrepareOptionsMenu(Menu menu);
  ```

- [https://developer.android.com/reference/android/app/Activity#public-methods](https://developer.android.com/reference/android/app/Activity)