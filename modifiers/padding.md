# Padding (In Progress)
A modifier that adds padding around the view that it is applied on

---

> Available since: iOS 13.0, macOS 10.15, macOS Catalyst 13.0, tvOS 13.0, watchOS 6.0, Xcode 11.0

**Tags:** `Non-Cascading`, `Stacking` _[What does this mean?](/modifiers/README.md#tags)_

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


### Usage

### Visuals