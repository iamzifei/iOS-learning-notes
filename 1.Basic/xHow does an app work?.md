## how does an app work?

An app is essentially made up of **objects** that can send messages to each other. Many of the objects in your app are provided by iOS, for example the button – a UIButton object – and the alert popup – a UIAlertController object. Some objects you will have to program yourself, such as the view controller.
These objects **communicate by passing messages to each other**. When the user taps a button in the app, for example, that UIButton object sends a message to your view controller. In turn the view controller may message more objects.
On iOS, apps are **event-driven**, which means that the objects listen for certain events to occur and then process them.