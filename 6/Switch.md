## Switch

### overview

1. A **Switch** is a two-state toggle switch widget that can select between two options.

2. **Usage**

   ```java
   import android.widget.Switch;
   ```

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/switch_1.png" alt="switch_1" style="zoom:67%;" />

### XML Attributes

1. Inherited XML attributes

   • From class android.widget.CompoundButton 

   • From class android.widget.TextView 

   • From class android.view.View

2. Whether to draw on/off text.

   • android:showText

3. Text to use when the switch is in the unchecked/"off" state.

   • android:textOff

4. Text to use when the switch is in the checked/"on" state.

   • android:textOn

5. [https://developer.android.com/reference/android/widget/Switch#xml-attributes_1](https://developer.android.com/reference/android/widget/Switch)

### Methods

1. Inherited methods

   • From class android.widget.Button

   • From class android.widget.TextView

   • From class android.view.View

   • From class android.widget.CompoundButton

   • From interface android.view.KeyEvent.Callback

2. [https://developer.android.com/reference/android/widget/Switch#inherited-methods](https://developer.android.com/reference/android/widget/Switch)

3. The current checked state of the view.

   ```java
   boolean isChecked();
   ```

4. Change the checked state of the view.

   ```java
   void setChecked(boolean checked);
   ```

5. Change the checked state of the view to the inverse of its current state.

   ```java
   void toggle();
   ```

6. Sets the text displayed when the button is in the checked state.

   ```java
   void setTextOn(CharSequence textOn);
   ```

7. Returns the text displayed when the button is in the checked state.

   ```java
   charSequence getTextOn();
   ```

8. Sets the text displayed when the button is not in the checked state.

   ```java
   void setTextOff(CharSequence textOff);
   ```

9. Returns the text displayed when the button is not in the checked state.

   ```java
   charSequence getTextOff();
   ```

10. Register a callback to be invoked when the checked state of this button changes.

    ```java
    void setOnCheckedChangeListener(CompoundButton.OnCheckedChangeListener listener);
    ```

### Example: On/Off

```java
public class MainActivity extends AppCompatActivity {

    private Switch exampleSwitch;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        exampleSwitch = findViewById(R.id.switch_example);
        if (exampleSwitch.isChecked()) {
            // Switch is on
        } else {
            // Switch is off
        }
    }

}

```

### Example: onCheckedChangedListener

```java
public class MainActivity extends AppCompatActivity {

    private Switch exampleSwitch;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        exampleSwitch = findViewById(R.id.switch_example);
        exampleSwitch.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {
                if (isChecked) {
                    // Switch is on
                } else {
                    // Switch is off
                }
            }
        });
    }

}
```

