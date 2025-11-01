
### Extension methods

⇒ `extension (obj: A)`
	`def method: B = ...
⇒ This defines a new method for the A class, even if it is inaccessible, that can 
⇒ Multiple extension methods can be defined in an extension

### Operators

⇒ Operators are methods in Sc\*la (don't ask). any method with a single parameter can be used as an *infix operator* (like +, -, \*, /)
⇒ Conversely, operators can be called with dot-notation: `10.+(1)`
⇒ Any legal identifier as an operator, including symbols, as long as they are defined

### Infix notation

⇒ **arity-x** means that a function has x argument
⇒ Methods with arity-1 can be invoked with a special punctuation, that should be for purely functional methods (with no side effects)
⇒ `object method parameter` instead of `object.method(parameter)`

### @main
⇒ Entry point of the program, just like in Java

### Package and imports

⇒ Define packages with `package path.name`
⇒ Import packages with `import package.*`

### Traits

⇒ Traits allow for interface and field sharing between classes. They can be extended by classes and objects but cannot be instantiated
⇒ Defined by `trait Name`, can take a type parameter and have variables, and they define abstract methods 
⇒ Then, classes extend a trait with the `extends` keyword, they must implement any abstract members using the `override` keyword

### Subtyping

⇒ "Where a given trait is required, a subtype of the trait can be used instead."
⇒ We can call any method of a trait, as it must be implemented by its subtypes

### Abstract classes

⇒ Classes may have abstract members, in which case we can either create a tract or an abstract class
⇒ An abstract class is defined with `abstract class Name(params)` but now traits can also have parameters, so we can write `trait Name(params)`

### Singleton objects

⇒ An object is a class with exactly one instance
⇒ Its definition looks like a class but uses the keyword `object Name` 
⇒ It can define methods, which will most often be utility methods
⇒ Method can be imported with `import package.Name.method` and is directly usable without calling `Name`

### Case classes

⇒ The definition syntax is `case class Name(params)`. The parameters will be public `val`s, so they are immutable
⇒ **Comparison:** Case classes are compared by structure/value rather than by reference (i.e. two different instances are equal if they have the same values for their parameters)
⇒ **Copying:** It's possible to create a shallow copy of an instance with the `copy` method, that can take arguments (`obj.copy(param1 = value, param2 = value)`)

### Enumerations

⇒ Used to define a type with a set of named values
⇒ `enum Name:
	`case Obj1, Obj2, Obj3` is the shorthand notation
⇒ `enum Name(params)`
	`case Obj1 extends Name(values)`
	`case Obj2 extends Name(values)`
	`case Obj3 extends Name(values)`
⇒ Enums can also have custom definitions for methods and `val`s. They can also have companion classes
⇒ If the enum has a covariant type parameter and one of the cases is parameterized, then that case is a case class extending the enum. Ex: `enum Option[+T]: case Some(x: T) extends Option[T]`

### Match case

⇒ **Syntax:** first the variable to match, then `match` and at least one `case`
⇒ `x match`
	`case 0 => "zero`
	`case 1 => "one"`
	`case _ => "other"`
⇒ Pattern guards are boolean expression added after the case pattern to be more specific
⇒ It is possible to match only the type of an object, like so:
	`obj match`
		`case a: A => do smth`
		`case b: B => do smth else`
