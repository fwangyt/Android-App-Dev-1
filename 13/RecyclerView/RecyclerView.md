##  **RecyclerView**

Imgine when you need to display a large dataset within your UI, it may be tempting to add hundreds of Views to your UI - this is almost always the wrong approach. Instead, the RecyclerView (available from the Android Support Library) offers a scrollable View Group specifically designed to efficiently display, and scroll through, a large number of items.

**RecyclerView** is scrollable container for large data sets

-   Uses and reuses limited number of Viewelements

-   Updates changing data fast



#### RecyclerView vs ListView

Several years ago before the RecyclerViewcomes out, ListViewis used to list a number of items in Android. 

The RecyclerView, however, provides a number of advantages over the ListView. In particular, the RecyclerViewis significantly more efficient in the way it manages the views that make up a list, essentially reusing existing views that make up list items as they scroll off the screen instead if creating new ones (hence the name “recycler”).

This both increases the performance and reduces the resources used by a list, a feature that is of particular benefit when presenting large amounts of data to the user.

Unlike the ListView, the RecyclerViewalso provides a choice of three built-in layout managers to control the way in which the list items are presented to the user.



#### RecyclerView Components

1.  **Data**

2.  **RecyclerView** scrolling list for list items—*RecyclerView*

3.  **Layout** for one item of data—*XML file*

4.  **Layout manager** handles the organization of UI components in a View—*Recyclerview.LayoutManager*

5.  **Adapter** connects data to the RecyclerView—*RecyclerView.Adapter*

6.  **ViewHolder** has view information for displaying one item—*RecyclerView.ViewHolder*



#### **How RecyclerView Components Fit Together**

![](https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView/img_01.png)



#### **Layout Manager**

-   Each ViewGrouphas a layout manager
-   Use to position Viewitems inside a RecyclerView
-   Reuses Viewitems that are no longer visible to the user 
-   Built-in layout managers 
    -   LinearLayoutManager
    -   GridLayoutManager
    -   StaggeredGridLayoutManager
-   Extend RecyclerView.LayoutManager

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView/img_02.png" style="zoom:50%;" />

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView/img_03.png" style="zoom:50%;" />

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView/img_04.png" style="zoom:50%;" />



#### Adapter

-   Helps incompatible interfaces work together
    -   Example: Takes data from database Cursorand prepares strings to put into a View

-   Intermediary between data and View

-   Manages creating, updating, adding, deleting Viewitems as underlying data changes

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView/img_05.png" style="zoom:50%;" />

RecyclerViewdepends on an adapter to act as the intermediary between the RecyclerViewinstance and the data that is to be displayed to the user. 

The adapter is created as a subclass of the RecyclerView.Adapterclass and must, at a minimum, implement three methods, which will be called at various points by the RecyclerViewobject to which the adapter is assigned:

-   ```getItemCount()``` –This method must return a count of the number of items that are to be displayed in the list.

-   ```onCreateViewHolder()``` –This method creates and returns a ViewHolderobject initialized with the view that is to be used to display the data. This view is typically created by inflating the XML layout file.

-   ```onBindViewHolder()``` –This method is passed the ViewHolderobject created by the *onCreateViewHolder()* method together with an integer value indicating the list item that is about to be displayed. Contained within the ViewHolderobject is the layout assigned by the *onCreateViewHolder()* method. It is the responsibility of the *onBindViewHolder()* method to populate the views in the layout with the text and graphics corresponding to the specified item and to return the object to the RecyclerViewwhere it will be presented to the user.



#### ViewHolder

-   Used by the adapter to prepare one Viewwith data for one list item 

-   Layout specified in an XML resource file

-   Can have clickable elements

-   Is placed by the layout manager

  <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/13/RecyclerView/img_05.png" style="zoom:50%;" />



#### **Implementing** RecyclerView Steps

1.  Add RecyclerViewdependency to build.gradleif needed

2.  Add RecyclerViewto layout

3.  Create XML layout for item

4.  Extend RecyclerView.Adapter

5.  Extend RecyclerView.ViewHolder

6.  In ActivityonCreate(), create RecyclerViewwith adapter and layout manager