# Font
Configure the font or font size used for text and images.

---

> UIKit equivalent: `UILabel.font`, `UITextField.font`
>
> Available since: iOS 13.0, macOS 10.15, macOS Catalyst 13.0, tvOS 13.0, watchOS 6.0, Xcode 11.0

**Tags:** `Cascading`, `Rendered` _[What does this mean?](/modifiers/README.md#tags)_

### Declarations
```swift
func font(_ font: Font?) -> some View

// `Text` provides a custom override.
func font(_ font: Font?) -> Text
```

###### Arguments
1. `font: Font?` - The font that should be used for the `Text` and `Image` view in this branch of the View hierarchy.

### Overview
The `font` modifier is used to control the font that should be used for a specific branch in a view hierarchy. Since it is a cascading modifier, it can be applied to containers, to easily set the font of multiple views at once. The modifier will be applied on all child views of the container that it is applied on.

The `font` modifier applies to both `Text` and `Image` views, controlling the font used for the `Text` view as well as the image size for `Image` views, when presenting a `.svg` image such as an [SF Symbol](https://developer.apple.com/design/human-interface-guidelines/sf-symbols/overview/) image.

The font to use is specified using a [`Font`](/views/docs_coming_soon.md) object. Check the documentation page for [`Font`](/views/docs_coming_soon.md) to find out the possible built-in values as well as how to specify custom fonts.

### Usage

Here's a simple example of setting the font size of two `Text` views. The first `Text` view will have a font size suitable for footnotes, while the `Text` view right under it will have a font size suitable for large titles.
```swift
VStack(alignment: .leading) {
    Text("Welcome to")
        .font(.footnote)
    
    Text("My Awesome App")
        .font(.largeTitle)
}
```

Here's another example demonstrating the cascadability of the font modifiers.
```swift
List(contacts) { contact in
    Image(systemName: "person.fill")

    Text(contact.name)
}
.font(.title)
```
The above example creates a list that displays the names of the user's contacts. Since the `font` modifier is applied on the list rather than the individual views inside the list, each row will have its font set to size `title`. Notice that the font size is also applied on the `Image` view, since it uses an SF Symbols image.

> **Note:** This is standard behaviour for **Cascading modifiers**. To learn more about this, checkout the [View Modifiers](/modifiers/README.md#tags) page.