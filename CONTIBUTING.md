# Contributing

So you'd like to contribute. Great! We'd like to make it as simple as possible for you to get started. Which is why we've dedicated this page to describing just how to do that. 

Start by heading over to the [project's repository](https://github.com/sketch204/OpenSwiftUIDocs) and cloning it. While you are doing that, also take a look at [docsify](https://docsify.js.org/#/). This is the site generator that is used for this project.

To get started it is recommended that you install their CLI tool, using `npm i docsify-cli -g`. Once that is done you can host the website locally by running `docsify serve` in the project directory. 
> **Note:** Running the `npm` command requires that you have [node.js](https://nodejs.org/en/) installed.

Alternatively, if you don't want to install node, or the node module, you can host the website locally by running `python -m SimpleHTTPServer 3000` in the project directory, assuming you have `python` installed. 

> **Note:** While you get the same functionality this way, hosting the website using the docsify CLI also gives you live reload anytime you save a file in the project directory.

### Project Structure

> **Note:** This documentation is not yet complete. Hence, the structure of the website may change as more documentation is added.

There are 3 main sections to this website; the Views section, the View Modifiers section and the Data section. 

The Views sections contains documentation pages for any views `SwiftUI` offers. This is also the place where the `View` protocol documentation resides.

The View Modifiers sections contains documentation pages for every view modifier that `SwiftUI` has. The `ViewModifier` protocol is also documented here.

The Data section contains documentation on all data related objects of `SwiftUI` such as `State` or `FetchRequest`.

Each section is contained inside its respective folder in the root directory of the project. Everything else, such as this page, or the homepage are stored as siblings to the section folders.

Every section directory, along with the root directory, contain a `_sidebar.md` and a `_navbar.md` files. These files correspond to the sidebar and the navbar of their respctive section/directory. For more info on their syntax or how to use them, checkout docsify's documentaion on [sidebars](https://docsify.js.org/#/more-pages?id=sidebar) and [navbars](https://docsify.js.org/#/custom-navbar?id=markdown).

Additionaly, every section directory must have a `README.md` file. This file acts as the home page for that section.

> **Note:** In the root directory of the project you will find an empty `.nojekyll` file. This file is necessary to make GitHub not ignore files whose names start with an underscore (`_`).

### Page Structure

Every documentation page follows a strict format. Mostly this format dictates the contents of the header of the page and the order of the sections for a page. To make this website as easy to use as possible, we want to make sure that every page follows a familiar order in its content, so that users can find the right information as fast and as easily as possible.