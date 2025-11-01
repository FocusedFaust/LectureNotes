
### Generic classes

⇒ These classes take a type as a parameter, and are particularly useful for collection classes
⇒ Their syntax is `class Name[A]` where A is the type identifier, and can be used in the class definition. To create an instance, you would call `val obj = Name[Type]`, and it would only accept instances of `Type` or its subtypes

### Polymorphic methods

⇒ Scala methods can take a type as parameter, as well as values. The syntax is `def methodName[A](param1: A, param2: B) = ...`
⇒ However, the type does not always need to be explicitly provided and can be inferred from the context or the type of the arguments

### Tuples
⇒ A **tuple** is a value that contains a fixed number of elements, each with its own types. Tuples are immutable
⇒ Its elements are accessed with their position, starting at index 0, so `tuple(0)`, `tuple(1)` and so on
⇒ Tuples can be taken apart with `val (elem1, elem2) = tuple`, and then we can directly call `println(elem2)` instead of `println(tuple(1))`
