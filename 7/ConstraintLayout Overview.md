## ConstraintLayout Overview

### Layout Editor

ConstraintLayout is responsible for managing the positioning and sizing behavior of the visual components (also referred to as widgets) it contains. It does this based on the constraint connections that are set on each child widget. It has the following key concepts:

- Constraints
- Margins
- Opposing Constraints
- Constraint Bias
- Chains
- Chain Styles
- Widget Dimensions
- Guidelines
- Barriers

### Constraints

- Sets of rules that dictate the way in which a widget is aligned and distanced in relation to other widgets, the sides of the containing ConstraintLayout and special elements called guidelines. 

- Dictate how the user interface layout of an activity will respond to changes in device orientation, or when displayed on devices of differing screen sizes.

- In order to be adequately configured, a widget must have sufficient constraint connections such that it’s position can be resolved by the ConstraintLayout layout engine in both the horizontal and vertical planes.
  - have sufficient constraint connections
  
    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_1.png" alt="constraint_layout_overview_1" style="zoom:50%;" />
  
  - miss horizontal constraint connections
  
    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_2.png" alt="constraint_layout_overview_2" style="zoom:51%;" />

### Margins

- A form of constraint that specifies a fixed distance.

- Consider a Button object that needs to be positioned near the top right-hand corner of the device screen.

- This might be achieved by implementing margin constraints from the top and right-hand edges of the Button connected to the corresponding sides of the parent ConstraintLayout.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_3.png" alt="constraint_layout_overview_3" style="zoom: 40%;" />

- Each of these constraint connections has associated with it a margin value dictating the fixed distances of the widget from two sides of the parent layout.

- Under this configuration, regardless of screen size or the device orientation, the Button object will always be positioned 20 and 15 device-independent pixels (dp) from the top and right-hand edges of the parent ConstraintLayout respectively as specified by the two constraint connections.

- Acceptable for most situations, but it lacks flexibility allowing the ConstraintLayout layout engine to adapt the position of the widget in order to respond to device rotation and to support screens of different sizes.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_4.png" alt="constraint_layout_overview_4" style="zoom: 40%;" />

### Opposing Constraints

- Two constraints operating along the same axis on a single widget.

- Make layout engine respond to device rotation change and support screens of different sizes.

- For example, a widget with constraints on both its left and right-hand sides is considered to have horizontally opposing constraints.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_5.png" alt="constraint_layout_overview_5" style="zoom:48%;" />

- Once opposing constraints are implemented on a particular axis, the positioning of the widget becomes percentage rather than coordinate based.

- Instead of being fixed at 20dp from the top of the layout, the widget is now positioned at a point 30% from the top of the layout.

- In different orientations and when running on larger or smaller screens, the Button will always be in the same location relative to the dimensions of the parent layout.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_6.png" alt="constraint_layout_overview_6" style="zoom: 50%;" />

### Constraint Bias

- By default, opposing constraints are equal, resulting in the corresponding widget being centered along the axis of opposition. 

- For example, the folloing figure shows a widget centered within the containing ConstraintLayout using opposing horizontal and vertical constraints:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_7.png" alt="constraint_layout_overview_7" style="zoom:40%;" />

- To allow for the adjustment of widget position in the case of opposing constraints, the ConstraintLayout implements a feature known as constraint bias.

- Constraint bias allows the positioning of a widget along the axis of opposition to be biased by a specified percentage in favor of one constraint.

- For example, the following figure shows the previous constraint layout with a 75% horizontal bias and 90% vertical bias:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_8.png" alt="constraint_layout_overview_8" style="zoom:40%;" />

### Chains

- Provide a way for the layout behavior of two or more widgets to be defined as a group.

- Can be declared in either the vertical or horizontal axis and configured to define how the widgets in the chain are spaced and sized.

- Widgets are chained when connected together by bi-directional constraints

- For example, the following figure illustrates three widgets chained in this way:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_9.png" alt="constraint_layout_overview_9" style="zoom: 50%;" />

- The first element in the chain is the chain head which translates to the top widget in a vertical chain or, in the case of a horizontal chain, the left-most widget.

- The layout behavior of the entire chain is primarily configured by setting attributes on the chain head widget.

### Chain Styles

The layout behavior of a ConstraintLayout chain is dictated by the *chain style* setting applied to the chain head widget. The ConstraintLayout class currently supports the following chain layout styles:

- **Spread Chain** – The widgets contained within the chain are distributed evenly across the available space. (default behavior for chains)

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_10.png" alt="constraint_layout_overview_10" style="zoom:48%;" />

- **Spread Inside Chain** – The widgets contained within the chain are spread evenly between the chain head and the last widget in the chain. The head and last widgets are not included in the distribution of spacing.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_11.png" alt="constraint_layout_overview_11" style="zoom: 43%;" />

- **Weighted Chain** – Allows the space taken up by each widget in the chain to be defined via weighting properties.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_12.png" alt="constraint_layout_overview_12" style="zoom:52%;" />

- **Packed Chain** – The widgets that make up the chain are packed together without any spacing. A bias may be applied to control the horizontal or vertical positioning of the chain in relation to the parent container.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_13.png" alt="constraint_layout_overview_13" style="zoom:51%;" />

### Widget Dimensions

The ConstraintLayout provides three options which can be set on individual widgets to manage sizing behavior. These settings are configured individually for height and width dimensions:

- **Fixed** – The widget is fixed to specified dimensions.
- **Match Constraint** –Allows the widget to be resized by the layout engine to satisfy the prevailing constraints. Also referred to as the *AnySize* or MATCH_CONSTRAINT option.
- **Wrap Content** – The size of the widget is dictated by the content it contains (i.e. text or graphics).

### Guideline

- Special elements available within the ConstraintLayout that provide an additional target to which constraints may be connected.

- Once added, constraint connections may be established from widgets in the layout to the guidelines.

- Particularly useful when multiple widgets need to be aligned along an axis.

- Multiple guidelines may be added to a ConstraintLayout instance to be configured in horizontal or vertical orientations.

- For example, the following figure shows three Button objects contained within a ConstraintLayout are constrained along a vertical guideline:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_14.png" alt="constraint_layout_overview_14" style="zoom:51%;" />

### Barriers

- Rather like guidelines, barriers are virtual views that can be used to constrain views within a layout.

- As with guidelines, a barrier can be vertical or horizontal and one or more views may be constrained to it (to avoid confusion, these will be referred to as *constrained views*).

- Unlike guidelines where the guideline remains at a fixed position within the layout, however, the position of a barrier is defined by a set of so called *reference views*.

- Barriers were introduced to address an issue that occurs with some frequency involving overlapping views.

- There is no limit to the number of reference views and constrained views that can be associated with a single barrier.

- Consider the layout illustrated below:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_15.png" alt="constraint_layout_overview_15" style="zoom:40%;" />

  - The width of View 3 is set to match constraint mode, and the left-hand edge of the view is connected to the right hand edge of View 1.
  - As currently implemented, an increase in width of View 1 will have the desired effect of reducing the width of View 3.

- A problem arises, however, if View 2 increases in width instead of View 1:

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_16.png" alt="constraint_layout_overview_16" style="zoom: 39%;" />

  - Because View 3 is only constrained by View 1, it does not resize to accommodate the increase in width of View 2 causing the views to overlap.

- A solution to this problem is to add a vertical barrier and assign Views 1 and 2 as the barrier’s *reference views* so that they control the barrier position. The left-hand edge of View 3 will then be constrained in relation to the barrier, making it a *constrained view*.

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/7/images/constraint_layout_overview_17.png" alt="constraint_layout_overview_17" style="zoom:38%;" />

  - Now when either View 1 or View 2 increase in width, the barrier will move to accommodate the widest of the two views, causing the width of View 3 change in relation to the new barrier position: