### LinearLayout

### Overview

A layout that arranges other views either **horizontally** in a single column or **vertically** in a single row.

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/8/images/linear_layout_1.png" alt="linear_layout_1" style="zoom:67%;" />

### Create

- The default root layout is ConstraintLayout

- To change the root layout to LinearLayout:
  - Find the *activity_name.xml* file.
  - Change ConstraintLayout to LinearLayout

<img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/8/images/linear_layout_2.png" alt="linear_layout_2" style="zoom: 67%;" />

- Or use layout editor to convert view

  - Component Tree -> right click on ConstraintLayout -> convert view…

    <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/8/images/linear_layout_3.png" alt="linear_layout_3" style="zoom: 67%;" />

### Orientation

- Set the layout be a column or a row

  - "horizontal" for a row

  - "vertical" for a column

- XML attributes: android:orientation

- Or use layout editor to convert the orientation

  <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/8/images/linear_layout_4.png" alt="linear_layout_4" style="zoom: 50%;" />

### Gravity

- Specifies how an object should position its content, on both the X and Y axes, within its own bounds.

- XML attribute: android:gravity

- Method

  ```java
  void setGravity(int);
  ```

  | Constant          | Value  | Description                                                  |
  | ----------------- | ------ | ------------------------------------------------------------ |
  | bottom            | 50     | Push object to the bottom of its container, not changing its size. |
  | center            | 11     | Place the object in the center of its container in both the vertical  and horizontal axis, not changing its size. |
  | center_horizontal | 1      | Place object in the horizontal center of its container, not changing  its size. |
  | center_vertical   | 10     | Place object in the vertical center of its container, not changing  its size. |
  | clip_horizontal   | 8      | Additional option that can be set to have the left and/or right edges  of the child clipped to its container's bounds. The clip will be based on the  horizontal gravity: a left gravity will clip the right edge, a right gravity  will clip the left edge, and neither will clip both edges. |
  | clip_vertical     | 80     | Additional option that can be set to have the top and/or bottom edges  of the child clipped to its container's bounds. The clip will be based on the  vertical gravity: a top gravity will clip the bottom edge, a bottom gravity  will clip the top edge, and neither will clip both edges. |
  | end               | 800005 | Push object to the end of its container, not changing its size. |
  | fill              | 77     | Grow the horizontal and vertical size of the object if needed so it  completely fills its container. |
  | fill_horizontal   | 7      | Grow the horizontal size of the object if needed so it completely  fills its container. |
  | fill_vertical     | 70     | Grow the vertical size of the object if needed so it completely fills  its container. |
  | left              | 3      | Push object to the left of its container, not changing its size. |
  | right             | 5      | Push object to the right of its container, not changing its size. |
  | start             | 800003 | Push object to the beginning of its container, not changing its size. |
  | top               | 30     | Push object to the top of its container, not changing its size. |

### XML attributes

- Inherited XML attributes from 
  - class android.view.View
  - class android.view.ViewGroup

- android:baselineAligned
  - When set to false, prevents the layout from aligning its children's baselines. This attribute is particularly useful when the children use different values for gravity. The default value is true.
- android:baselineAlignedChildIndex
  - When a linear layout is part of another layout that is baseline aligned, it can specify which of its children to baseline align to (that is, which child TextView).
- android:divider
  - Drawable to use as a vertical divider between buttons.
- android:measureWithLargestChild
  - When set to true, all children with a weight will be considered having the minimum size of the largest child. If false, all children are measured normally.
- [https://developer.android.com/reference/android/widget/LinearLayout#xml-attributes_1](https://developer.android.com/reference/android/widget/LinearLayout)

### Inherited Methods

- From class android.view.View
- From class android.view.ViewGroup
- From class java.lang.Object 
- From interface android.view.ViewParent
- From interface android.view.ViewManager
- From interface android.graphics.drawable.Drawable.Callback
- From interface android.view.KeyEvent.Callback
- From interface android.view.accessibility.AccessibilityEventSource

### Methods

- The index of the child that will be used if this layout is part of a larger layout that is baseline aligned, or -1 if none has been set.

  ```java
  int getBaselineAlignedChildIndex();
  ```

- Get the padding size used to inset dividers in pixels.

  ```java
  public int getDividerPadding();
  ```

- A flag set indicating how dividers should be shown around items. Value is either 0 or a combination of SHOW_DIVIDER_NONE, SHOW_DIVIDER_BEGINNING, SHOW_DIVIDER_MIDDLE, and SHOW_DIVIDER_END.

  ```java
  int getShowDividers();
  ```

- Return true if the pressed state should be delayed for children or descendants of this ViewGroup.

  ```java
  boolean shouldDelayChildPressedState();
  ```