## Unwrapping optionals

In SWIFT we can delare an option variable such as `var window: UIWindow?`

To *unwrap* an optional you normally use the `if let` syntax:

```
if let w = window {
	let navigationController = w.rootViewController
}
```

As a shorthand you can use *optional chaining*
`let navigationController = window?.rootViewController`

If you're sure an optional will **NOT** be `nil` when you're going to use it, you can use *force unwrap* it by adding an *exclamation point*:
`let navigationController = window!.rootViewController`

Force unwrapping is the simplest way to deal with optionals, but it comes with a danger: if you’re wrong and the optional is nil, the app will crash. Use with caution!