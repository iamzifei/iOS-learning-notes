## How does an app work

An app is essentially made up of **objects** that can send messages to each other. Many of the objects in your app are provided by iOS, for example the button – a UIButton object – and the alert popup – a UIAlertController object. Some objects you will have to program yourself, such as the view controller.
These objects **communicate by passing messages to each other**. When the user taps a button in the app, for example, that UIButton object sends a message to your view controller. In turn the view controller may message more objects.
On iOS, apps are **event-driven**, which means that the objects listen for certain events to occur and then process them.

### The app dicrectory

You can see several things inside the app’s directory:* The **Documents** directory where the app will put its data files. The contents of this directory are backed up when the user syncs their device with iTunes or iCloud. When updating the app, the folder is left *untouched*. 
* The **Library** directory has cache files and preferences files. The contents of this directory are managed by the operating system.* The **tmp** directory is for temporary files. Sometimes apps need to create files for temporary usage. You don’t want these to clutter up your Documents folder, so tmp is a good place to put them. iOS will clear out this folder from time to time.