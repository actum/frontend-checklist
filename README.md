# Frontend Checklist

## Contents
* [1. Before development](#user-content-1-before-development)
* [2. During development](#user-content-2-during-development)
* [3. After development](#user-content-3-after-development)

## 1. Before development

### 1.1. Browser compatibility

Matrix of supported browsers should be defined and agreed on with the client.

#### Outcomes

* QA engineers know which browsers to test in
* Developers know which features they can use

#### Example

| Device        | Platform/version | Browser       | Version      |
| ------------- | -------------    | ------------- | ------------ |
| Mobile        | iOS 8+           | Safari        | 9  and above |
|               | Android 4.4+     | Google Chrome | 53 and above |
| Tablet        | iOS 8+           | Safari        | 9  and above |
|               | Android 4.4+     | Google Chrome | 53 and above |
| Desktop       | Windows 8+       | MS IE         | 11           |
|               |                  | MS Edge       | 12 and above |
|               |                  | Google Chrome | 53 and above |
|               |                  | Firefox       | 47 and above |
|               | Mac              | Safari        | 9  and above |

### 1.2. Dev Stack

Use the latest versions of the [gulp dev stack](https://github.com/actum/gulp-dev-stack).
In case you need more features, add them within the project.
You can also [raise an issue on Github](https://github.com/actum/gulp-dev-stack/issues) and discuss an addition of the feature to the dev stack there.

#### Outcomes

* Best practices are ensured (structure, linting, …)
* No need to reinvent the wheel

### 1.3. Graphic sources

The quality of the source files is important for the collaboration between FE developers and designers.

#### Example

* The designer should follow [Photoshop Etiquette](http://photoshopetiquette.com/) when creating the source files.
* Do not use font antialiasing in the PSD (no crisp/sharp/smooth style) - it is not supported in the browsers.

#### Outcomes

* Consistency of colors, typography, spacing, …

### 1.4. Responsive design

* Define breakpoints: [Bootstrap example](http://getbootstrap.com/css/#grid-options)
* The file format should be agreed on between the designer and FE developer.

#### Example

* PSD - ensure that the file is compatible with Photoshop or [Avocode](https://avocode.com/)
* One file for each breakpoint (device)

### 1.5. Forms

* Avoid styling of the following elements: `checkbox`, `radio`, `select` on mobile (touch) devices. The native implementation is the best for the user experience.
* Provide validation states (valid/invalid states, error message placement)

#### Example

* If the custom style is required, then all of the following styling must be defined:
	* default state
	* checked (radio, checkbox) state
	* open state (select)

### 1.6. Design

* Links: `hover`/`focus`/`active`/`visited` state
* Buttons: `hover`/`focus`/`active`/`disabled` states
* 404 page and other error pages
* Prepare favicon, touch icons, OG image etc. (see [http://realfavicongenerator.net](http://realfavicongenerator.net))
* Ajax loading icon (preferably [CSS animation](https://projects.lukehaas.me/css-loaders/), or SVG when it is supported in IE11+)

#### Outcomes

* Developer does not need guess/design the missing states and no additional iteration of design process is neeeded.

### 1.7. Design should contain the real content

* Adjust the text line height for languages with diacritic (Czech), especially in the headlines
* Design for variable text length
* Design for variable images (height/width/ratio) in case of user uploaded image
* Design should be provided for the empty state (example: empty search result; no user profile photo/description)

#### Example

* Do not use "Lorem ipsum…"
* It should be specified and clear form in the design which containers should have equal heights, and which should be fluid (flexible)

### Outcomes

* Decreasing the possibility of broken page layout

### 1.8. Fonts

* Consider how many fonts and variants (bold, black, light,…) to use
* Custom fonts will increase the page loading time (critical on mobile devices)
* Define the fallback font in case the custom font does not load
* Where the fonts will be hosted? ([Google fonts](https://fonts.google.com/), [Typekit](https://typekit.com/), [Fonts.com](https://www.fonts.com/), selfhosted - if so, provide the source files and make sure that the correct licence is used)
* Does the font support all the necessary characters?

#### Outcomes

* Fast page load

### 1.9. Styleguide

We prefer [Atomic design](http://atomicdesign.bradfrost.com/), based on [Bootstrap framework](http://getbootstrap.com/).
Styleguide describes all elements and components, their behavior, style, usage and code snippets.

* headings – h1 to h6
* paragraphs and links
* lists (ordered, unordered, definition) – 3 levels
* tables
* images
* form elements
* error messages (form error messages)
* pagination
* buttons (1 or 2 or 3 versions - but nowhere use 4th version)
* components (lightbox, …)

#### Outcomes

* All elements are defined and reusable, without need for additional development.

#### 1.9.1. Icons

* Prefered format: `SVG`
* Icon system - [https://css-tricks.com/icons-and-teams/](https://css-tricks.com/icons-and-teams/)

##### Outcomes

* Icons are crisp sharp on all screen sizes (devices/high screen density)

#### 1.9.2. User interactions

Define the behavior of collapsing, read more, animations.

##### Example

* [Animations](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Animations)
* [UI-microinteractions](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/UI-microinteractions)

##### Outcomes

* Better user experience
* Consistency

#### 1.9.3. Colors

* provide hexadecimal code: `#4285f4` or RGBA: `rgba(34,34,34,.3)` for transparency

##### Outcomes

* Consistency

---

## 2. During development

### 2.1. Best Practices

* Write the code according to best practices [http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Coding-style](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Coding-style)
* Use our CSS naming conventions ([http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/CSS-Guidelines](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/CSS-Guidelines)
* Maintain living styleguide using the dev stack
* Make sure favicon, touch icons, OG images are implemented

### 2.2. Accessibility

* Write valid code
* Keep the code semantic (use headings, paragraphs, etc. where appropriate)
* Use alt text for images (at least leave the alt attribute empty, [read more](http://a11yproject.com/posts/alt-text/))
* Focus state for links
* `TODO more?`

---

## 3. After development

* Add readme.md with info how to use dev stack etc. Also put this info to the [project page in Intranet](http://intranet/Wiki-Actum/Development/Front-end/Projects).

### 3.1. Browser compatibility

* Test in supported browsers and devices ([1.1.](#user-content-11-browser-compatibility))

### 3.2. Performance

* Aim for the highest score on desktop and mobile in [PageSpeedInsights](https://developers.google.com/speed/pagespeed/insights/)
* Make sure that you serve the minified build of CSS, JS and SVG on production

#### Outcomes

* The pages load quickly.
* Better user experience.
