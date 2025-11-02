
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

### Ensuring

⇒ The `final implicit class Ensuring[A](self: A) extends AnyVal` is mainly used in the whole system of pre- and postconditions. It is in the package `scala.Predef` and has a method `ensuring(predicate)`
⇒ It is usually after a code block in brackets and can take an additional parameter that is a message error

### Option

⇒ An abstract class that can contain, or not, a value. Instances of `Option` are either `Some(value)` or `None`
⇒ Mostly used to indicate if the method yielded a value or could not

### Either

⇒ An abstract class that represents a value of two possible types.
⇒ It can  be used as an alternative of `Option`. In this case, `Left` is used for failure and `Right` for success, by convention. The two are the subtypes of `Either`

### Lists and List operations

⇒ Lists in Scala are immutable, and instanciated with either `List(obj1, obj2)` or `obj1 :: obj2 :: Nil`
⇒ It is not necessary to declare the list's type, except in case of mixed types, where we specify either `List[A | B]`(union types) or `List[Any]`, but the second option is more permissive and can lead to type error
⇒ To *prepend* an element: `elem :: list`, to prepend another list, `list1 ::: list2`. It is generally slower to *append* elements because lists are singly-linked

### MUnit

⇒ The `MUnit` package provides different ways to test code
⇒ Using `test("name") {test body}` declares a test that passes, as long as the body does not crash with an exception
⇒ The FunSuite is a class that can be extended to create a test suite: 
	`class TestSomeMethod extends FunSuite {`
		`test suite body, with definitions and tests}`
⇒ The `assertEquals(a, b)` methods allows for comparison between two values, for example one expected and a result