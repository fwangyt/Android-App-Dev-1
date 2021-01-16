## ImageView

### Overview

1. Displays image resources, for example Bitmap or Drawable resources. 

2. **Usage**

   ```java
   import android.widget.ImageView;
   ```
   
   <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/image_view_1.png" alt="image_view_1" style="zoom:80%;" />

### Create

1. Layout Editor
   
- Palette window -> Widgets -> ImageView
  
2. Write XML

   ```xml
   <ImageView />
   ```

3. Through Java code

   ```java
   •ImageView(Context context)
   •ImageView(Context context, AttributeSet attrs)
   •...
   ```

### XML Attributes

1. Inherited XML attributes from class android.view.View.
2. Set this to true if you want the ImageView to adjust its bounds to preserve the aspect ratio of its drawable.
   - android:adjustViewBounds
3. Controls how the image should be resized or moved to match the size of this ImageView.
   - android:scaleType
4. Sets a drawable as the content of this ImageView.
   - android:src
5. If true, the image will be cropped to fit within its padding.
   - android:cropToPadding
6. The offset of the baseline within this view.
   - android:baseline
7. If true, the image view will be baseline aligned with based on its bottom edge.
   - android:baselineAlignBottom
8. [https://developer.android.com/reference/android/widget/ImageView#xml-attributes_1](https://developer.android.com/reference/android/widget/ImageView)

### Inherited methods

- From class android.view.View
- From class java.lang.Object 
- From interface android.graphics.drawable.Drawable.Callback 
- From interface android.view.KeyEvent.Callback 
- From interface android.view.accessibility.AccessibilityEventSource

### Methods

1. Sets a drawable as the content of this ImageView.

   ```java
   public void setImageResource(int resId);
   ```

2. Controls how the image should be resized or moved to match the size of this ImageView.

   ```java
   public void setScaleType(ImageView.ScaleType scaleType);
   ```

3. Set the visibility state of this view.

   ```java
   public void setVisibility(int visibility);
   ```

4. True when ImageView is adjusting its bounds to preserve the aspect ratio of its drawable.

   ```java
   public boolean getAdjustViewBounds();
   ```

5. [https://developer.android.com/reference/android/widget/ImageView#public-methods_1](https://developer.android.com/reference/android/widget/ImageView)

### ScaleType

1. **ScaleType** is a nested enum type class of class ImageView, which offers options for scaling the bounds of an image to the bounds of this view.

2. Enum values

   - CENTER
     - Center the image in the view, but perform no scaling.

   - CENTER_CROP
     - Scale the image uniformly (maintain the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the view (minus padding).

   - CENTER_INSIDE
     - Scale the image uniformly (maintain the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or less than the corresponding dimension of the view (minus padding).

3. [https://developer.android.com/reference/android/widget/ImageView.ScaleType.html](https://developer.android.com/reference/android/widget/ImageView.ScaleType.html)
