# Frontend Checklist

## Before development

### Browser compatibility

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

### Dev Stack

Use the latest versions of the [gulp dev stack](https://github.com/actum/gulp-dev-stack).
In case you need more features, add them within the project.
You can also [raise an issue on Github](https://github.com/actum/gulp-dev-stack/issues) and discuss an addition of the feature to the dev stack there.

#### Outcomes

* Best practices are ensured (structure, linting, …)
* No need to reinvent the wheel

### Graphic sources

* File format (PSD, version, multiple files?, …)
* What will be designed – desktop, responsive?
* font family(ies) - from where (Google fonts/Typekit/Fonts.com) - who pays for the licence?
* form fields - validation
* styled form fields - select/radio/checkbox - all states (expanded, collapsed)
* links (hover/focus/active/visited?)
* buttons: hover/focus/active/disabled states
* empty states (example: empty search result; no user profile photo)
* 404 page and other error pages
* design for variable text length
* design for variable images (height/width/ratio) (user uploaded image)
* No font antialiasing in the PSD (no crisp/sharp/smooth style)
* text line-height - think about languages with diacritcs so that lines do not overlap - especially for headlines
* Prepare favicon, touch icons, OG image etc. (see [http://realfavicongenerator.net](http://realfavicongenerator.net)

### Styleguide

We prefer [Atomic design](http://atomicdesign.bradfrost.com/), based on [Bootstrap framework](http://getbootstrap.com/)

* headings – h1 to h6
* paragraphs and links
* lists (ordered, unordered, definition) – 3 levels
* tables
* images
* form (styling consult with coder and PM)
* error messages (form error messages)
* pagination
* buttons (1 or 2 or 3 versions - but nowhere use 4th version)
* components (lightbox, …)
* colors (hexadecimal code: #4285f4 or RGBA for transparency)
* User interactions (collapsing, read more, animations)
* Icon system - [https://css-tricks.com/icons-and-teams/](https://css-tricks.com/icons-and-teams/)

---

## During development

### Best Practices

* Write the code according to best practices [http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Coding-style](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Coding-style)
* Use our CSS naming conventions ([http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/CSS-Guidelines](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/CSS-Guidelines)
* Maintain living styleguide using the dev stack
* Make sure favicon, touch icons, OG images are implemented

### Accessibility

* Write valid code
* Keep the code semantic (use headings, paragraphs, etc. where appropriate)
* Alt text for images
* Focus state for links
* `TODO more?`

---

## After development

* Add readme.md with info how to use dev stack etc.

### Browser compatibility

* Test in supported browsers and devices

### Browser compatibility

* Test in supported browsers and devices

### Performance

* PageSpeedInsights (https://developers.google.com/speed/pagespeed/insights/)
* Minified production build for CSS, JS, SVG
