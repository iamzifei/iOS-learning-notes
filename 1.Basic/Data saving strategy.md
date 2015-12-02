## Data saving strategy

Is it really necessary to save changes all the time? While the app is running, the data model sits in working memory and is always up-to-date.

The only time you have to load anything from the file/DB is when the app first starts up. You just need to make sure that you save the data to the file just before the app gets terminated.

There are three situations in which an app can terminate:

1. While the user is running the app. Earlier versions of iOS did not support multitasking apps. Receiving an incoming phone call would kill the currently running app. As of iOS4, the app will simply be suspended.
2. When the app is suspended in the background. Sometimes the OS needs to kill the suspended apps to get some memory.
3. The app crashes.

iOS will inform the app about significant changes such as "about to be terminated" and "about to be suspended". You can listen for these events. The ideal place is inside the **application delegate**.

###Xcode’s Stop button>When you press Xcode’s Stop button, the application delegate will not receive the applicationWillTerminate() notification. Xcode kills the app without mercy.Therefore, to test the saving behavior, always simulate a tap on the home button to make the app go into the background before you press Stop. If you don’t press Shift+⌘+H first, you’ll lose your data.