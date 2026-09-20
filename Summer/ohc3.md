# ohc3.css design notes

`ohc3.css` is a visual refresh of the existing `ohc2.css`. It changes presentation only; the HTML structure, content, links, W3.CSS dependency, and existing navigation behaviour remain intact.

## What changed

- Introduced a small set of CSS custom properties for the club red, charcoal, neutral backgrounds, borders, and shadows.
- Replaced the older fixed typography with a readable system font, improved line height, and responsive heading sizes.
- Added a restrained page background and a centered content card with a red accent, rounded corners, and a subtle shadow.
- Improved navigation contrast and hover feedback while retaining the existing W3.CSS menu and dropdown markup.
- Styled tables with clearer spacing, a stronger header row, subtle zebra striping, borders, and row hover feedback.
- Improved link visibility with accessible colour contrast and underlines that appear on focus/hover.
- Added responsive rules for smaller screens, including a full-width content card and horizontally scrollable tables.
- Kept the existing `.oly-*`, `.w3-*`, and content classes so other saved pages or shared markup are not affected by this stylesheet alone.
