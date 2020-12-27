## TextView and EditText

TextView is a user interface element that displays text to the user. 

EditText is a user interface element for entering and modifying text.

In Android, they are text-related views.

```java.lang.Object ```

​	↳	```android.view.View ```

​		↳	```android.widget.TextView```



```java.lang.Object```

 	↳	```android.view.View ```

​		↳	```android.widget.TextView ```

​			↳	```android.widget.EditText```



### Usage

```java
import import android.widget.TextView;
```



#### Layout Editor

Palette window / Text / TextView

Palette window / Text / Plain Text

<img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/5/TextView%20and%20EditText/img_1.png" style="zoom:50%;" />

#### XML

``` xml
<TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="TextView"
        tools:layout_editor_absoluteX="161dp"
        tools:layout_editor_absoluteY="334dp" />
```

``` xml
<EditText
        android:id="@+id/editTextTextPersonName"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="Name"
        tools:layout_editor_absoluteX="85dp"
        tools:layout_editor_absoluteY="266dp" />
```



#### TextWatcher

When an object of this type is attached to an Editable, its methods will be called when the text is changed.

``` java
abstract void afterTextChanged(Editable s);
// This method is called to notify you that, somewhere within s, the text has been changed.

abstract void beforeTextChanged(CharSequence s, int start, int count, int after);
// This method is called to notify you that, within s, the count characters beginning at start are about to be replaced by new text with length after.

abstract void onTextChanged(CharSequence s, int start, int before, int count);
// This method is called to notify you that, within s, the count characters beginning at start have just replaced old text that had length before.
```



##### Add TextWatcher On EditText

``` java
editText.addTextChangedListener(new TextWatcher() {
		@Override
		public void beforeTextChanged(CharSequence charSequence, int i, int i1, int i2) {
				Log.i("beforeTextChanged", "YES");
		}

		@Override
		public void onTextChanged(CharSequence charSequence, int i, int i1, int i2) {
				Log.i("onTextChanged", "YES");
    }

  	@Override
		public void afterTextChanged(Editable editable) {
				Log.i("afterTextChanged", "YES");
		}
});
```

