# ohc4.css rationale

`ohc4.css` is a more expressive visual redesign of the Summer coaching page. It remains a CSS-only change: the existing HTML, text, imagery, W3.CSS dependency, and navigation markup are preserved.

## Why this should feel less flat

- The page now has a layered background, a dark gradient masthead, a warm red/coral accent gradient, and a subtle geometric masthead detail.
- The main content is presented as a large elevated paper-like card instead of a plain grey panel.
- The two main headings receive deliberately different scale: the page title becomes a strong editorial-style hero, while activity sections use coloured vertical markers and divider lines.
- Tables become distinct content components with elevated borders, rounded corners, stronger gradient headers, clearer row rhythm, and a warm hover state.
- Navigation gains a persistent top position, clearer weight, stronger hover feedback, and elevated dropdowns.
- Images receive consistent framing and depth so they participate in the layout rather than appearing as unstyled inserts.
- The responsive rules retain the visual hierarchy on small screens while allowing wide tables to scroll instead of breaking the page.

## Design principles

The palette combines the club's red with navy rather than using black and grey alone. Contrast is intentional: dark navy carries structure, red identifies club actions and headings, and coral/gold accents add energy associated with running and summer. Shadows and rounded corners are used sparingly to establish layers, not to decorate every element.

The stylesheet uses selectors already present in the saved page, so no HTML restructuring is required. Inline styles remain in the document, but the more specific `ohc4.css` rules provide the updated page-level presentation.
