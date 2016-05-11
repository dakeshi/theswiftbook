# Optionals

What are optionals? Actually, you already know about it. For example, suppose a website registration form needs to provide your personal information. To complete the registration, you must have to give your `Email Address`. On the other hand, `Phone` and `Website` are **optional** fields. So, you can put your information or keep the empty in these fields. And that's what optionals do in Swift.

How to implement the optional field of the example with Swift? Fortunately, Swift provides optionals to cope with the absence of value. An optional type is defined as an [`enumeration`](enumerations.md) in the Swift standard library :

```swift
enum Optional<Wrapped> {
    case Some(Wrapped)
    case None
}
```

* Some: assign some value in the instance of an optional type.
* None: set no value in the instance of an optional type.

`<Wrapped>` means that it is [`generic type`](generics.md). Therefore, you can use optionals with any type. An actual optional type will be determined when an optional variable or constant is declared.

In order to access a value which contains in an instance of an optional type, you can use _safely unwrapping_ or _forced unwrapping_. Recall how the optional enumeration is. Because a value is `wrapped` in the `Optional` enumeration, we need to take _unwrap_ process.


## [Syntax](#syntax)

Here is a simple way of creating an optional type:

```swift
let cityOne: Optional<String> = "Stockholm" // "Stockholm"
let cityTwo: String? = "Stockholm" // "Stockholm"
let cityThree: String? = Optional.Some("Stockholm") // "Stockholm"
let cityFour = Optional.Some("Stockholm") // "Stockholm"
```

They are equivalent. Instead of `Optional<Wrapped>`, you can use `?` with an actual type to make simple syntax expression. It's the most preferred way to create the optional type.

Also, you can have no value using the optional type:

```swift
let cityFive: String? = Optional.None
let citySix: String? = nil
var citySeven: String? // nil
```

If you declare an optional variable without an initial value, it will have a default value of nil. For more information about an initialization, see [struct initializers](struct_initializers.md) and [class initializers](class_initializers.md) documents.

## [Safely Unwrapping](#safely-unwrapping)

Since optionals might contain no values, before using them, you need to ensure that they indeed contain a value. There can be multiple solutions to unwrap it safely:

* `if` statement with `nil`
* optional binding

### `if` statement with `nil`

Simply, you can use `if` statement for checking optionals. For example:

```swift
if cityOne != nil {
  // Surely, a cityOne has a value.
  print("cityOne is \(cityOne!)")
}
```

If you are sure that optionals have a value, you can access its underlying value using an exclamation mark, such as `cityOne!`. Be careful when you use an optional with `!`.  If an optional has no value, it will report a compile-time error.

### optional binding

An optional can bind its value to a constant or variable. So, it is called _optional binding_. For example:

```swift
if let cityTwoName = cityTwo {
  print("cityTwoName = \(cityTwoName)")
}
```

Compared to the above solution, you don't need to use the `!` suffix to access a value of an optional within `if` block. It has already been safely unwrapped and bound to a constant called `cityTwoName` through _optional binding_.

Also, you can use `guard` statement with _optional binding_. For example:

```swift
guard let cityOneName = cityOne else {
  return
}

guard let cityFiveName = cityFive else {
  // The value of an optional constant,`cityFive`, is nil. So, `else` clause is executed.
  return
}

print("cityOneName = \(cityOneName)") // cityOneName = Stockholm
```

If constants or variables is declared in `guard` statement, you will use them without an exclamation mark, such as `cityOneName!`. In the above example, the `print` function uses `\(cityOneName)` instead of `\(cityOneName!)` because `cityOneName` constant is declared in `guard` statement.


## [Force Unwrapping](#force-unwrapping)

TODO: talk about `!` and how it is useful sometimes and how it can be dangerous

## [Switching](#switching)

TODO: explain how we can use the `switch` statement to find out what value is inside an optional. A custom `apply()` function on an extension to `Optional` comes to mind
