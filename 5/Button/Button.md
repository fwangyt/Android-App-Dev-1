## Button

Button is a user interface element the user can tap or click to perform an action.

In Android, button is a button-like view. Its inheritance structure: 

``` java.lang.Object ```

​	↳	```android.view.View ```

​		↳	```android.widget.TextView ```

​			↳	```android.widget.Button```



### Usage

```java
import android.widget.Button;
```



#### Layout Editor

Palette window / Buttons / Button

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/Button/img_1.png" style="zoom:50%;" />

#### XML

``` xml
<Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button"
        tools:layout_editor_absoluteX="161dp"
        tools:layout_editor_absoluteY="341dp" />
```



#### Click Events

##### onClick

Declare  ```android:onClick```  attribut in XML. For example: 

```xml
 <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button"
        tools:layout_editor_absoluteX="161dp"
        tools:layout_editor_absoluteY="341dp"
        android:onClick="clickMe"/>
```

And declare the corresponding method in the activity file.

``` java
		private Button btn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        btn = findViewById(R.id.button);
    }

    public void clickMe(View view) {

        Log.i("Tag","Clicking!!!");
    }
```



##### OnClickListener

Declare the click event handler in the activity file.

``` java
		private Button btn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        btn = findViewById(R.id.button);
        btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                Log.i("click","Yes");
            }
        });

        btn.setOnLongClickListener(new View.OnLongClickListener() {
            @Override
            public boolean onLongClick(View view) {

                Log.i("long click", "Yes");
                return false;
            }
        });
    }
```



