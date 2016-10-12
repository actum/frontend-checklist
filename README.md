# frontend-checklist

# Before development starts
## Browser compatibility
Browser matrix should be defined and agreed on

## Code conventions
* Make sure dev stack is set up (eslint etc.)
* CSS naming conventions ([http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/CSS-Guidelines](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/CSS-Guidelines), [http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Coding-style](http://intranet/Wiki-Actum/Development/Front-end/Best-Practice/Coding-style)
* Living styleguide (based on styleguide from designers)

## Graphic sources
* File format (PSD, version, multiple files?, …)
* What will be designed – desktop, responsive?
* color codes (hex / rgba)
* font family(ies) - from where (Google fonts/Typekit/Fonts.com) - who pays for the licence?
* hover/focus/active/disabled states of buttons
* form fields - validation
* styled form fields - select/radio/checkbox - all states (expanded, collapsed)
* links (hover/active/visited?)
* empty state (example: empty search result; no user profile photo)
* 404 page and other error pages
* design for variable text lenght
* design for variable images (height/width/ratio) (user uploaded image)
* text line-height - think about languages with diacritcs so that lines do not overlap - especially for headlines

## Styleguide
We prefer atomic design, based on Bootstrap [http://getbootstrap.com/](http://getbootstrap.com/)
* headings – h1 to h6
* paragraphs and links
* lists (ordered, unordered, definition) – 3 levels
* tables
* images, linked images
* form (styling consult with coder and PM)
* error messages (form error messages)
* pagination
* buttons (1 or 2 or 3 versions - but nowhere use 4th version)
* lightbox
* colors (hexadecimal code: #4285f4)
* No font antialiazing in the PSD (no crisp/sharp/smooth style)
* User interactions (collapsing, read more, animations)
* Favicons, touch icons, OG image etc. (see [http://realfavicongenerator.net](http://realfavicongenerator.net)
* Icon system - [https://css-tricks.com/icons-and-teams/](https://css-tricks.com/icons-and-teams/)

# Development in progress
TODO

# Development finished
## Browser compatibility
* Test in supported browsers and devices
## Performance
* PageSpeedInsights (https://developers.google.com/speed/pagespeed/insights/)
* Minified production build for CSS, JS, SVG
