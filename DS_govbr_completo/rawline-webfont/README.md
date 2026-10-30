# Rawline Webfont

[![npm](https://img.shields.io/npm/v/rawline-webfont?color=brightgreen)](https://www.npmjs.com/package/rawline-webfont)

The CSS and web font files to easily self-host the “Rawline” font. 

## Quick Installation

This package offers multiple methods to import the CSS, including using a bundler like Vite or using SASS. 

It was generated using [Fontsource CLI](https://www.npmjs.com/package/@fontsource-utils/cli), for complete documentation, see the [Fontsource docs](https://fontsource.org/docs/getting-started/introduction).

```javascript
npm install rawline-webfont
```

Within your app entry file or site component, import it in.

```javascript
import "rawline-webfont"; // Defaults to weight 400
import "rawline-webfont/400.css"; // Specify weight
import "rawline-webfont/400-italic.css"; // Specify weight and style
```

Supported variables:
- Weights: `[100,200,300,400,500,600,700,800,900]`
- Styles: `[italic,normal]`
- Subsets: `[cyrillic,cyrillic-ext,latin,latin-ext,vietnamese]`

Finally, you can reference the font name in a CSS stylesheet, CSS Module, or CSS-in-JS.

```css
body {
  font-family: "Rawline";
}
```

## Licensing

Copyright (c) 2010 - 2013, Matt McInerney (matt@pixelspread.com), Pablo Impallari (impallari@gmail.com), Rodrigo Fuenzalida (hello@rfuenzalida.com) with Reserved Font Name RALEWAY. 

Copyright (c) 2016, Henrique Ibaldo (hi@ibaldo.co), with Reserved Font Name RAWLINE.
[OFL-1.1](https://openfontlicense.org)

## Other Notes
Font version (provided by source): `be0e9077d2ae8140db4b2127ff7ba12daba46469`.

---
Created with [Fontsource CLI](https://www.npmjs.com/package/@fontsource-utils/cli)