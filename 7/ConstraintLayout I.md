## ConstraintLayout I

### Add Constraints

There are typically 2 ways to add constraints in Layout Editor Tool for ConstraintLayout:

- Automatically add Constraints
- Manually add Constraints

### Automatically add Constraints

#### Autoconnect Mode

- Automatically establishes constraint connections as items are added to the layout.

- Can be enabled and disabled using the button in toolbar.

- Use algorithms to decide the best constraints to establish based on the position of the widget and the widget’s proximity to both the sides of the parent layout and other elements in the layout.

- In the event that any of the automatic constraint connections fail to provide the desired behavior, these may be changed manually.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_1.png" alt="constraint_layout_1_1" style="zoom:50%;" />

#### Autoconnect Mode Example

- Turn on Autoconnect Mode by clicking the button.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_2.png" alt="constraint_layout_1_2" style="zoom: 50%;" />

- Drag a widget like a button into the design view. Put it either center horizontally or vertically, or both. The dash lines will be shown to indicate this. The constraints will automatically be added.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_3.png" alt="constraint_layout_1_3" style="zoom:50%;" />

#### Inference Mode

- Use a heuristic approach involving algorithms and probabilities to automatically implement constraint connections after widgets have already been added to the layout.

- This mode is usually used when the Autoconnect feature has been turned off and objects have been added to the layout without any constraint connections.

- This allows the layout to be designed simply by dragging and dropping objects from the palette onto the layout canvas and making size and positioning changes until the layout appears as required.

- In essence this involves “painting” the layout without worrying about constraints.

- Inference mode can also be used at any time during the design process to fill in missing constraints within a layout.

- Constraints are automatically added to a layout when the *Infer constraints* button is clicked.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_4.png" alt="constraint_layout_1_4" style="zoom: 67%;" />
  
  *There could always be the possibility that the Layout Editor tool will infer incorrect constraints, which need to be manually corrected later.*

#### Inference Mode Example

- Make sure Autoconnect Mode is turned off.

- Drag a button onto design view, then drag a TextView onto design view into design view. And click infer constraints button.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_5.png" alt="constraint_layout_1_5" style="zoom:50%;" />

- The constraints will automatically been added.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_6.png" alt="constraint_layout_1_6" style="zoom:50%;" />

### Manually add Constraints

#### Layout Handles on a widget

- The spring-like lines (A) represent established constraint connections leading from the sides of the widget to the targets.

- The small square markers (B) in each corner of the object are resize handles which, when clicked and dragged, serve to resize the widget.

- The small circle handles (C) located on each side of the widget are the side constraint anchors. To create a constraint connection, click on the handle and drag the resulting line to the element to which the constraint is to be connected (such as a guideline or the side of either the parent layout or another widget).

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_7.png" alt="constraint_layout_1_7" style="zoom:48%;" />

- When connecting to the side of another widget, simply drag the line to the side constraint handle of that widget and, when it turns green, release the line.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_8.png" alt="constraint_layout_1_8" style="zoom:48%;" />

- An additional marker indicates the anchor point for baseline constraints whereby the content within the widget (as opposed to outside edges) is used as the alignment point.

- To display this marker, simply click on the button displaying the letters ‘ab’ (D).

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_9.png" alt="constraint_layout_1_9" style="zoom:48%;" />

- To establish a constraint connection from a baseline constraint handle, simply hover the mouse pointer over the handle until it begins to flash before clicking and dragging to the target (such as the baseline anchor of another).

- When the destination anchor begins to flash green, release the mouse button to make the constraint connection.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_10.png" alt="constraint_layout_1_10" style="zoom:48%;" />

#### Adding Constraints in the Inspector

- Constraints may also be added to a view within the Android Studio Layout Editor tool using the *Inspector* panel located in the Attributes tool.

- The square in the center represents the currently selected view and the areas around the square the constraints applied to the corresponding sides of the view:

- The absence of a constraint on a side of the view is represented by a dotted line leading to a blue circle containing a plus sign (as is the case with the bottom edge of the view in the above figure).

- To add a constraint, simply click on this blue circle and the layout editor will add a constraint connected to what it considers to be the most appropriate target within the layout.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_11.png" alt="constraint_layout_1_11" style="zoom:48%;" />

### Deleting Constraints

- To delete an individual constraint, simply click within the anchor to which it is connected.

- The constraint will then be deleted from the layout (when hovering over the anchor it will glow red to indicate that clicking will perform a deletion):

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_12.png" alt="constraint_layout_1_12" style="zoom: 60%;" />

- Remove all of the constraints on a widget by selecting it and clicking on the Delete All Constraints button which appears next to the widget when it is selected in the layout.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_13.png" alt="constraint_layout_1_13" style="zoom: 60%;" />

- To remove all of the constraints from every widget in a layout, use button named Clear All Constraints.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_14.png" alt="constraint_layout_1_14" style="zoom: 67%;" />

### Adjusting Constraint Bias

- As has been discussed before, the concept of using bias settings to favor one opposing constraint over another was outlined.

- Bias within the Android Studio Layout Editor tool is adjusted using the Inspector located in the Attributes tool window.

- The two sliders indicated by the arrows in the figure are used to control the bias of the vertical and horizontal opposing constraints of the currently selected widget.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_15.png" alt="constraint_layout_1_15" style="zoom: 60%;" />

- Suppose a button has 50% horizontal opposing bias, and 50% vertical opposing bias. It will be placed at the center of the screen.

- Now change of horizontal bias to 30%, and vertical bias to 80%, it will be moved to left-bottom direction.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_16.png" alt="constraint_layout_1_16" style="zoom:50%;" />

### ConstraintLayout Margins

- Constraints can be used in conjunction with margins to implement fixed gaps between a widget and another element (such as another widget, a guideline or the side of the parent layout).

- Consider, horizontal constraints applied to following Button.

- As currently configured, horizontal constraints run to the left and right edges of the parent ConstraintLayout. As such, the widget has opposing horizontal constraints indicating that the ConstraintLayout layout engine has some discretion in terms of the actual positioning of the widget at runtime.

- This allows the layout some flexibility to accommodate different screen sizes and device orientation.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_17.png" alt="constraint_layout_1_17" style="zoom:48%;" />

- The horizontal bias setting is also able to control the position of the widget right up to the right-hand side of the layout.

- For example, the following shows the same button with 100% horizontal bias applied.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_18.png" alt="constraint_layout_1_18" style="zoom:45%;" />

- ConstraintLayout margins can appear at the end of constraint connections and represent a fixed gap into which the widget cannot be moved even when adjusting bias or in response to layout changes elsewhere in the activity.

- For the following button, the right-hand constraint now includes a 50dp margin into which the widget cannot be moved even though the bias is still set at 100%.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_19.png" alt="constraint_layout_1_19" style="zoom: 50%;" />

- Existing margin values on a widget can be modified from within the Inspector. 

- A dropdown menu is being used to change the right-hand margin on the currently selected widget to 16dp.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_20.png" alt="constraint_layout_1_20" style="zoom:48%;" />

- Alternatively, clicking on the current value also allows a number to be typed into the field.

- And the default margin (initially is 8dp) for new constraints can be changed at any time using the option in the toolbar.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_21.png" alt="constraint_layout_1_21" style="zoom: 67%;" />

### Importance of Opposing Constraints and Bias

#### Issues without Opposing Constraints

- When a widget is constrained without opposing constraint connections, those constraints are essentially margin constraints, which is indicated visually within the Layout Editor tool by solid straight lines accompanied by margin measurements.

- For example, the button shown below has constraints essentially fix the widget at that position.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_22.png" alt="constraint_layout_1_22" style="zoom: 50%;" />

- The issue with previous layout is that if the device is rotated to landscape orientation, the widget will no longer be visible since the vertical constraint pushes it beyond the top edge of the device screen.

- A similar problem will arise if the app is run on a device with a smaller screen than that used during the design process.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_23.png" alt="constraint_layout_1_23" style="zoom:48%;" />

- When opposing constraints are implemented, the constraint connection is represented by the spring-like jagged line (the spring metaphor is intended to indicate that the position of the widget is not fixed to absolute X and Y coordinates).

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_24.png" alt="constraint_layout_1_24" style="zoom:48%;" />

- When rotated, the widget is still visible and positioned in the same location relative to the dimensions of the screen.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_25.png" alt="constraint_layout_1_25" style="zoom:50%;" />
  
  *When designing a responsive and adaptable user interface layout, it is important to take into consideration both bias and opposing constraints when manually designing a user interface layout and making corrections to automatically created constraints.*

### Configuring Widget Dimensions

- The inner dimensions of a widget within a ConstraintLayout can also be configured using the Inspector. 

- Widget dimensions can be set to wrap content, fixed or match constraint modes.

- The prevailing settings for each dimension on the currently selected widget are shown within the square representing the widget in the Inspector as illustrated below.

  - both the horizontal and vertical dimensions are set to wrap content mode

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_26.png" alt="constraint_layout_1_26" style="zoom:48%;" />

  - visual indicators to represent the three dimension modes

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_27.png" alt="constraint_layout_1_27" style="zoom: 67%;" />

- To change the current setting, simply click on the indicator to cycle through the three different settings.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_28.png" alt="constraint_layout_1_28" style="zoom:75%;" />

- When the dimension of a view within the layout editor is set to match constraint mode, the corresponding sides of the view are drawn with the spring-like line instead of the usual straight lines.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_29.png" alt="constraint_layout_1_29" style="zoom: 67%;" />

- It can also be changed in the inspector panel.

- For example, the width of the following view has been set to match constraint, and its height has been left with a fixed value.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_30.png" alt="constraint_layout_1_30" style="zoom:48%;" />

- In addition, the size of a widget can be expanded either horizontally or vertically to the maximum amount allowed by the constraints and other widgets in the layout using the *Expand horizontally* and *Expand vertically* options.

- These are accessible by right clicking on a widget within the layout and selecting the *Organize* option from the resulting menu.

- When used, the currently selected widget will increase in size horizontally or vertically to fill the available space around it. And this will change the widget dimension to a fixed value on selected axis.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_1_31.png" alt="constraint_layout_1_31" style="zoom: 45%;" />