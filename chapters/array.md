# Arrays

Arrays are an ordered, random-access collection of values of the same type. Because elements of an array are stored with an order, you can enumerate its value in sequence. Also, you can get a specific value using an index. An array can hold the same value more than once. Because of the nature of how arrays work, you can easily implement some data collection, such as [the world records holders in swimming](https://en.wikipedia.org/wiki/List_of_world_records_in_swimming). If a variable is declared with an array type, it will be mutable. It means that you can change its value with the new ones, remove its element, or add the new value in the array. An array provides default implementations for many common operations, such as count, filter, map, zip and reduce.

## [Syntax](#syntax)

Here is a simple way of creating an empty array:

```swift
var shoppingList: Array<String> = Array()
var fruits: [String] = []
var bucketList = [String]()
```

They are equivalent. It creates an empty array type of `String`. Instead of `Array<Element>`, you can use `[type]` expression to make simple syntax. It's the most preferred way to create the Array type.

You can check whether or not an array is the empty.

```swift
if shoppingList.isEmpty {
    print("an array is empty") // an array is empty
}
```

Let's add some elements in an array. You can use an array literal to do that.

```swift
var intArrayOne: Array<Int> = [1, 2, 3]
var intArrayTwo: [Int] = [4, 5, 6]
```

Using Swift's [Type Inference](data_types.md#type-inference), you can declare an array without the type annotation.

```swift
var intArrayThree = [7, 8, 9]
```

How to access an element in an array? An array provides an element's index to get a specific element in the array. The index number begins with `0`.

```swift
print(intArrayOne[0]) // 1
print(intArrayOne[1]) // 2

print(intArrayTwo[3]) // the runtime error
```

If you access the element with the wrong index number, the complier makes the runtime error. To avoid these kind of issues, an array provides some properties which return an optional type.

```swift
// first, last property return an optional type
// use the optional binding to get access the value in the optional
if let firstElement = intArrayTwo.first, lastElement = intArrayTwo.last {
    print(firstElement, lastElement, separator: ", ") // 4, 6
}
```

## [Mutating](#mutating)

If you assign an array to a variable, you can change elements in an array.

```swift
// add, remove and replace an element in the array
shoppingList.append("apple") // ["apple"]
shoppingList.append("mango")  // ["apple", "mango"]
shoppingList.removeLast() // ["apple"]. Remove the last element
shoppingList.insert("banana", at: 1) // ["apple", "banana"]. Insert element in the index 1
shoppingList.insert("cherry", at: shoppingList.startIndex) // ["cherry", "apple", "banana"]. Insert element in startIndex, 0.
shoppingList[1] = "orange" // ["cherry", "orange", "banana"]. Replace element in the index 1
```

Also, you can add multiple elements in an array.

```swift
// add multiple elements in another array
fruits.append(contentsOf: shoppingList) // ["cherry", "orange", "banana"]
```

## [Enumerating](#enumerating)

TODO: explain different ways of going through an array, such as `for x` or `forEach()`, etc.

## [Counting](#counting)

TODO: explain counting the number of items in an array

## [Filtering](#filtering)

TODO: explain the `filter()` function on arrays and tell the reader when it is useful to use `filter()`

## [Mapping](#mapping)

TODO: explain the `map()` function on arrays and tell the reader when it is useful to use `map()`

## [Zipping](#zipping)

TODO: explain the `zip()` function on arrays and tell the reader when it is useful to use `zip()`

## [Reducing](#reducing)

TODO: explain the `reduce()` function on arrays and tell the reader when it is useful to use `reduce()`
