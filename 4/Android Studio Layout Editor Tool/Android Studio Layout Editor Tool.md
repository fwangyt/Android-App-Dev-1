## Android Studio Layout Editor Tool



### Layout Editor

- provides a “what you see is what you get” (WYSIWYG) environment in which views can be selected from a palette and then placed onto a canvas representing the display of an Android device
- Once a view has been placed on the canvas, it can be moved, deleted and resized (subject to the constraints of the parent view)
- Further, a wide variety of properties relating to the selected view may be modified using the Attributes tool window



#### Design mode and Text mode

- Under the surface, the Layout Editor tool actually constructs an XML resource file containing the definition of the user interface that is being designed.
- The Layout Editor tool operates in two distinct modes referred to as *Design mode* and *Text mode*



#### Design mode

In design mode, the user interface can be visually manipulated by directly working with the view palette and the graphical representation of the layout.





- **A – Palette** – The palette provides access to the range of view components provided by the Android SDK. These are grouped into categories for easy navigation. Items may be added to the layout by dragging a view component from the palette and dropping it at the desired position on the layout.

- **B – Device Screen** – The device screen provides a visual “what you see is what you get” representation of the user interface layout as it is being designed. This layout allows for direct manipulation of the design in terms of allowing views to be selected, deleted, moved and resized. The device model represented by the layout can be changed at any time using a menu located in the toolbar.

- **C – Component Tree** – User interfaces are constructed using a hierarchical structure. The component tree provides a visual overview of the hierarchy of the user interface design. Selecting an element from the component tree will cause the corresponding view in the layout to be selected. Similarly, selecting a view from the device screen layout will select that view in the component tree hierarchy.

- **D – Attributes** – All of the component views listed in the palette have associated with them a set of attributes that can be used to adjust the behavior and appearance of that view. The Layout Editor’s attributes panel provides access to the attributes of the currently selected view in the layout allowing changes to be made.

- **E – Toolbar** – The Layout Editor toolbar provides quick access to a wide range of options including the ability to zoom in and out of the device screen layout, change the device model currently displayed, rotate the layout between portrait and landscape and switch to a different Android SDK API level. The toolbar also has a set of context sensitive buttons which will appear when relevant view types are selected in the device screen layout.

- **F – Mode Switching Tabs** – The tabs located along the lower edge of the Layout Editor provide a way to switch back and forth between the Layout Editor tool’s text and design modes.



#### Palette



- Layout Editor palette is organized into two panels.

- The category panel (A) lists the different categories of view components supported by the Android SDK.
- When a category is selected, the second panel (B) updates to display a list of the components that fall into that category
- To add a component from the palette onto the layout canvas, simply select the item either from the component list, drag it to the desired location and drop it into place.
- A search for a specific component within the currently selected category can be initiated by clicking on the search button (C) in the palette toolbar and typing in the component name. 
- If you are unsure of the category in which the component resides, simply select the All category either before or during the search operation.



#### Design and Layout Views

- When the Layout Editor tool is in Design mode, the layout can be viewed in two different ways.
- The view previous shown is the Design view and shows the layout and widgets as they will appear in the running app.
- Another mode, referred to as Layout or Blueprint view can be shown either instead of, or concurrently with the Design view.
- The toolbar menu shown provides options to display the Design, Blueprint, or both views.
- The fourth option, *Force Refresh Layout* will cause the layout to rebuild and redraw. This can be useful when the layout enters an unexpected state or is not accurately reflecting the current design settings (It is not a mode)



Whether to display the layout view, design view or both is a matter of personal preference. A good approach is to begin with both displayed



#### Text mode

- using the Android Studio Layout Editor tool that all it is really doing is providing a user friendly approach to creating XML layout resource files.
- At any time during the design process, the underlying XML can be viewed and directly edited simply by clicking on the *Text* tab located at the bottom of the Layout Editor tool panel.
- To return to design mode, simply click on the *Design* tab.



**A – Editor** – The editor panel displays the XML that makes up the current user interface layout design.

**B – Preview** – As changes are made to the XML in the editor, these changes are visually reflected in the preview window. The preview also allows direct manipulation and design of the layout just as if the layout were in Design mode, with visual changes being reflected in the editor panel in real-time.

**C – Toolbar** – The toolbar in text mode provides access to the same functions available in design mode.

**D - Mode Switching Tabs** – The tabs located along the lower edge of the Layout Editor provide a way to switch back and forth between the Layout Editor tool’s Text and Design modes.



#### Setting Attributes

- The Attributes panel provides access to all of the available settings for the currently selected component.

- By default, the attributes panel shows the most commonly changed attributes for the currently selected component in the layout

For example, the following shows this subset of attributes for the TextView widget:





- To access all of the attributes for the currently selected widget, click on the button, or use the *View all attributes* link at the bottom of the attributes panel

- A search for a specific attribute may also be performed by selecting the search button in the toolbar of the attributes tool window and typing in the attribute name.

- Select the *View all attributes* button or link either before or during a search to ensure that all of the attributes for the currently selected component are included in the results.

   



#### Design Mode and Text Mode

- As mentioned before, under the surface, the Layout Editor tool actually constructs an XML resource file. It’s up to you whether use Design Mode or Text Mode, and they will be reflected on each other.

- For example, set the attributes to a view in Layout Editor tool, it will be shown the same in XML file, and vice versa.

  