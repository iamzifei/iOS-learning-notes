## Delegation

An object will rely on another object to help it out of certain tasks.

**Delegations in 5 steps:**

Object A is the delegate for object B, and Object B will send message back to A.

1. Define a delegate *protocol* for object B
2. Give B an optional delegate variable. The variable should be `weak`
3. Make B send messages to its delegate when something happens. `delelgate?.methodName(self, ...)`
4. Make object A conform to the delegate protocol. It should put the name of the protocol in its *class* line and implement the methods from the protocol.
5. Tell B that A is now its delegate.


Check [Sending message from one view controller to another](1.Basic/Sending message from one view controller to another.md) for more details