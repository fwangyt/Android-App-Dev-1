## Multiple Activities and Intents



### Multiple Activities

#### 1.1 Activity Overview

-   Recall: an Activity represents a single screen with a user interface.

-   Real-world Android apps are multiple activities app.

-   Example: 3 activities to a simple user account management.
    -   Login screen
    -   Signup screen
    -   Reset password screen



#### 1.2 Create a New Activity

-   In the Project window, right-click the app folder and select New > Activity > Empty Activity. 

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/Multiple%20Activities%20and%20Intents/img_01.png" alt="Img_01" style="zoom:67%;" />

-   In the Configure Activity window, enter Activity Name. Leave all other properties set to their defaults and click Finish.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/Multiple%20Activities%20and%20Intents/img_02.png" style="zoom:67%;" />

-   Android Studio automatically does three things: Creates the nameActivityfile. Creates the layout file activity_name.xml, which corresponds with the nameActivityfile. Adds the required <activity> element in AndroidManifest.xml.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/10/Multiple%20Activities%20and%20Intents/img_03.png" alt="Img_03" style="zoom:67%;" />



### Intent

An Intent is an object that provides runtime binding between separate components. Its most significant use is in the launching of activities, where it can be thought of as the glue between activities. It is basically a passive data structure holding an abstract description of an action to be performed.



#### 1.1 Forms

-   **Explicit Intents** have specified a component (via `setComponent(ComponentName)` or `setClass(Context, Class)`), which provides the exact class to be run. Often these will not include any other information, simply being a way for an application to launch various internal activities it has as the user interacts with the application.

    ``` java
    // 1. Create an intent by its constrctor
    Intent intent = new Intent(this, SecondActivity.class);  
    startActivity(intent);
    ```

    ``` java
    // 2. setComponent method
    Intent intent = new Intent();    
    intent.setClass(this, SecondActivity.class);          
    startActivity(intent); 
    ```

    ``` java
    // 3. setClass / setClassName
    Intent intent = new Intent();    
    intent.setClass(this, SecondActivity.class);  
    //	intent.setClassName(this, "com.example.app.SecondActivity");  
    //	intent.setClassName(this.getPackageName(),"com.example.app.SecondActivity");            
    startActivity(intent); 
    ```

    

- **Implicit Intents** have not specified a component; instead, they must include enough information for the system to determine which of the available components is best to run for that intent.

  Using ``` <intent-filter> ``` to set intent in ``` AndroidManifest.xml ```.

  ```xml
  <activity  
      android:name="com.example.app.SecondActivity">  
      <intent-filter>  
          <action android:name="com.example.app.IT4410"/>  
          <category android:name="android.intent.category.DEFAULT"/>  
      </intent-filter>  
  </activity>  
  ```

  ``` java
  // 1. call setAction method
  Intent intent = new Intent();  
  intent.setAction("com.example.app.IT4410");  
  startActivity(intent);  
  ```

  ``` java
  // 2. call constrctor
  Intent intent = new Intent("com.example.app.IT4410");  
  startActivity(intent);  
  ```



#### 1.2 Structure

Again, an Intent provides a facility for performing late runtime binding between the code in different applications. Its most significant use is in the launching of activities, where it can be thought of as the glue between activities. It is basically a passive data structure holding an abstract description of an action to be performed.

- **action/data pair**

  - **action** -- The general action to be performed.
  - **data** -- The data to operate on

  For example, create an intent with a given action and for a given data url.

  ``` java
  // action - String: The Intent action, such as ACTION_VIEW.
  // Uri: The Intent data URI.
  public Intent (String action, 
                 Uri uri)
  ```

- **secondary attributes**

  - **category** -- Gives additional information about the action to execute.
  - **type** -- Specifies an explicit type (a MIME type) of the intent data.
  - **component** -- Specifies an explicit name of a component class to use for the intent
  - **extras** -- This is a `Bundle` of any additional information.



#### 1.3 Usage

- Dial & Call

```dart
// dial 573-123-4567
Uri uri = Uri.parse("tel:5731234567");
Intent intent = new Intent(Intent.ACTION_DIAL, uri);
startActivity(intent);
```

```java
// call 573-123-4567, with permission <uses-permission id="android.permission.CALL_PHONE" /> 
Uri callUri = Uri.parse("tel:10010"); 
Intent intent = new Intent(Intent.ACTION_CALL, callUri); 
```



- Text Message

```dart
 // Text to 5731234567 with "Hello"
Uri uri = Uri.parse("smsto:5731234567");
Intent intent = new Intent(Intent.ACTION_SENDTO, uri);
intent.putExtra("sms_body", "Hello");
startActivity(intent);
```

```dart
// with attached the image
Intent intent = new Intent(Intent.ACTION_SEND);
intent.putExtra("sms_body", "Hello");
Uri uri = Uri.parse("content://media/external/images/media/23");
intent.putExtra(Intent.EXTRA_STREAM, uri);
intent.setType("image/png");
startActivity(intent);
```



- Open URL in the browser

```dart
// Open Google
Uri uri = Uri.parse("https://www.google.com");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```



- Email

```dart
// Send Email
Uri uri = Uri.parse("mailto:IT4410@mizzou.com");
Intent intent = new Intent(Intent.ACTION_SENDTO, uri);
startActivity(intent);
```

```cpp
// Send Email with text "Hello"
Intent intent = new Intent(Intent.ACTION_SEND);
intent.putExtra(Intent.EXTRA_EMAIL, "IT4410@mizzou.com");
intent.putExtra(Intent.EXTRA_SUBJECT, "Subject");
intent.putExtra(Intent.EXTRA_TEXT, "Hello");
intent.setType("text/plain");
startActivity(intent);
```

```dart
// Send multiple emails at once
Intent intent=new Intent(Intent.ACTION_SEND);
String[] tos = {"1@abc.com", "2@abc.com"}; // To
String[] ccs = {"3@abc.com", "4@abc.com"}; // Cc
String[] bccs = {"5@abc.com", "6@abc.com"}; // Bcc
intent.putExtra(Intent.EXTRA_EMAIL, tos);
intent.putExtra(Intent.EXTRA_CC, ccs);
intent.putExtra(Intent.EXTRA_BCC, bccs);
intent.putExtra(Intent.EXTRA_SUBJECT, "Subject");
intent.putExtra(Intent.EXTRA_TEXT, "Hello");
intent.setType("message/rfc822");
startActivity(intent);
```



- Map

```dart
 // Open Google map with coordinate (139.9, 16.3)
Uri uri = Uri.parse("geo:139.9,16.3");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```

```dart
// route planning: from (139.9, 16.3) to (131.2, 21.4)
Uri uri = Uri.parse("http://maps.google.com/maps?f=d&saddr=139.9 16.3&daddr=131.2 21.4");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```



- Media

```dart
Intent intent = new Intent(Intent.ACTION_VIEW);
Uri uri = Uri.parse("file:///sdcard/foo.mp3");
intent.setDataAndType(uri, "audio/mp3");
startActivity(intent);

Uri uri = Uri.withAppendedPath(MediaStore.Audio.Media.INTERNAL_CONTENT_URI, "1");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```



- Photo

```cpp
Intent intent = new Intent(Intent.ACTION_GET_CONTENT);
intent.setType("image/*");
startActivityForResult(intent, 2);
```



- Capture

```cpp
Intent intent = new Intent(MediaStore.ACTION_IMAGE_CAPTURE);
startActivityForResult(intent, 1);
```

```csharp
Bundle extras = intent.getExtras();
Bitmap bitmap = (Bitmap) extras.get("data");
```



- Edit Photo

```dart
Intent intent = new Intent(Intent.ACTION_GET_CONTENT);
intent.setType("image/*");
intent.putExtra("crop", "true");
intent.putExtra("aspectX", 1); 
intent.putExtra("aspectY", 2);
intent.putExtra("outputX", 20);
intent.putExtra("outputY", 40);
intent.putExtra("output", Uri.fromFile(new File("/mnt/sdcard/temp"))); 
intent.putExtra("outputFormat", "JPEG");
startActivityForResult(intent, 0);
```

```dart
Intent intent = new Intent("com.android.camera.action.CROP");
intent.setClassName("com.android.camera", "com.android.camera.CropImage");
intent.setData(Uri.fromFile(new File("/mnt/sdcard/temp")));
intent.putExtra("outputX", 1); 
intent.putExtra("outputY", 2);
intent.putExtra("aspectX", 20);
intent.putExtra("aspectY", 40);
intent.putExtra("scale", true);
intent.putExtra("noFaceDetection", true);
intent.putExtra("output", Uri.parse("file:///mnt/sdcard/temp"));
startActivityForResult(intent, 0);
```



- Install app

```dart
String fileName = Environment.getExternalStorageDirectory() + "/myApp.apk";   
Intent intent = new Intent(Intent.ACTION_VIEW);   
intent.setDataAndType(Uri.fromFile(new File(fileName)),
"application/vnd.android.package-archive");   
startActivity(intent);  
```



- Uninstall app

```dart
Uri uri = Uri.parse("package:" + packageName);   
Intent intent = new Intent(Intent.ACTION_DELETE, uri);
startActivity(intent);
```



- Go to settings

```cpp
Intent intent = new Intent(android.provider.Settings.ACTION_SETTINGS);
startActivity(intent);
```