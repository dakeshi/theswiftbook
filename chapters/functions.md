# Functions

A part of being a software engineer is to write as little code as possible in order to solve a problem. Problems can, however, be very similar to each other but have different requirements and output. Imagine the following problems that a programmer may need to solve:

* Download a JSON feed and parse its output into object models
* Download a text file and display its contents to the user
* Download a media file and play its contents for the user

All these problems have downloading in common, in that we first have to download the contents and then do something with them. As a programmer, we need to ensure that we don't write the downloading code 3 times. Instead, we need to strive to write it once and reuse it in other places.

Therefore, we should encapsulate our downloading code into a function or series of functions that can be placed inside a [structure](structures.md) or a [class](classes.md).

## [Syntax](#syntax)

The syntax for a function is made out of a few components:

1. The `func` reserved word: to indicate the beginning of a function declaration
2. The name of the function that should follow the [CamelCase](https://en.wikipedia.org/wiki/CamelCase) naming convention
3. An optional list of [arguments](function_arguments.md), with their names and their types
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

You can also have a list of [arguments](function_arguments.md) for your function with their names and data types:

```swift
func fullName(firstName: String, lastName: String) -> String{
  return firstName + " " + lastName;
}
```

Function arguments can have two names:

1. Internal
2. External

The internal function argument names are only used within the function body (inside the curly brackets) while the external names are used by the caller. Taking the previous example, the function's body uses the `fistName` and `lastName` arguments, just like the caller does. You can however change the function's definition so that inside the function's body you can refer to the arguments with another name, such as `fName` for `firstName` and `lName` for `lastName`:

```swift
func fullName(
  firstName fName: String,
  lastName lName: String) -> String{
  return fName + " " + lName;
}
```

You will learn more about function arguments later (see here).


TODO: give a few examples of functions and explain their syntax, with and without arguments or return values and then link the user to other sections under the Functions super section, such as [Arguments](function_arguments.md), [Return Type](function_return_type.md), etc

## [Versus Properties](#versus-properties)

TODO: explain where a function is more useful than a property. it usually comes down to the fact that a property is a function without arguments but perhaps there are other cases (such as functional programming) where functions are more useful




