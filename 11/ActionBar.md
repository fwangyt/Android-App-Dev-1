## ActionBar

### Overview

- A primary toolbar within the activity that may display the activity title, application-level navigation affordances, and other interactive items.

- Usage

  ```java
  import android.support.v7.app.ActionBar;
  ```

  <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/11/images/action_bar_1.png" alt="action_bar_1" style="zoom: 60%;" />

- The app bar, also known as the action bar, is one of the most important design elements in your app's activities, because it provides a visual structure and interactive elements that are familiar to users. Using the app bar makes your app consistent with other Android apps, allowing users to quickly understand how to operate your app and have a great experience. The key functions of the app bar are as follows: 

  - A dedicated space for giving your app an identity and indicating the user's location in the app. 
  - Access to important actions in a predictable way, such as search. 
  - Support for navigation and view switching (with tabs or drop-down lists).

- When you create an Activity from a template (such as Empty Template), an app bar is automatically included for the Activity.

- Each activity that uses the default theme also has an ActionBar as its app bar. Some themes also set up an ActionBar as an app bar by default. When you start an app from a template such as Empty Activity, an ActionBar appears as the app bar.

- Default ActionBar location

  - Project -> res -> value -> styles.xml

### Methods

- Retrieve the current height of the ActionBar.

  ```java
  abstract int getHeight();
  ```

- Returns the current ActionBar subtitle in standard mode.

  ```java
  abstract CharSequence getSubtitle();
  ```

- Returns a Context with an appropriate theme for creating views that will appear in the action bar.\

  ```java
  Context getThemedContext();
  ```

- Return whether the action bar is configured to scroll out of sight along with a nested scrolling child.

  ```java
  boolean isHideOnContentScrollEnabled();
  ```

- True if the ActionBar is showing, false otherwise.

  ```java
  abstract boolean isShowing();
  ```

- Set the action bar's title.

  ```java
  abstract void setTitle(CharSequence title);
  ```

- Show the ActionBar if it is not currently showing.

  ```java
  abstract void show();
  ```

- Hide the ActionBar if it is currently showing.

  ```java
  abstract void hide();
  ```

- Set the ActionBar's background.

  ```java
  abstract void setBackgroundDrawable(Drawable d);
  ```

- Set the icon to display in the 'home' section of the action bar.

  ```java
  abstract void setIcon(int resId);
  ```

- Set the logo to display in the 'home' section of the action bar.

  ```java
  abstract void setLogo(int resId);
  ```

- Set the action bar's subtitle.

  ```java
  abstract void setSubtitle(CharSequence subtitle);
  ```

- •[https://developer.android.com/reference/android/support/v7/app/ActionBar#public-methods](https://developer.android.com/reference/android/support/v7/app/ActionBar)

