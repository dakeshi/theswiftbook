# Functions

A part of being a software engineer is to write as little code as possible in order to solve a problem. Problems can, however, be very similar to each other but have different requirements and output. Imagine the following problems that a programmer may need to solve:

* Download a JSON feed and parse its output into object models
* Download a text file and display its contents to the user
* Download a media file and play its contents for the user

All these problems have downloading in common, in that we first have to download the contents and then do something with them. As a programmer, we need to ensure that we don't write the downloading code 3 times. Instead, we need to strive to write it once and reuse it in other places.

Therefore, we should encapsulate our shared task into a function or series of functions that can be placed inside a [structure](structures.md) or a [class](classes.md).

A function is made out of line(s) of code and it knows how to deal with a specific task. Usually, a function has a name, unless it is passed to another function as a parameter, in which case the receiving function assigns a name to it ([see here](functions_passed_to_other_functions.md)). We can call functions using their names whenever we need their functionality.

## [Syntax](#syntax)

The syntax for a function is made out of a few components:

1. The `func` keyword: to indicate the beginning of a function declaration
2. The name of the function that should follow the [CamelCase](https://en.wikipedia.org/wiki/CamelCase) naming convention
3. An optional list of [parameters](function_parameters.md), with their names and their types
4. An optional [return value type](function_return_type.md)
5. Curly brackets, within which the contents of the function will be written

Given the 2 optional components in this list, you can create functions that only have a name, and nothing else, as shown here:

```swift
func emptyFunction(){
  //empty
}
```

Should you wish to return a value from your function, you can specify that with the `->` syntax followed by your return value data type:

```swift
func myName() -> String{
  return "Foo Bar"
}
```

Note how the [`return`](function_return_type.md) statement is used to return a value of the promised data type.

You can also have a list of [parameters](function_parameters.md) for your function with their names and data types:

```swift
func fullName(firstName: String, lastName: String) -> String{
  return firstName + " " + lastName;
}
```

Function parameters can have two names:

1. Internal
2. External

The internal function parameter names are only used within the function body (inside the curly brackets) while the external names are used by the caller. Taking the previous example, the function's body uses the `fistName` and `lastName` parameters, just like the caller does. You can however change the function's definition so that inside the function's body you can refer to the parameters with another name, such as `fName` for `firstName` and `lName` for `lastName`:

```swift
func fullName(
  firstName fName: String,
  lastName lName: String) -> String{
  return fName + " " + lName;
}
```

You will learn more about function parameters later ([see here](function_parameters.md)).

## [Versus Properties](#versus-properties)

[Structures](structures.md) and [classes](classes.md) can have functions; and so can they have [properties](properties.md) too. A property has a data type, such as [String](string.md), and so does a function. The only thing that differentiates a property and a function is that the former cannot have [parameters](function_parameters.md), while the latter can.
