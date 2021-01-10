## Android View, View Group and Layout Manager



### View

- Every item in a user interface is a subclass of the Android View class (android.view.View)

- Android SDK provides a set of pre-built views called *widgets* or *components* to construct a user interface, such as Button, CheckBox, ProgressBar and TextView classes

- new views can be created by extending an existing component class or even the View class to create components that are not supplied with the SDK



### View Group

- A view comprised of multiple other views (known as a *composite view*)

- These views are subclass of the Android *ViewGroup* class (*android.view.ViewGroup*)

- *ViewGroup* itself is a subclass of *View*

- Composite views consist of a single parent view (known as a *container view* or *root element)* that is capable of containing other views (known as *child views*)

Example: RadioGroup, is intended to contain multiple Radio Button objects such that only one can be in the “on” position at any one time.



### Layout Managers

- In addition to the widget style views, the SDK also includes a set of view groups referred to as *layouts*, designed for controlling how child views are positioned on the screen.

- Layout Managers can be nested within each other to create a user interface design of just about any necessary level of complexity.



#### **1. ConstraintLayout**

- Introduced in Android 7, and is recommended for most layout requirements

- Allows the positioning and behavior of the views in a layout to be defined by simple constraint settings assigned to each child view

- The flexibility of this layout allows complex layouts to be quickly and easily created without the necessity to nest other layout types inside each other, resulting in improved layout performance.

- Tightly integrated into the Android Studio Layout Editor tool

- Unless otherwise stated, this is the majority layout choice for the examples in the course



#### **2. LinearLayout**

- Positions child views in a single row or column depending on the orientation selected

- A weight value can be set on each child to specify how much of the layout space that child should occupy relative to other children



#### **3. TableLayout**

- Arranges child views into a grid format of rows and columns

- Each row within a table is represented by a TableRow object child, which, in turn, contains a view object for each cell



#### **4. FrameLayout**

- To allocate an area of screen, typically for the purposes of displaying a single view

- If multiple child views are added they will, by default, appear on top of each other positioned in the top left-hand corner of the layout area

- Alternate positioning of individual child views can be achieved by setting gravity values on each child

For example, setting a *center_vertical* gravity value on a child will cause it to be positioned in the vertical center of the containing FrameLayout view



#### **5. RelativeLayout**

- Allows child views to be positioned relative both to each other and the containing layout view through the specification of alignments and margins on child views.

- For example, child *View A* may be configured to be positioned in the vertical and horizontal center of the containing RelativeLayout view. *View B* might be configured to be centered horizontally within the layout view, but positioned 30 pixels above the top edge of *View A*, thereby making the vertical position *relative* to that of *View A*. 

- Can be of useful when designing a user interface that must work on a variety of screen sizes and orientations



#### **6. AbsoluteLayout**

- Allows child views to be positioned at specific X and Y coordinates within the containing layout view.

- Use of this layout is discouraged since it lacks the flexibility to respond to changes in screen size and orientation



#### **7. GridLayout**

- Divided by invisible lines that form a grid containing rows and columns of cells

- Child views are then placed in cells and may be configured to cover multiple cells both horizontally and vertically allowing a wide range of layout options to be quickly and easily implemented

- Gaps between components in a GridLayout may be implemented by placing a special type of view called a *Space* view into adjacent cells, or by setting margin parameters



#### **8. CoordinatorLayout**

- Designed specifically for coordinating the appearance and behavior of the app bar across the top of an application screen with other view elements

- When creating a new activity using the Basic Activity template, the parent view in the main layout will be implemented using a CoordinatorLayout



### View Hierarchy

- Each view in a user interface represents a rectangular area of the display

- A view is responsible for what is drawn in that rectangle and for responding to events that occur within that part of the screen, such as a touch event

- A user interface screen is comprised of a view hierarchy with a root view positioned at the top of the tree and child views positioned on branches below

- The child of a container view appears on top of its parent view and is constrained to appear within the bounds of the parent view’s display area.

Example: consider the following user interface, one way to achieve this is using the layout mechanism shown in right figure. In addition to the visible button and checkbox views, the user interface actually includes a number of layout views that control how the visible views are positioned.





User interfaces are constructed in the form of a view hierarchy with a root view at the top. The example user interface discussed before can be visualized in the form of the view tree.

