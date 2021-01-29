### ScrollView

### Overview

- A view group that allows the view hierarchy placed within it to be scrolled.

- Usage:

  ```java
  import android.widget.ScrollView;
  ```

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/8/images/scroll_view_1.png" alt="scroll_view_1" style="zoom: 67%;" />

### Create

- Layout Editor
  
- Palette window -> Containers -> ScrollView
  
- Write XML

  ```xml
  <ScrollView>
  ...
  </ScrollView>
  ```

- Programmatically
  - ScrollView(Context context)
  - ScrollView(Context context, AttributeSet attrs)
  - ...

### XML attributes

- Inherited XML attributes 

  - From class android.view.View.

  - From class android.view.ViewGroup

  - From class android.widget.FrameLayout

- android:scrollbarStyle

  - Controls the scrollbar style and position. The scrollbars can be overlaid or inset. When inset, they add to the padding of the view. And the scrollbars can be drawn inside the padding area or on the edge of the view.
    - insideInset: Inside the padding and inset.
    - insideOverlay: Inside the padding and overlaid.
    - outsideInset: Edge of the view and inset.
    - outsideOverlay: Edge of the view and overlaid.

- android:clipToPadding

  - Defines whether the ViewGroup will clip its children and resize (but not clip) any EdgeEffect to its padding, if padding is not zero.

- android:fillViewport

  - Defines whether the scrollview should stretch its content to fill the viewport.

- ...

- [https://developer.android.com/reference/android/widget/ScrollView#inherited-xml-attributes](https://developer.android.com/reference/android/widget/ScrollView)

### Inherited methods

- From class android.view.View

- From class android.view.ViewGroup

- From class android.widget.FrameLayout

- From class java.lang.Object 

- From interface android.view.ViewParent 

- From interface android.view.ViewManager 
- From interface android.graphics.drawable.Drawable.Callback 
- From interface android.view.KeyEvent.Callback 
- From interface android.view.accessibility.AccessibilityEventSource

### Methods

- Fling the scroll view.

- ```java
  void fling(int velocityY);
  ```

- Handles scrolling in response to a "home/end" shortcut press.

  ```java
  boolean fullScroll(int direction);
  ```

- Indicates whether this ScrollView's content is stretched to fill the viewport.

  ```java
  boolean isFillViewport();
  ```

- Whether arrow scrolling will animate its transition.

  ```java
  boolean isSmoothScrollingEnabled();
  ```

- Handles scrolling in response to a "page up/down" shortcut press.

  ```java
  boolean pageScroll(int direction);
  ```

- Set the scrolled position of your view.

  ```java
  void scrollTo(int x, int y);
  ```

- Scrolls the view to the given child.

  ```java
  void scrollToDescendant(View child);
  ```

- Indicates this ScrollView whether it should stretch its content height to fill the viewport or not.

  ```java
  void setFillViewport(boolean fillViewport);
  ```

- Set whether arrow scrolling will animate its transition.

  ```java
  void setSmoothScrollingEnabled(boolean smoothScrollingEnabled);
  ```

- Like View#scrollBy, but scroll smoothly instead of immediately.

  ```java
  final void smoothScrollBy(int dx, int dy);
  ```

- Like scrollTo(int, int), but scroll smoothly instead of immediately.

  ```java
  final void smoothScrollTo(int x, int y);
  ```

- Compute the vertical offset of the vertical scrollbar's thumb within the horizontal range.

    ```java
int computeVerticalScrollOffset();
    ```

- The scroll range of a scroll view is the overall height of all of its children.

  ```java
  int computeVerticalScrollRange();
  ```

- •[https://developer.android.com/reference/android/widget/ScrollView#public-methods](https://developer.android.com/reference/android/widget/ScrollView)



