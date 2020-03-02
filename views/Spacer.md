# Spacer
A view that is used to create a flexible space inside layouts.

---

> UIKit equivalents: `UIBarButtonItem.SystemItem.flexibleSpace`
> 
> Available since: iOS 13.0, macOS 10.15, macOS Catalyst 13.0, tvOS 13.0, watchOS 6.0, Xcode 11.0

### Declaration
```swift
@frozen struct Spacer
```

### Overview
A `Spacer` view is used to fill in spaces inside your layout and push neighbouring views apart from each other. When a spacer is placed inside a `VStack` or an `HStack` it will attempt to take up any and all unoccupied space, pushing neighbouring edges to the edges of the stack. This can be particularly useful, when using alignments, such as `.topLeading`, or `.trailing` is not possible or more difficult.

When creating a spacer you have the option of providing a minimum length for the spacer. This will be the absolute minimum length that the spacer must always have. This can come in useful when you need variadic spacing your stack view.

> **Note:** A spacer's `minLength` is not 0 by default but rather `nil`. This means that spacers that were not provided a minimum length, will infer a system default minimum length, which may not necessarily be 0. If you wish to create a spacer that will collapse entirely when there is no unused space, then consider creating a spacer with a custom `minLength` of 0. 

> **Note:** It is not recommended to specify minimum or maximum lengths for a spacer using the `frame` modifier, since a spacer can grow both in horizontal and vertical directions (not both). Using the `minLength` property ensures that your spacer will always have the right minimum length no matter which axis it is on. However if you must resort to using the `frame` modifier for controling the size of your spacer, make sure to **always** provide both a width and a height constraint to avoid layout bugs.

### Usage
Here's an example of how a spacer can be used to position a `Text` view on the bottom trailing corner of the layout.
```swift
HStack {
    // This causes the text to move to the trailing edge of the layout.
    Spacer()
    
    VStack {
        // This causes the text to move to the bottom edge of the layout.
        Spacer()
        
        Text("Hello Corner!")
    }
}
```

### Visuals
`Spacer`s are _non-rendered_ views, meaning that while they occupy space on the screen, using modifiers such as `background`, `border` or `overlay` will not produce any visible content for you to see. Therefore a spacer can never be directly seen on the screen (except for the space that it actually occupies).

## Topcis

---
#### Creating a spacer

```swift
init(minLength: CGFloat? = nil)
```
Creates a spacer with the given minimum length. If no value, or `nil` is provided as the minimum length, a system default spacing is assumed.

###### Arguments
1. `minLength: CGFloat? = nil` - The minimum length this spacer should try to respect. If `nil` is provided then a system default spacing is used instead.

###### Usage
See [usage](#Usage) examples above to see how this initializer can be used.

--- 
#### Instance Properties
```swift
var minLength: CGFloat?
```

Represent the minimum length of this spacer. If `nil`, a system default spacing is used.