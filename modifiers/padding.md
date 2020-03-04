# Padding
A modifier that adds padding around the view that it is applied on

---

> Available since: iOS 13.0, macOS 10.15, macOS Catalyst 13.0, tvOS 13.0, watchOS 6.0, Xcode 11.0

**Tags:** `Stacking`, `Rendered` _[What does this mean?](/modifiers/README.md#tags)_

### Declarations
```swift
func padding(_ length: CGFloat) -> some View
```
###### Arguments
1. `length: CGFloat` - The length of the padding to add to each side of the view.

---

```swift
func padding(_ insets: EdgeInsets) -> some View
```
###### Arguments
1. `insets: EdgeInsets` - The `EdgeInsets` object that specifies how much padding to add to each side of the view.

---

```swift
func padding(_ edges: Edge.Set = .all, _ length: CGFloat? = nil) -> some View
```
###### Arguments
1. `edges: Edge.set = .all` - The edges that should be padded.
2. `length: CGFloat? = nil` - The length of the padding to apply to that side. If no value or a value of `nil` is provided then a system default length is used.

### Overview
The `.padding` modifier is used to add insets to a view. The kind of padding that should be added is specified by you, and SwiftUI provides two ways for you to do so.
- You can specify the sides that should be padded, and how much they should be padded by. You can also pass groups of sides such `.horizontal` or `.all`. This gives less control but you seldom need to specify a different padding for each side.
- Alternatively you can pass in an `EdgeInsets` struct, specifying exactly how much padding each side must have. This gives you fine control of your padding but you must provide a value for each side.

If you pass in no arguments, then the view will be padded on all four sides with a system default padding amount.

Most view by default start out with a padding of zero. There are exception of course, such as `List` view adding a default padding to each one of its rows (the same goes for `Form`), as well as others.

`.padding` is a stackable modifier. They way it stacks is when there are multiple `.padding` modifiers added to a view, each instance will add additional insets of top of the previous `.padding` modifier. For example, the following code will results in a padding of 12 for the top side of the `Text` view.
```swift
Text("Hello World!")
    .padding(.top, 8)
    .foregroundColor(.accentColor)
    .padding(.top, 4)
```

> **NOTE:** The `.padding` modifier alters the frame of the view by making it larger.

### Usage
Here is how one would add the system default padding to a view.
```swift
Text("Hello World!")
    .padding()
```

Here is another example. This time we would like more precise control of our padding, setting one value for the horizontal edges, and another value for the vertical ones.
```swift
Text("Hello World!")
    .padding(.horizontal, 20)
    .padding(.vertical, 10)
```

For even more fine control we can pass an `EdgeInsets` object to the `.padding` modifier, as shown below.
```swift
Text("Hello World!")
    .padding(EdgeInsets(top: 2, leading: 10, bottom: 15, trailing: 0))
```

Note, that the same effect can be achieved by stacking three padding modifiers, as shown below.
```swift
Text("Hello World!")
    .padding(.top, 2)
    .padding(.leading, 10)
    .padding(.bottom, 15)
```

### Visuals
Here's an example depicting the difference in views' frames with and without padding. The red border highlights the views' borders.

![Example of a view with and without a padding modifier](/../images/modifiers/padding/padding-example.png)