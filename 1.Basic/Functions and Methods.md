## Functions and Methods

###Difference between functions and methods

The difference between the two is that a **function doesn’t belong to an object** while a method does. In other words, a method is exactly like a function – that’s why you use the func keyword to define them – except that you need to have an object to use the method. But regular **functions**, or free functions as they are sometimes called, **can be used anywhere**.

### Method with multiple parameter in SWIFT

In other programming language it typically looks like this:
```
Int numberOfRowsInSection(UITableView tableView, Int section) {
	...}
```

In Swift:
```
override func tableView(tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
	... 
}
```

The full name of this method is `tableView(numberOfRowsInSection)`

The first parameter looks like this:
`ableView: UITableView`.

The name of this parameter is "tableView". The name is followed by a colon and the parameter's type, `UITableView`.

The second parameter looks like this:
`numberOfRowsInSection section: Int`

This one has two names, `numberOfRowsInSection` and `section`. The first name, `numberOfRowsInSection`, is used when calling the method (this is known as the *external parameter name*). Inside the method itself you use the second name, `section` (the local parameter name). The data type of this parameter is `Int`.

### The `return` value

The `return` type of the method is at the end, after the `->` arrow. If there is no arrow, then the method is not supposed to return a value. If the return type is something with `?`, it means can return nil object.

E.g. 
```
override func tableView(tableView: UITableView, willSelectRowAtIndexPath indexPath: NSIndexPath) -> NSIndexPath? 
```

the method is return a NSIndexPath object or nil. For method without `->`, you can still use `return` at the end to exit the method, but not following/returning a value