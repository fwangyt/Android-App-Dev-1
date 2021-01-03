## AlertDialog

### Overview

1. **AlertDialog** is a dialog that can show a title, up to three buttons, a list of selectable items, or a custom layout.

2. **Usage**

   ```java
   import android.app.AlertDialog;
   import android.content.DialogInterface;
   ```

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/6/images/alert_dialog_1.png" alt="alert_dialog_1" style="zoom: 67%;" />

### AlertDialog.Builder

1. Use nested class **AlertDialog.Builder** to create new AlertDialog object.

2. Constructors

   1. Creates a builder for an alert dialog that uses an explicit theme resource.

      ```java
      AlertDialog.Builder(Context context, int themeResId);
      ```

   2. Creates a builder for an alert dialog that uses the default alert dialog theme.

      ```java
      AlertDialog.Builder(Context context);
      ```

3. [https://developer.android.com/reference/android/app/AlertDialog.Builder#top_of_page](https://developer.android.com/reference/android/app/AlertDialog.Builder)

### AlertDialog.Builder Methods

1. Creates an AlertDialog with the arguments supplied to this builder.

   ```java
   create();
   ```

2. Set a list of items to be displayed in the dialog as the content, you will be notified of the selected item via the supplied listener.

   ```java
   setItems(int itemsId, DialogInterface.OnClickListener listener);
   ```

3. Set a list of items to be displayed in the dialog as the content, you will be notified of the selected item via the supplied listener.

   ```java
   setItems(CharSequence[] items, DialogInterface.OnClickListener listener);
   ```

4. Set the message to display.

   ````java
   setMessage(CharSequence message);
   ````

5. Set the title displayed in the Dialog.

   ```java
   setTitle(CharSequence title);
   ```

6. Sets whether the dialog is cancelable or not.

   ```java
   setCancelable(boolean cancelable);
   ```

7. Set a listener to be invoked when the positive button of the dialog is pressed.

   ```java
   setPositiveButton(int textId, DialogInterface.OnClickListener listener);
   ```

8. Creates an AlertDialog with the arguments supplied to this builder and immediately displays the dialog.

   ```java
   show();
   ```

9. More...

### Create

```java
AlertDialog.Builder builder = new AlertDialog.Builder(this);
// Implement AlertDialog.Builder methods
AlertDialog alertDialog = builder.create(); 
alertDialog.show();
```

### Example with Title and Message

```java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        createAlertDialog();
    }

    private void createAlertDialog() {
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        // ************ Implement AlertDialog.Builder methods ************
        builder.setCancelable(true);
        builder.setTitle("IT4410 AlertDialog Example");
        builder.setMessage("AlertDialog with title and message");
        // ************ End ************
        AlertDialog alertDialog = builder.create();
        alertDialog.show();
    }

}
```

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/6/images/alert_dialog_2.png" alt="alert_dialog_2" style="zoom:67%;" />

### Example with Buttons

```java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        createAlertDialog();
    }

    private void createAlertDialog() {
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        // ************ Implement AlertDialog.Builder methods ************
        builder.setCancelable(true);
        builder.setTitle("IT4410 AlertDialog Example");
        builder.setMessage("AlertDialog example set buttons");
        builder.setNeutralButton("Neutral", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                dialog.cancel();
            }
        });
        builder.setNegativeButton("Negative", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                dialog.cancel();
            }
        });
        builder.setPositiveButton("Positive", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                dialog.cancel();
            }
        });
        // ************ End ************
        AlertDialog alertDialog = builder.create();
        alertDialog.show();
    }

}
```

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/6/images/alert_dialog_3.png" alt="alert_dialog_3" style="zoom:67%;" />