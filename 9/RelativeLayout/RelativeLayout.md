##  RelativeLayout



### Overview

**RelativeLayout:** is a view group that displays child views in relative positions. The position of each view can be specified as relative to sibling elements (such as to the left-of or below another view) or in positions relative to the parent RelativeLayoutarea (such as aligned to the bottom, left or center).

![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayout/img_01.png)

### Create

-   Change the default root layout to RelativeLayout

-   Edit XML directly.

    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayout/img_02.png)

-   Use layout editor to convert view
    
    -   Component Tree -> right click on ConstraintLayout
    
    ![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayout/img_03.png)

### Positioning

**RelativeLayout** lets child views specify their position relative to the parent view or to each other (specified by ID). So you can align two elements by right border, or make one below another, centered in the screen, centered left, and so on. By default, all child views are drawn at the top-left of the layout, so you must define the position of each view using the various layout properties available from RelativeLayout.LayoutParams.

**Positioning parameters**

| XML attributes                                               |                                                              |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| [`android:layout_above`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_above) | Positions the bottom edge of this view above the given anchor view ID. |
| [`android:layout_alignBaseline`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignBaseline) | Positions the baseline of this view on the baseline of the given anchor view ID. |
| [`android:layout_alignBottom`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignBottom) | Makes the bottom edge of this view match the bottom edge of the given anchor view ID. |
| [`android:layout_alignEnd`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignEnd) | Makes the end edge of this view match the end edge of the given anchor view ID. |
| [`android:layout_alignLeft`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignLeft) | Makes the left edge of this view match the left edge of the given anchor view ID. |
| [`android:layout_alignParentBottom`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignParentBottom) | If true, makes the bottom edge of this view match the bottom edge of the parent. |
| [`android:layout_alignParentEnd`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignParentEnd) | If true, makes the end edge of this view match the end edge of the parent. |
| [`android:layout_alignParentLeft`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignParentLeft) | If true, makes the left edge of this view match the left edge of the parent. |
| [`android:layout_alignParentRight`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignParentRight) | If true, makes the right edge of this view match the right edge of the parent. |
| [`android:layout_alignParentStart`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignParentStart) | If true, makes the start edge of this view match the start edge of the parent. |
| [`android:layout_alignParentTop`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignParentTop) | If true, makes the top edge of this view match the top edge of the parent. |
| [`android:layout_alignRight`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignRight) | Makes the right edge of this view match the right edge of the given anchor view ID. |
| [`android:layout_alignStart`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignStart) | Makes the start edge of this view match the start edge of the given anchor view ID. |
| [`android:layout_alignTop`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignTop) | Makes the top edge of this view match the top edge of the given anchor view ID. |
| [`android:layout_alignWithParentIfMissing`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_alignWithParentIfMissing) | If set to true, the parent will be used as the anchor when the anchor cannot be be found for layout_toLeftOf, layout_toRightOf, etc. |
| [`android:layout_below`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_below) | Positions the top edge of this view below the given anchor view ID. |
| [`android:layout_centerHorizontal`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_centerHorizontal) | If true, centers this child horizontally within its parent.  |
| [`android:layout_centerInParent`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_centerInParent) | If true, centers this child horizontally and vertically within its parent. |
| [`android:layout_centerVertical`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_centerVertical) | If true, centers this child vertically within its parent.    |
| [`android:layout_toEndOf`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_toEndOf) | Positions the start edge of this view to the end of the given anchor view ID. |
| [`android:layout_toLeftOf`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_toLeftOf) | Positions the right edge of this view to the left of the given anchor view ID. |
| [`android:layout_toRightOf`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_toRightOf) | Positions the left edge of this view to the right of the given anchor view ID. |
| [`android:layout_toStartOf`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams#attr_android:layout_toStartOf) | Positions the end edge of this view to the start of the given anchor view ID. |



### XML attributes

-   Inherited XML attributes from 
    -   class android.view.View
    -   class android.view.ViewGroup
-   android:gravity
    -   Specifies how an object should position its content, on both the X and Y axes, within its own bounds.
-   android:ignoreGravity
    -   Indicates what view should not be affected by gravity.
-   https://developer.android.com/reference/android/widget/RelativeLayout#inherited-xml-attributes



### Inherited methods

-   Fromclass android.view.View

-   Fromclass android.view.ViewGroup

-   Fromclass java.lang.Object

-   Frominterface android.view.ViewParent

-   Frominterface android.view.ViewManager

-   Frominterface android.graphics.drawable.Drawable.Callback

-   Frominterface android.view.KeyEvent.Callback

-   Frominterface android.view.accessibility.AccessibilityEventSource



### Methods

-   Describes how the child views are positioned.

    ``` java
    void setGravity (int gravity)
    ```

-   Describes how the child views are positioned horizontally.

    ``` java
    void setHorizontalGravity (int horizontalGravity)
    ```

-   Describes how the child views are positioned vertically.

    ``` java
    void setVerticalGravity (int verticalGravity)
    ```

-   https://developer.android.com/reference/android/widget/RelativeLayout#public-methods



