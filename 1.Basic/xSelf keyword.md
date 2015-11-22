## self keyword

The `self` keyword allows the view controller to refer to itself. Normally you don't need to use self to send messages to the view controller.

**The exception**: inside *closures* you *do* have to use `self` to refer to the view controller.

*what is closure*
You can think of it as a method without a name. usually used as a call back handler.