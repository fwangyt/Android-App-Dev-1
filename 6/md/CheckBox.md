## CheckBox

### overview

1. A **CheckBox** is a specific type of two-states button that can be either checked or unchecked.

2. **Usage**

   ```java
   import android.widget.CheckBox;
   ```

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/check_box_1.png" alt="check_box_1" style="zoom:67%;" />

### Create

1. Layout Editor

   Palette window -> Buttons -> CheckBox

2. Write XML

   ```xml
   <CheckBox
       android:id="@+id/checkbox_example“
       android:... />
   ```

### XML Attributes

1. Inherited XML attributes

   • From class android.widget.CompoundButton 

   • From class android.widget.TextView 

   • From class android.view.View

2. [https://developer.android.com/reference/android/widget/CheckBox#inherited-xml-attributes](https://developer.android.com/reference/android/widget/CheckBox)

### Methods

1. Get current checked state of the view.

   ```java
   boolean isChecked();
   ```

2. Change the checked state of the view.

   ```java
   void setChecked(boolean checked);
   ```

3. Change the checked state of the view to the inverse of its current state.

   ```java
   void toggle();
   ```

4. Register a callback to be invoked when the checked state of this button changes.

   ```java
   void setOnCheckedChangeListener(CompoundButton.OnCheckedChangeListener listener);
   ```

5. More...

### Example: Checked/Unchecked

```java
public class MainActivity extends AppCompatActivity {

    private CheckBox exampleCheckBox;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        exampleCheckBox = findViewById(R.id.check_box_example);
        if (exampleCheckBox.isChecked()) {
            // CheckBox is checked
        } else {
            // CheckBox is unchecked
        }
    }

}
```

### Example: OnCheckedChangeListener

```java
public class MainActivity extends AppCompatActivity {

    private CheckBox exampleCheckBox;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        exampleCheckBox = findViewById(R.id.check_box_example);
        exampleCheckBox.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {
                if (isChecked) {
                    // CheckBox is checked
                } else {
                    // CheckBox is unchecked
                }
            }
        });
    }

}
```

