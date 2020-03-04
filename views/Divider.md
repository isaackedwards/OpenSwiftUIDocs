# Divider
A view that is used to create a visual separator in your layout.

---

> Available since: iOS 13.0, macOS 10.15, macOS Catalyst 13.0, tvOS 13.0, watchOS 6.0, Xcode 11.0

### Declaration
```swift
struct Divider: View
```

### Overview
This view renders a visual separator in your layout, and can be used to logically separate you layout into sections or parts. It renders almost the same on each platform.

The divider consist of a single, straight line, typically one pixel in width. It will orient itself appropriately based on the context that it's used in. For example if placed inside a `VStack`, the divider will appear as a horizontal line. Where as if it is used inside an `HStack`, it will render as a vertical line instead.

A divider will typically take all of the provided space along the axis of its line, making the separator line as long as possible.

> **Note:** While it is possible to constrain a divider within a specific size using a `frame` modifier, there is currently no known way to change the thickness of a divider. For dividers with a custom width, consider utilizing shapes such as a `Rectangle`.

### Usage
Since dividers are very simple views with only a single initializer, they are very straightforward to use. Below is an example of how a divider can be used to visually separate two `Text` views.
```swift
VStack {
    Text("Part 1")
    Divider()
    Text("Part 2")
}
```

### Visuals
A divider usually always renders the same way on all platforms. An example image is shown below.

![An example divider](/../images/views/divider/divider-simple.png)

## Topics

---
#### Creating a divider

```swift
init()
```
The only initializer of a `Divider` view.