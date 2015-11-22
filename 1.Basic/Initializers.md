##Initializers

Methods named “init” are special in Swift. They are only used when you’re creating new objects, to make those new objects ready for use.

It is pretty common for objects to have more than one init method. Which one is used depends on the circumstances.

The implementations of these init methods, whether they’re just called `init()` or `init?(coder)` or something else, always follow the same series of steps. When you write your own init methods, you need to stick to those steps as well.This is the standard way to write an init method:

```init() {// Put values into your instance variables and constants.super.init()// Other initialization code, such as calling methods, goes here.}
```

Note that unlike other methods, `init` *does not have the func keyword*.

Sometimes you’ll see it written as `override init` or `required init?`. That is necessary when you’re adding the init method to an object that is a subclass of some other object.

The question mark is for when `init?` can potentially fail and return a `nil` value instead of a real object. You can imagine that decoding an object can fail if not enough information is present in the plist file.