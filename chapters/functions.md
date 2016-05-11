# Functions

A part of being a software engineer is to write as little code as possible in order to solve a problem. Problems can, however, be very similar to each other but have different requirements and output. Imagine the following problems that a programmer may need to solve:

* Download a JSON feed and parse its output into object models
* Download a text file and display its contents to the user
* Download a media file and play its contents for the user

All these problems have downloading in common, in that we first have to download the contents and then do something with them. As a programmer, we need to ensure that we don't write the downloading code 3 times. Instead, we need to strive to write it once and reuse it in other places.

Therefore, we should encapsulate our downloading code into a function or series of functions that can be placed inside a [structure](structures.md) or a [class](classes.md).

## [Syntax](#syntax)

TODO: given a few examples of functions and explain their syntax, with and without arguments or return values and then link the user to other sections under the Functions super section, such as [Arguments](function_arguments.md), [Return Type](function_return_type.md), etc

## [Versus Properties](#versus-properties)

TODO: explain where a function is more useful than a property. it usually comes down to the fact that a property is a function without arguments but perhaps there are other cases (such as functional programming) where functions are more useful




