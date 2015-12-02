## Tableview

### general concept

A `UITableView` object displays a list of things.

There're 2 styles of tables: "plain" and "grouped".

The data for a table comes in the form of **rows**.

Tables display their data in **cells**. A cell is related to a row but not exactly the same.
>A cell is a **view** that shows a row of data that happens to be **visible at that moment**.
>
>If your table can show 10 rows at a time on the screen, then it only has 10 cells, even though there may be 100 rows with actual data.
>
>Whenever a row scrolls off the screen and becomes invisible, its cell will be **re-used** for a new row that scrolls into the screen. (via *reuse identifier*)

Xcode has a handy feature named **prototype cells** lets you design your cells visually in Interface Builder.

### data source protocol
The data source is the link between your data and the table view. Usually the view controller plays the role of data source and implements these methods.

* The table view needs to know how many rows of data it has 
* The table view needs to know how it should display each of those rows.

> You don't say: " here are my 100 rows and show them on the screen."
> 
> Instead: "This view controller is now your data source. You can ask it questions about the data anytime you like."
>
>  ViewController: Hi, I'm your data source.
> 
>  UITableView: Hi, how many rows do you have?
> 
>  ViewController: 100
> 
>  UITableView: Can I have the cell for the first row?
> 
>  ViewController: here is the cell.
> 
>  UITableView: Can I have the cell for the 2nd row?
> 
>  ViewController: here is the cell.
> 
>  ...

Once hooked up to data source, e.g. view controller:

1. The table view sends a `numberOfRowsInSection` message to find out how many rows in total.
2. The table view needs to draw a particular row on the screen it sends the `cellForRowAtIndexPath` message to ask the data source for a cell.

*You can use static cells for the Table View if you know beforehand how many sections and rows the table view will have.* **In this case you don't need to provide a data source** *,and you can hook up UI elements such as Label or Button directly to outlets on the view controller*.

### Index paths
NSIndexPath is simply an object that points to a specific row in the table. It is a combination of a *row number* and a *section number*, that’s all.

### Delegation pattern in table view

The table view doesn’t really care who its data source is or what kind of data your app deals with, just that it can send the `cellForRowAtIndexPath` message and that it will receive a cell in return. This keeps the table view component simple and moves the responsibility for handling the data to where it belongs: in your code.

Likewise, the table view knows how to recognize when the user taps a row, but what it should do in response completely depends on the app. In this app you’ll make it toggle the checkmark; another app will likely do something totally different.

The table view splits up its delegate duties into two separate helpers: the `UITableViewDataSource` for putting rows into the table, and the `UITableViewDelegate` for handling taps on the rows and several other tasks.


### Tableview Cell
4 ways to make table view cells:

1. Using prototype cells, in Storyboard. This is the simplest and quickest way.

2. Using sattic cells. This is limited to screens where you know in advance which cells you'll have. The advantage with this is *you don't need to provide any data source method*
3. Using a *nib* file. Similar  to 1st way, except that you can do it outside of a Storyboard.
4. By hand/Coding. You need to specify a certain **cell style**.

