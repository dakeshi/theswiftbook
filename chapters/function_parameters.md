# Function Parameters

A function, [as we discussed previously](functions.md), can optionally have parameters. Think of a parameter as an input to the function, so that the function can carry out its job as it should.

For instance, imagine that you are tasked with going shopping for a big dinner party tonight. What you need is:

* A list of things to buy
* Money
* Location of the store(s) where to purchase the goods
* Time

The act of going shopping is the function that you will perform and all the items that were just listed will be the parameters to your function. In other words, you won't be able to go shopping if any of the aforementioned parameters/inputs are missing.

Function parameters have the following properties:

* In-out specifier (`inout`)
* An internal name
* An external name
* A data type (e.g. [String](string.md), [Int](integer.md), [Double](double.md))
* [Variadic](#variadic) suffix (`...`)

Function parameter names contribute to the overal name of a function, where the first parameter's name is implicitly left off of the function signature. For instance:

```swift
func name(shortened: Bool) -> String{
  if shortened{
    return "Foo"
  }
  return "Foo Bar"
}
```

The name of this function is `name(_:)`. Pay attention to the `_:` syntax where `_` means _something_ in Swift and `:` denotes that _something_ is a parameter. All parameters except the first one will have their names implicitly mentioned as part of the function's signature. Take a look at this function:

```swift
func name(shortened: Bool, withoutSpace: Bool) -> String{
  if shortened{
    return "Foo"
  }
  
  if withoutSpace{
    return "FooBar"
  }
  
  return "Foo Bar"
}
```

The name of this function is therefore `name(_:withoutSpace:)`. For the first parameter's name to be mentioned in the function signature, it has to have an [internal](#internal-name) and an [external](#external-name) name, as shown here:

```swift
func name(shortened short: Bool, withoutSpace: Bool) -> String{
  if short{
    return "Foo"
  }
  
  if withoutSpace{
    return "FooBar"
  }
  
  return "Foo Bar"
}
```

Where `shortened` is the external parameter name and `short` is the internal name. After specifying both an external and an internal name for the first parameter of a function, the parameter's name will become part of the function's signature, such as `name(shortened:withoutSpace:)`.

## [Examples](#examples)

Let's have a look at various functions with different blend of parameters.

1. A function with one parameter:

```swift
func isValid(name: String) -> Bool{
  return name.characters.count > 10
}
```

When you call this function, the `name` parameter will not be visible by the caller:

```swift
isValid("Foo Bar")
```

Therefore this might be difficult to understand by the caller. In this case, you have two choices: to either give an [external name](#external-name) to the parameter:

```swift
func isValid(name name: String) -> Bool{
  return name.characters.count > 10
}
```

... or change the function name so that the parameter name is part of the function name as shown here:

```swift
func isValidName(name: String) -> Bool{
  return name.characters.count > 10
}
```

2. A function with (WORK IN PROGRESS)...

## [External Name](#external-name)

TODO: talk about external argument names here. Give examples

## [Internal Name](#internal-name)

TODO: talk about internal argument names here. Give examples. tell the reader why they might be useful and why they are not there by default

## [Naming Guidelines](#naming-guidelines)
 
TODO: talk about camelCase and link even to Wikipedia if necessary where they explain camelCase in details. it's good to also talk about guidelines for internal and external names

## [Default Values](#default-values)

TODO: tell the reader how functions can have arguments with default values and guidelines around which argument is best to have a difficult value (usually they come last in the list)

## [Variadic](#variadic)

TODO: write about what variadics are and how they can be used in Swift and what their limitations are. Compare the usage of variadics with arrays and tell the reader why we use one over the other

 

