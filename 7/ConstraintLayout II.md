## ConstraintLayout II

### Adding Guidelines

- Guidelines provide additional elements to which constraints may be anchored.

- Guidelines are added by right-clicking on the layout and selecting either the *Add Vertical Guideline* or *Add Horizontal Guideline* menu option or using the toolbar menu.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_1.png" alt="constraint_layout_2_1" style="zoom:50%;" />

- Once added, a guideline will appear as a dashed line in the layout and may be moved simply by clicking and dragging the line.

- To establish a constraint connection to a guideline, click in the constraint handler of a widget and drag to the guideline before releasing.

- In the following Figure, the left sides of two Buttons are connected by constraints to a vertical guideline.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_2.png" alt="constraint_layout_2_2" style="zoom:48%;" />

- The position of a vertical guideline can be specified as an absolute distance from either the left or the right of the parent layout (or the top or bottom for a horizontal guideline).

- The vertical guideline in the previous example is positioned 96dp from the left-hand edge of the parent.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_3.png" alt="constraint_layout_2_3" style="zoom:46%;" />

- Alternatively, the guideline may be positioned as a percentage of the overall width or height of the parent layout.

- To switch between these three modes, select the guideline and click on the circle at the top or start of the guideline (depending on whether the guideline is vertical or horizontal). 

- For example, the following Figure shows a guideline positioned based on percentage:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_4.png" alt="constraint_layout_2_4" style="zoom:35%;" />

### Adding Barriers

- Barriers can also be added by right-clicking on the layout and selecting either the *Add Vertical Barrier* or *Add Horizontal Barrier* option from the *Helpers* menu, or using the toolbar menu options.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_5.png" alt="constraint_layout_2_5" style="zoom:50%;" />

- Once a barrier has been added to the layout, it will appear as an entry in the Component Tree panel:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_6.png" alt="constraint_layout_2_6" style="zoom:75%;" />

- To add views as reference views (in other words, the views that control the position of the barrier), simply drag the widgets from within the Component Tree onto the barrier entry.

- For example, widgets named textView1 and textView2 have been assigned as the reference widgets for barrier1.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_7.png" alt="constraint_layout_2_7" style="zoom:70%;" />

- After the reference views have been added, the barrier needs to be configured to specify the direction of the barrier in relation those views.

- This is the *barrier direction* setting and is defined within the Attributes tool window when the barrier is selected in the Component Tree panel.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_8.png" alt="constraint_layout_2_8" style="zoom:48%;" />

### Widget Group Alignment and Distribution

- The Android Studio Layout Editor tool provides a range of alignment and distribution actions that can be performed when two or more widgets are selected in the layout.

- Simply shift-click on each of the widgets to be included in the action, right-click on the layout and make a selection from the many options displayed in the Align menu.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_9.png" alt="constraint_layout_2_9" style="zoom:48%;" />

- These options are also available as buttons in the Layout Editor toolbar.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_10.png" alt="constraint_layout_2_10" style="zoom:48%;" />

- Similarly, the Pack menu can be used to collectively reposition the selected widgets so that they are packed tightly together either vertically or horizontally.

- It achieves this by changing the absolute x and y coordinates of the widgets but does not apply any constraints. 

- The two distribution options in the Pack menu move the selected widgets so that they are spaced evenly apart in either vertical or horizontal axis and applies constraints between the views to maintain this spacing.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_11.png" alt="constraint_layout_2_11" style="zoom:55%;" />

### Creating a Chain

- Consider a layout consisting of three Button widgets constrained so as to be positioned in the top-left, top-center and top-right of the ConstraintLayout parent.

- Having heavily use the Design View adding the widget add widgets and constraints, this time we will cover a little bit about the code style layout.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_12.png" alt="constraint_layout_2_12" style="zoom: 40%;" />

- Add the following code to create the 3 buttons. The result will lead to 3 buttons created with constraints.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_13.png" alt="constraint_layout_2_13" style="zoom:50%;" />

- As currently configured, there are no bi-directional constraints to group these widgets into a chain.

- To address this, additional constraints need to be added from the right-hand side of button1 to the left side of button2, and from the left side of button3 to the right side of button2 with 2 lines of code as follows.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_14.png" alt="constraint_layout_2_14" style="zoom:50%;" />

- In order to make 2 widget form a chain, the first widget should have constraint to the second widget, also the second widget should have constraint to the first widget.

- With these changes, the widgets now have bi-directional horizontal constraints configured.

- This essentially constitutes a ConstraintLayout chain which is represented visually within the Layout Editor by chain connections as shown below.

- Note that in this configuration the chain has defaulted to the spread chain style.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_15.png" alt="constraint_layout_2_15" style="zoom:60%;" />

- It is also possible to create the chain using Design View.

- Select all the widgets you want to create the chains, and right-clicking on one of the views and selecting the *Chains -> Create Horizontal Chain* or *Chains -> Create Vertical Chain* menu options.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_16.png" alt="constraint_layout_2_16" style="zoom:75%;" />

### Changing the Chain Style

- If no chain style is configured, the ConstraintLayout will default to the spread chain style. The chain style can be altered by selecting any of the widgets in the chain and clicking on the Cycle Chain Style button as highlighted in the following Figure:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_17.png" alt="constraint_layout_2_17" style="zoom:60%;" />

- The chain style can be altered by selecting any of the widgets in the chain and clicking on the Cycle Chain Style button.

- Each time the chain button is clicked the style will switch to another setting in the order of spread, spread inside and packed.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_18.png" alt="constraint_layout_2_18" style="zoom:60%;" />

- Alternatively, the style may be specified in the Attributes tool window by clicking on the *View all attributes* link, unfolding the *Constraints* section and changing either the *horizontal_chainStyle* or *vertical_chainStyle* property depending on the orientation of the chain.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_19.png" alt="constraint_layout_2_19" style="zoom:48%;" />

- The following two figures show *spread inside* chain and *packed* chain styles separately.
  - *spread inside* chain
  
    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_20.png" alt="constraint_layout_2_20" style="zoom:46%;" />
  
  - *packed* chain 
  
    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_21.png" alt="constraint_layout_2_21" style="zoom: 50%;" />

### Packed Chain Style with Bias

- The positioning of the packed chain may be influenced by applying a bias value.

- The bias can be any value between 0.0 and 1.0, with 0.5 representing the center of the parent.

- Bias is controlled by selecting the chain head widget and assigning a value to the *horizontal_bias* or *vertical_bias* attribute in the Attributes panel.

- The following figure shows a packed chain with a horizontal bias setting of 0.2.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_22.png" alt="constraint_layout_2_22" style="zoom: 52%;" />

### Weighted Chain

- The weight of the individual widgets is used to control how much space each widget in the chain occupies within the available space.

- A weighted chain may only be implemented using the *spread* or *spread inside* chain style and any widget within the chain that is to respond to the weight property must have the corresponding dimension property (height for a vertical chain and width for a horizontal chain) configured for *match constraint* mode.

- Match constraint mode for a widget dimension can be set by selecting the widget, displaying the Attributes panel and changing the dimension to *match_constraint*.

- For example, the *layout_width* constraint for button1 has been set to *match_constraint* to indicate that the width of the widget is to be determined based on the prevailing constraint settings.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_23.png" alt="constraint_layout_2_23" style="zoom:50%;" />

- Assuming that the spread chain style has been selected, and all three buttons have been configured such that the width dimension is set to match the constraints, the widgets in the chain will expand equally to fill the available space.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_24.png" alt="constraint_layout_2_24" style="zoom: 67%;" />

- The amount of space occupied by each widget relative to the other widgets in the chain can be controlled by adding weight properties to the widgets.

- The following figure shows the effect of setting the *horizontal_weight* property to 4 on button1, and to 2 on both button2 and button3.

- As a result of these weighting values, button1 occupies half of the space (4/8), while button2 and button3 each occupy one quarter (2/8) of the space.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_2_25.png" alt="constraint_layout_2_25" style="zoom:70%;" />