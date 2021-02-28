##  MediaPlayer

MediaPlayer class can be used to control playback of audio/video files and streams.

The media resources can be loaded from:

- Embedded in the App
- Internal and external storage (SD Card) 
- Internet

**Note**: we are going to discuss about playing audio files embedded in the App in this lecture. More advanced technologies will be put in reading resources, and will also be covered in Android II course.



Before playing the audio, the audio file need to be put as resources in the App. This step is much like putting the image files into the resources folders as we did previously. However, the difference is the audio file should be put it *raw* resources folder, if it does not exist, we need to create one.

Img_01

There are generally 2 ways to create an instance of the MediaPlayer, and set the media resource:

- Use new keyword to create an instance by the constructor, then call *setDataSource* method on the class.

  ``` java
  MediaPlayer mediaPlayer = new MediaPlayer(); 
  mediaPlayer.setDataSource(xxx);
  ```

- Use the static *create* method on the class, and it will return an instance of the MediaPlayer. 

  ``` java
  MediaPlayer mediaPlayer = MediaPlayer.create(xxx);
  ```

- Note: To play the resource embedded in the App, only the second way is supported.



Media Play Control methods

- ```public void start() ```
   Starts or resumes playback. If playback had previously been paused, playback will continue from where it was paused. If playback had been stopped, or never started before, playback will start at the beginning.

- ```public void stop()```
   Stops playback after playback has been started or paused.

- ```public void pause()```
   Pauses playback. Call start() to resume.

- ```public int getCurrentPosition ()```
   Get the current playback position in milliseconds.
- ```public int getDuration ()```
   Gets the duration of the file in milliseconds, if no duration is available (for example, if streaming live content), -1 is returned.
- ```public void seekTo (int msec)```
   Seeks to specified time position specified in milliseconds offset from the start.



### Example

Example Code: 



1. Create an Empty Activity project and name it MediaPlayerExample1.

2. Go to activity_main.xml file, and delete the existing TextView. Then drag a Button, and then put it below

   the center of the screen. Set the id to play_btn, and set Text to Play.

   Img_02

3. Drag another Button, and put it aside the Play Button. Set ID to pause_btn, and set Text to Pause.

   Img_03

4. Drag the last Button, and put it aside the Pause Button. Set ID to stop_btn, and set Text to Stop.

   Img_04

5. Add the constraints for the 3 Buttons, it is a good approach to create the horizontal chain for them. Select Buttons, and right click, then click on Chains, and Create Horizontal Chain.

   Img_05

6. Add the vertical constraints for each button. A alternative approach is to select each Button, adjust the values to 0, and set Vertical Bias to whatever needed.

   Img_06

   Img_07

7. After doing the previous approach for each button, the result will looks like the following way.

   Img_08

8. Go to MainActivity.java file, add the following code to get references to the three buttons.

   Img_09

9. Right click on resources folder, then click New, and Directory. In the popup Window, enter *raw* to create a raw resources folder.

   Img_10_0

   Img_10_1

   Img_10_2

10. Copy and paste your music file into the raw resources folder.
     Note: Please make sure the name before the extension(.mp3) contains only a-z, 0-9 and ”_”, and the numbers don’t start first. Or it will give compile errors later.

    Img_11

    Img_12

11. Add the following code in MainActivity.java to create a MediaPlayer, and load the music we just added.

    Img_13

12. Then add the following code to add OnClickListener for each Button to the behave MediaPlayer corresbonding controls.

    Img_14

13. Run the App, and enjoy the music. You may need to turn up the volume by clicking on the following button. How ever you may notice the Play Button doesn’t work once you click on the Stop Button.

    Img_15

14. To solve the issue, when the stop method is called, the prepare method need to be called before the start method to make it work again. Add the following code to solve this issue.

    Img_16