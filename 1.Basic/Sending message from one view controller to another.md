## Sending message from one view controller to another

>a view controller to add a new task in a Todo list app. 
>
>From the ListViewController, tap Add button to the NewTaskViewController. 
>
>After adding new task, tap Done button to return to the ListViewController.

Maybe some code like this:

```
class AddItemViewController: UITableViewController ... 
{	// This variable refers to the other view controller	var checklistViewController: ChecklistViewController	@IBAction func done() {		// Create the new checklist item object		let item = ChecklistItem()
		item.text = textField.text!		// Directly call a method from ChecklistViewController		checklistViewController.addItem(item)
	} 
}
```

`AddItemViewController` has a variable that refers to the `ChecklistViewController` and `done()` calls its `addItem()` method with the new ChecklistItem object.

*This will work, but **NOT** the iOS way*, the big downside of this approach is it shackles 2 view controller objects together.

**The solution is to make your own delegate.**
>Screen A opens screen B. At some point screen B needs to communicate back to screen A, usually when it closes.
>The solution is to make screen A the delegate of screen B, so that B can send its messages to A whenever it needs to.

This principle, where screen B is independent of screen A yet can still talk to it, is called **loose coupling** and is considered good software design practice.

In SWIFT, Delegates go hand-in-hand with *protocols*.

### Protocols
A protocol doesn’t implement any of the methods it declares. It just says: any object that conforms to this protocol must implement methods X, Y and Z. Like Interface in JAVA.

Delegate methods *usually* have a reference to their owner as the first (or only) parameter.

Often delegates are truly optional. So declaration would be `weak var delegate: AddItemViewControllerDelegate?`. The ending `?` saying this `var` could have a `nil` value.