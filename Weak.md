## Weak

Relationships between objects can be weak or strong. You use weak relationships to avoid so-called *ownership cycles*.

When object A has a strong reference to object B, and at the same time object B also has a strong reference back to A, then these two objects are involved in a dangerous kind of romance: an ownership cycle.Normally, an object is destroyed – or deallocated – when there are no more strong references to it. But because A and B have strong references to each other, they’re keeping each other alive.

The result is a potential *memory leak* where an object that ought to be destroyed isn’t, and the memory for its data is never reclaimed. 

Such cycles can occur in other situations too but they are most common with delegates. Therefore, delegates are always made *weak*.(There is another relationship type, *unowned*, that is similar to weak and can be used for delegates too. The difference is that *weak variables are allowed to become nil again*. You may forget this right now.)

`@IBOutlets` are usually also declared with the *weak* keyword. 