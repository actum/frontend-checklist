# Frontend Checklist

## Contents
* [1. Before development](#user-content-1-before-development)
* [2. During development](#user-content-2-during-development)
* [3. After development](#user-content-3-after-development)

## 1. Before development

## 1.1. UX Output
**Frontend developer should see the design before it goes to the client for approval. In this way we can prevent asking the client for repetitive approvals, if we have to change the design because of some technical issues, design issues etc.**

### 1.1.1. Graphic sources

The quality of the source files is important for the collaboration between FE developers and designers.
* Designer should keep consistency in colors, font sizes, paddings, margins etc. among all the files and components.
* Designer should avoid using decimal numbers, e.g. `20,45px`

#### Outcomes

* Consistency in design makes consistency in the code. The latter results in smaller source size, proper reusability and stable QA testing.

### 1.1.2. Responsive design

* Start and follow **mobile-first design**.
* Ensure component's consistency. When simple list of items becomes tabbed carousel on mobile it is most likely a wrong solution. However, this problem is self-eliminated when following mobile-first approach.
* Designer has to provide design in all predefined viewports.
* Designer should use Sketch pages as actual web pages and artboards as different viewports of the pages. It makes it easier to see the differences between mobile/tablet/desktop versions of the page in one screen.
* For default grid, designer can use [Bootstrap grid for Sketch](https://sketchrepo.com/free-sketch/bootstrap-4-grid-freebie/). In case design requires a custom grid, it should be acknowledged and aligned with the developer before development process begins to prevent unnecessary implementations.

**Default Bootstrap 4 grid**

| | Extra small `<576px` | Small `≥576px` | Medium `≥768px` | Large `≥992px` | Extra large `≥1200px` |
|-|----------------------|----------------|-----------------|----------------|-----------------------|
| Max container width (with padding!) | None (auto) | 540px | 720px | 960px | 1140px |

> When creating grid, beware that the basic `.container` width has **padding included!**.

> For example: gutter = 30px (15px each side) so `.container` width on **Extra large screen** is `1140px - 30px = 1110px`

### 1.1.3. Styleguide

We prefer [Atomic design](http://atomicdesign.bradfrost.com/), based on [Bootstrap framework](https://v4-alpha.getbootstrap.com/)
Styleguide describes all elements and components, their behavior, style, usage and code snippets.

* Colors
	* with examples where used, e.g. text-color, link-color, body-bg-color, primary-color, etc.
	* provide hexadecimal code: `#4285f4` or RGBA: `rgba(34, 34, 34, .3)` for transparency
	* if possible, use lowercase hexadecimal code `#fff` instead of `#FFF`
* Buttons - including `:hover`, `:focus`, `:active`, `:disabled` states
* Typography for all viewports!
	* headings – h1 to h4 (h5-h6 - if applicable)
	* paragraphs and links
	* line height, margins - possibly following a [vertical rhythm](https://www.gridlover.net/)
* Form elements
	* `:focus` state
	* validation with errors
* Lists (ordered, unordered, definition) – 3 levels
* Tables - if applicable

#### Outcomes

* All elements are defined and reusable, without need for additional development.

### 1.1.4. Forms

* Avoid styling of the following elements: `checkbox`, `radio`, `select` on mobile (touch) devices. The native implementation is the best for the user experience.
* Provide validation states (valid/invalid states, error message placement - animation if applicable)

#### Example

* If the custom style is required, then all of the following styling must be defined:
	* default state
	* checked (radio, checkbox) state
	* open state (select)

### 1.1.5. Design

* Links: `hover`/`focus`/`active`/`visited` state
* Buttons: `hover`/`focus`/`active`/`disabled` states
* 404 page and other error pages
* Prepare favicon, touch icons, OG image etc. (see [http://realfavicongenerator.net](http://realfavicongenerator.net))
* Ajax loading icon (preferably [CSS animation](https://projects.lukehaas.me/css-loaders/), or SVG when it is supported in IE11+)

#### Outcomes

* Developer does not to need guess/design the missing states and no additional iteration of design process is needed.

### 1.1.6. Design should contain the real content

* Adjust the text line height for languages with diacritic (Czech), especially in the headlines
* Design for **variable text length**, prepare a version with longer text, if it's gonna wrap on a new line or it should be truncate text with `...` in the end.
* Design for variable images (height/width/ratio) in case of user uploaded image
* Design should be provided for the empty state (example: empty search result; no user profile photo/description)

#### Example

* Do not use "Lorem ipsum…", if real content is not available, use some [real text generator](http://meettheipsums.com/)
* It should be specified and clear in the design which containers should have equal heights, and which should be fluid (flexible)

### Outcomes

* Decreasing the possibility of broken page layout

### 1.1.7. Fonts

* Consider how many fonts and variants (bold, black, light,…) to use *(for better performance 2-3 types are recommended)*
* Custom fonts will increase the page loading time (critical on mobile devices)
* Define the fallback font in case the custom font does not load
* Where the fonts will be hosted? ([Google fonts](https://fonts.google.com/), [Typekit](https://typekit.com/), [Fonts.com](https://www.fonts.com/), self hosted - if so, provide the source files and make sure that the correct licence is used)
* Does the font support all the necessary characters?

#### Outcomes

* Fast page load

#### 1.1.8. Icons - TODO: check https://fvsch.com/code/svg-icons/how-to/#section-styling

* Preferred format: `SVG`
* Icon system - [https://css-tricks.com/icons-and-teams/](https://css-tricks.com/icons-and-teams/)

1. Icon shapes are grouped semantically.
    * if the shapes have the same `fill` attribute and it should change e.g. on hover, it should be in one `<g>` group tag (*represents a folder in graphic editor*)
    * if the icon shouldn’t change it’s `fill`, `stroke`, etc., all the shapes should be in one `<g>`
    * all groups, paths, shapes, etc. should have semantic/meaningful name (*e.g. head, eyebrows, left-arm, right-arm, etc.*)
        * more words should be connected with dash `-`
        * should be in English, no special characters
2. Icon shouldn't have `mask`
    * if you have an icon inside a circle and the inside shape is bigger, so that it overflows the circle, just use **subtract, intersect or difference** tool in Sketch or Illustrator, to cut the icon to it’s proper size and then use circle shape for the background
3. Icon and its shapes should have *no explicit* `fill`/`stroke`.
    * That means that there is no explicit color assigned to the icon's shapes in the graphic editor
    * Icon with no colors assigned looks black in the Finder
    * This is needed to dynamically change the color via CSS. When there is a custom color attached to the icon's shapes, it does not get overriden when applying CSS modifications.
    * Please see the example of a **proper** `cart` icon below:
    
```svg
<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
  <path d="M4,21a3,3,0,1,0,3-3A3,3,0,0,0,4,21Zm4,0a1,1,0,1,1-1-1A1,1,0,0,1,8,21Z"/>
  <path d="M16,21a3,3,0,1,0,3-3A3,3,0,0,0,16,21Zm4,0a1,1,0,1,1-1-1A1,1,0,0,1,20,21Z"/>
  <path d="M5.125,17h15.7l2.4-12H5.542L4.875,0H1V2H3.125ZM20.78,7l-1.6,8H6.875L5.809,7Z"/>
</svg>
```

As you see, there is no explicit `fill` or `stroke` attributes set anywhere. This example illustrates only the proper way to export icon with no color.

##### Outcomes

* Icons are crisp sharp on all screen sizes (devices/high screen density)

#### 1.1.9. User interactions

* Define the behavior of collapsing, read more and transitions or animations.
* If there are any more complicated interactive transitions or animations, designer should provide a working prototype, where FE developer can see the actual animation.

##### Example

* [Animations](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Animations)
* [UI-microinteractions](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/UI-microinteractions)
* [Possible list of prototyping tools](http://www.creativebloq.com/web-design/top-10-prototyping-tools-2016-21619216)

##### Outcomes

* Better user experience
* Consistency

## 1.2. Frontend Output

### 1.2.1. Browser compatibility

Matrix of supported browsers should be defined and agreed on with the client.

#### Outcomes

* QA engiers know which browsers to test in
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

### 1.2.2. Dev Stack

Use the latest versions of the [gulp dev stack](https://github.com/actum/gulp-dev-stack).
In case you need more features, add them within the project.
You can also [raise an issue on Github](https://github.com/actum/gulp-dev-stack/issues) and discuss an addition of the feature to the dev stack there.

#### Outcomes

* Best practices are ensured (structure, linting, …)
* No need to reinvent the wheel

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
* Focus state for links (accessible using keyboard)

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
