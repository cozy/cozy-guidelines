# GUI Guidelines

Note: This is a quick and dirty version of the GUI guidelines, and will be improved as long as the project evolves :].


## Fonts

To match the Cozy branding, these fonts are recommended:

- titles: Source Sans Pro
- titles and labor: Source Sans Pro
- fixed-width: Source Code Pro

### How to use it?

Fonts should be used as served by the proxy. To do it, simply add this line in the `<head/>` section of your webapp page:

```html
<link rel="stylesheet" href="/fonts/fonts.css">
```

Note that the file is served from the root base (`/`) which means that the proxy will respond from this URL, and not your webapp. This use will CDNize the file for the platform. You can embed the fonts in your app if you want for development purposes by cloning the [fonts directory](https://github.com/cozy/cozy-proxy/tree/master/client/app/assets/fonts).

Then, you can simply use the `font-family` declarations as provided by the _fonts_ file:

```css
body {
    font-family: 'Source Sans Pro', sans-serif;
}

h1, h2, h3 {
    font-family: 'Maven Pro', sans-serif;
}

pre, code {
    font-family: 'Source Code Pro', monospace;
}
```

Note that the file only _declares_ the font-faces, and not set their use (as the example below does).

### Weights and styles

The fonts comes with the following styles:

- Source Sans Pro:
    - Regular
    - Bold
    - Italic
    - Bold italic

- Maven Pro
    - Regular
    - Bold

- Source Code Pro
    - Regular
    - Bold


## Icons

The fonts.css file (see section below) comes with and up-to-date version of [Font Awesome](http://fortawesome.github.io/Font-Awesome/) ready to use.

### How to use it?

To display an icon, simply declares an element with the class `fa`. Convention use the `<i/>` element, but you can use it everywhere. Icon is drawn in the `:before` pseudo-element. List of icons is [available here](http://fortawesome.github.io/Font-Awesome/icons/).


### Label in icon

Icons are generally use as follow:

```html
<button><i class="fa fa-trash"></i> Delete</button>
```

You sometimes just want an icon, but the text should remain available (i.e. for accessibility purposes), just you don't want it to be rendered on screen. In this case, the `fonts.css` declares a trick that will render the content of an icon element with the [Adobe Blank](https://github.com/adobe-fonts/adobe-blank) font (that is… well… just a blank font). So you just need to embed your label in the icon to mask it:

```html
<button><i class="fa fa-trash">Delete</i></button>
```

or, more simple:

```html
<button class="fa fa-trash">Delete</button>
```
