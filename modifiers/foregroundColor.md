# Foreground Color
A modifier that controls the foreground color of the view that it is applied on.

---

> UIKit equivalent: `UILabel.textColor: UIColor`, `UIImageView.tintColor: UIColor!`
>
> Available since: iOS 13.0, macOS 10.15, macOS Catalyst 13.0, tvOS 13.0, watchOS 6.0, Xcode 11.0

**Tags:** `Cascading`, `Rendered` _[What does this mean?](/modifiers/README.md#tags)_

### Declarations
```swift
func foregroundColor(_ color: Color?) -> some View

// `Text` provides a custom override.
func foregroundColor(_ color: Color?) -> Text
```

###### Arguments
1. `color: Color?` - The color to use for the foreground.

### Overview
A modifier that controls the foreground color of the view that it is applied on. What this means varies based on the type of view that it is applied on.
- When applied on a `Text` or another view which has a text based view inside of it, be it a container or a view such as a `TextField` or `Button`, then the `foregroundColor` modifier affects the color of the text.
- When applied on a `Shape` or a container that contains a `Shape` inside of it, the `foregrouncColor` modifier will set the fill color of the shape.
    - Note that a similar effect can be achieved for `Shape`s using their `fill` modifier. 
- When applied on an `Image` or a container that contains an `Image` inside of it, then `foregroundColor` modifier will set the tint color of template images such as an SF Symbols image.

### Usage
Below is a simple example of how the `foregroundColor` modifier can be used to alter a `Text`'s text color.
```swift
// Creates red-colored Text
Text("Hello World!")
    .foregroundColor(.red)
```

Here's another example of how the `foregroundColor` modifier can be used to control a shape's fill color.
```swift
// Creates a blue Rectangle 
Rectangle()
    .frame(width:150, height: 100)
    .foregroundColor(.blue)
```

Here's another example demonstrating how the `foregroundColor` modifier can be used for fine control of styling your views.
```swift
Button(action: {}) {
    ZStack {
        RoundedRectangle(cornerRadius: 15)
            .foregroundColor(.green)
        
        HStack {
            Image(systemName: "plus")
                .foregroundColor(Color.white.opacity(0.5))
            Text("Hello There!")
        }
    }
}
.foregroundColor(.white)
```
