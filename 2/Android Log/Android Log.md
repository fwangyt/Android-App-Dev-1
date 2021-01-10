## Android Log



Logs are necessary when you develop the Android App, it can be used to print out some useful information. And it also help for debugging.

Android has a log class in  ```android.util```  package which provides a set of APIs for sending log output.Generally, develpers should use the Log.v(), Log.d(), Log.i(), Log.w(), and Log.e() methods to write logs. You can then view the logs in logcat.



The meaning of each log method is show in the following table.

| Log.()  | Log.d() | **Log.i**() | **Log.w**() | **Log.e**() |
| ------- | ------- | ----------- | ----------- | ----------- |
| VERBOSE | DEBUG   | INFO        | WARN        | ERROR       |

The order in terms of verbosity, from least to most is ERROR, WARN, INFO, DEBUG, VERBOSE. Verbose should never be compiled into an application except during development. Debug logs are compiled in but stripped at runtime. Error, warning and info logs are always kept.



For each of these method, it has two overloads except Log.w:

``` java
public static int xx(String tag, String msg);
public static int xx(String tag, String msg, Throwable tr);
// xx = v, d, i, w, or e
public static int w(String tag, Throwable tr)
```

The meaning of each parameter is shown below:

| Parameters | Type      | **Description**                                              |
| ---------- | --------- | ------------------------------------------------------------ |
| tag        | String    | Used to identify the source of a log  message. It usually identifies the class or activity where the log call  occurs. This value may be null. |
| msg        | String    | The message you would like logged. This  value may be null.  |
| tr         | Throwable | An exception to log This value may  be null.                 |



In order to view the Android logs, the Logcat window is needed. It provides access to the monitoring log output from a running application in addition to options for taking screenshots and videos of the application and stopping and restarting a process.



The following table show the function of each selection or text filed box:

| **Box#** | **Usage**                                                    |
| -------- | ------------------------------------------------------------ |
| A        | Selection  the device to show the log, including simulatosr  and real devices |
| B        | The  Application process to show the log                     |
| C        | Log  level                                                   |
| D        | Keyword  filter                                              |



You can control how many messages appear in logcat by setting the log level. You can display all messages, or just the messages indicating the most severe conditions

Remember that logcat continues to collect all messages regardless of the log level setting. The setting just determines what logcat displays.

- **Verbose:** Show all log messages (the default).

- **Debug:** Show debug log messages that are useful during development only, as well as the message levels lower in this list (have higher priority).

- **Info:** Show expected log messages for regular usage, as well as the message levels lower in this list.

- **Warn:** Show possible issues that are not yet errors, as well as the message levels lower in this list.

- **Error:** Show issues that have caused errors, as well as the message level lower in this list.

- **Assert:** Show issues that the developer expects should never happen.

