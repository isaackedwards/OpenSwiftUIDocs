# View Modifiers

This section contains documentation for SwiftUI's various view modifiers.

## Overview
> // Go over the basic of view modifiers in SwiftUI. How they're applied and how they really work behind the scenes (`ViewModifier` and `.modifier`, and views wrapping views and all that), part of this documentation may need to be shared or moved to the `ViewModifier` page.
> 
> // Touch upon the fact that modifiers return new views (and that's what the official docs take into account), however in this documentation that fact is skipped over, and rarely mentioned. Modifiers are discussed as simply effects applied on a view, not as functions returning your original view, embedded in another view.

### Tags
Throughout this documentation website you will see a number of tags applied onto view modifiers. These tags are meants to be a quick way to convey some important information about the view modifiers. While some of them may be self-explanatory to some, below is a definition for each view modifier tag that you might encounter on this website.

* **Cascading:** - A cascading modifier is a modifier that cascades down to child views when applied onto a container view. 
  * For example, What this means is that if a `foregroundColor` modifier was to be applied to a `Group` view, then all child views of that `Group` view will get the `foregroundColor` effect as well. That is unless they themselves have a `foregroundColor` modifier applied to them, in which case the modifier applied to the child view takes precedence over the container view's one.
* **Stacking:** - A stacking modifier is one that can be applied to a view multiple times and have an effect on the view each time it is applied. 
  * For example, a `frame` modifier is a stacking modifier, since it can be applied onto a view multiple times, and each time an additional frame will be created around the view. However a `foregroundColor` modifier is non-stacking, since it can only be applied once. If it is applied more than once then only the top-most instance takes precendence.
* **Rendered:** - A rendered modifier is a modifier which will directly modify how the view is rendered. These are modifers which directly alter a view's appearance on screen.
  * For example. a `foregroundColor` is a rendered modifier, because it clearly changes how the view is rendered by altering its text color, among other things. An `environmentObject` modifier on the other, does not directly modify how the view is presented (even if it might do so, indirectly, due to your implementation).
  > // Needs a better name