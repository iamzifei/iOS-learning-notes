## declare a variable and type

```swift
var a: Int = 0
var b = 0
```

* Swift needs variable either having an *data type* or *initial value*, or *both* when define it.
* if you don't specify a data type, e.g. `var b = 0`, Swift uses type *inference* to figure out what type you meant. This will needs an initial value for the variable. Because the initial value 0 is an whole number, Swift assumes that should be an integer. So same as `var b: Int = 0`
 