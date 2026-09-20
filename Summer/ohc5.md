# ohc5.css rationale

`ohc5.css` preserves the stronger visual design from `ohc4.css` and applies the requested colour and contrast changes through a small override layer.

## Changes

- Replaced the dark navy palette with true black for the masthead, navigation, and dropdown surfaces.
- Brightened the red from `#b32135` to `#e21d3f` and the coral from `#ed6a5a` to `#ff594f` for more energy and visibility.
- Deepened the supporting red to `#b5092a` so gradients retain enough contrast against bright red.
- Set all text on red surfaces to bold white, including the red utility bar, table header rows, header links, and red navigation hover states.
- Increased shadow contrast slightly so the white content card still separates clearly from the black and brighter colour treatment.

The file is standalone and contains the page layout, responsive behaviour, component styling, and colour overrides directly. It no longer depends on `ohc4.css`, so the HTML has a single stylesheet dependency for this design.
