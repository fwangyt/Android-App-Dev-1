## RadioButton **and** RadioGroup

### Overview

#### RadioButton

1. **RadioButton** allows the user to select one option. 

2. **Usage**

   ```java
   import android.widget.RadioButton;
   ```

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_button_1.png" alt="radio_button_1" style="zoom:67%;" />

#### RadioGroup

1. **RadioGroup** is used to create a multiple-exclusion scope for a set of radio buttons. Checking one radio button that belongs to a radio group unchecks any previously checked radio button within the same group. 

2. **Usage**

   ```java
   import android.widget.RadioButton;
   ```

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_button_2.png" alt="radio_button_2" style="zoom:67%;" />

### Create

#### RadioButton

1. Layout Editor

   Palette window -> Buttons -> RadioButton

2. Write XML

   ```xml
   <RadioButton />
   ```

#### RadioGroup

1. Layout Editor

   • Palette window -> Buttons -> RadioGroup

   • Palette window -> Buttons -> RadioButton

   ​	• Dragging into the Component Tree under the RadioGroup.

   <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/radio_button_3.png" alt="radio_button_3" style="zoom: 50%;" />

2. Write XML

   ```xml
   <RadioGroup />
       <RadioButton />
       <RadioButton />
       ...
   </RadioGroup />
   ```

### XML Attributes

#### RadioGroup

1. id
2. text
3. *checkedButton*
4. alpha
5. ...
6. 

#### RadioButton

1. id
2. text
3. style
4. *checked*
5. textSize
6. textColor
7. textAlignment
8. ...

### Methods

#### RadioGroup

1. Inherited methods

   • From class android.view.View

   • From interface android.view.KeyEvent.Callback

   • ...

2. Sets the selection to the radio button whose identifier is passed in parameter.

   ```java
   void check(int id);
   ```

3. Clears the selection.

   ```java
   void clearCheck();
   ```

4. Returns the identifier of the selected radio button in this group.

   ```java
   int getCheckedRadioButtonId();
   ```

5. Register a callback to be invoked when the checked radio button changes in this group.

   ```java
   void setOnCheckedChangeListener(RadioGroup.OnCheckedChangeListener listener);
   ```

6. Interface definition for a callback to be invoked when the checked state of a compound button changed. Called when the checked state of a compound button has changed.

   ```java
   /**
    * @param group the group in which the checked radio button has changed
    * @param checkedId the unique identifier of the newly checked radio button
    */
   abstract void onCheckedChanged(RadioGroup group, int checkedId);
   ```

7. [https://developer.android.com/reference/android/widget/RadioGroup#public-methods](https://developer.android.com/reference/android/widget/RadioGroup)

#### RadioButton

1. Inherited methods

   • From class android.view.View

   • From class android.widget.TextView

   • From class android.widget.Button

   • From interface android.graphics.drawable.Drawable.Callback

   • From interface android.view.KeyEvent.Callback

   • …

2. [https://developer.android.com/reference/android/widget/RadioButton.html#inherited-methods](https://developer.android.com/reference/android/widget/RadioButton.html)

### Example: OnCheckedChangeListener

```java
public class MainActivity extends AppCompatActivity {

    private RadioGroup exampleRadioGroup;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        exampleRadioGroup = findViewById(R.id.radio_group_example);
        exampleRadioGroup.setOnCheckedChangeListener(new RadioGroup.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(RadioGroup group, int checkedId) {
                switch (checkedId) {
                    case R.id.radio_button_1:
                        // Do somethings
                        break;
                    case R.id.radio_button_2:
                        // Do somethings
                        break;
                    case R.id.radio_button_3:
                        // Do somethings
                        break;
                }
            }
        });
    }

}
```

