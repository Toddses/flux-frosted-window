# flux-frosted-window

A fully responsive component that contains an inner panel with a frosted glass window effect, blurring the background behind the window. There are several options for theming and positioning the element, and affecting it's behavior.

Check out the [Polymer Project](https://www.polymer-project.org/1.0/) for more information on using Polymer based Web Components.

## Install

So easy with [Bower](http://bower.io).

```sh
$ bower install --save flux-frosted-window
```

## Usage

```html
<flux-frosted-window auto-position>
    <h1>This is neat!</h1>
    <p>I love the internet!</p>
</flux-frosted-window>
```

## Attributes

Boolean attributes for changing the behavior.

* `auto-position` automatically positions the glass window

## Theming

All these custom properties are available, and their default values are listed.

```css
/*
Custom properties for both manual and auto positioning
*/

flux-flat-button {
    --background-image: none;
    --fallback-image: none;
    --background-position: center;
    --glass-blur: 5px;
    --gutter-right: 0;
    --gutter-left: 0;
    --glass-border: 0;
    --glass-border-radius: 0;
    --window-tint: rgba(0, 0, 0, 0.5);
}
```

**A note on the `--fallback-image` property** For full cross-browser support, you need to create a fallback image for browsers that don't support CSS filters (IE 10 and 11). Typically this will be the same background image with a blur effect manually applied. Photoshop's Gaussian Blur with the same value as your `--glass-blur` property generally produces similar results as the CSS filter.

```css
/*
Custom properties for manual positioning
For manual positioning, you must set at least one vertical and horizontal property
for the element to be positioned properly, but you can set all 4 for full control
*/

--component-height: 100vh;
--pos-top: auto;
--pos-right: auto;
--pos-bottom: auto;
--pos-left: auto;
```
```css
/*
Custom properties for auto positioning
*/

--padding-top: 0;
--padding-bottom: 0;
--glass-max-width: auto;
```

**A note on positioning and the gutters** For an auto-position component, you likely want to set a left and right gutter,
so your window doesn't get pushed all the way to the edge of the browser.
For manual positioning, you either want to set one side's gutter, or no gutter
at all. If you position both the left and right side, don't use any gutters.
If you position only one side, set a gutter on the opposite side and it won't
smush up on the edge of the browser.
