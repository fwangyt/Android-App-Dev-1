##  Example: RelativeLayout

[Example Code](https://github.com/fwangyt/Android-App-Dev-1/raw/master/9/RelativeLayoutExample.zip)



-   Let’s build a simple UI from Instagram app with RelativeLayout

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayoutExample/img_01.png" style="zoom:67%;" />



-   Create a new TextView,calledwarningTextView. Since the width of the warningTextView is equal to the width of the screen. Both layout_alignParentStartand layout_alignParentEnd should be true. Other attributes are shown below.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayoutExample/img_02.png" style="zoom:80%;" />



-   Create a new TextView, called titleTextView. Since the titleTextViewis below the warningTextView. Set layout_below=“id ofwarningTextView”. Then let’s just set layout_alignStartand layout_alignEndis equal to warningTextViewand add margins.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayoutExample/img_03.png" style="zoom:80%;" />



-   Create a new TextView, called messageTextView. Repeat the last setp.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayoutExample/img_04.png" style="zoom:80%;" />



-   Create a new TextView, called emailTextView. Repeat it again.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayoutExample/img_05.png" style="zoom:80%;" />



-   Create a new Button, called sendButton. The attributes of the sendButtonare shown below.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayoutExample/img_06.png" style="zoom:80%;" />



-   Run the app.

    <img src="https://raw.githubusercontent.com/fwangyt/Android-App-Dev-1/master/9/RelativeLayoutExample/img_07.png" style="zoom:80%;" />