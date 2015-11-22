## MVC

### Model

These objects obtain your data and any operations on the data.

E.g. if you were writing a cookbook app, the model would consist of the recipes. In a game app, it would be the design of the levels, the score of the player and the positions of the monsters, etc.

The operations that the data model objects perform are sometimes called the *business rules* or the *domain logic*.

### View

These objects make up the visual part of the app: images, buttons, labels, text fields, etc. In a game the views form the visual representation of the game world, such as the monster animations and a frag counter.

*A view can draw itself and responds to user input, but it typically does not handle any application logic.* Many views can be re-used as they are not tied to a specific data model.

### Controller

The controller is the object that *connects* your data model objects to the views. It listens to taps on the views, makes the data model objectsdo some calculations in response, and updates the views to reflect the new state of your model.

*Your app flows from one view controller to the other.*

### View vs. View Controller

A view is an objewct that draws something on the screen, such as a button or a label. It is what you see.

The view controller is what does the work behind the scenes. It is the *bridge sits between data model and the views*.

### Container view controller

Usually one view controller represents one scree, but sometimes could have two view controllers for a screen: a Table View Controller that sits inside a **Navigation Controller**.

The Navigation Controller is a special type of view controller that acts as a container for other view controllers. It comes with a navigation bar and has the ability to easily go from one screen to another, by sliding them in and out of sight. The container essentially “wraps around” these screens.

The Navigation Controller is just the frame that contains the view controllers that do the real work, which are known as the “content” controllers.

Another often-used container is the **Tab Bar Controller**.

On the iPad, container view controllers are even more commonplace. View controllers on the iPhone are full-screen but on the iPad they often occupy only a portion of the screen, such as the content of a popover or one of the panes in a split-view.