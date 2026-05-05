## Why

Stickers in the collection book appear as empty white boxes on Safari (iOS/macOS) devices. This is caused by a known WebKit rendering bug where SVGs inside Flexbox containers collapse to zero size if they lack explicit width/height attributes. Additionally, legacy iPad devices running iOS < 15 do not support `aspect-ratio`, causing the grid items to have zero height.

## What Changes

- **SVG Fix**: Add explicit `width="100%"` and `height="100%"` attributes to all dynamically generated sticker SVGs.
- **CSS Compatibility**:
  - Add fallback height/width for `.sticker-item` to support devices without `aspect-ratio`.
  - Add `-webkit-backdrop-filter` for proper blur effect on Safari.
  - Set `display: block` on SVG elements to ensure stable rendering in Flexbox.

## Capabilities

### New Capabilities
- None

### Modified Capabilities
- `sticker-book-ui`: Update UI rendering logic to ensure cross-browser compatibility for SVG icons.

## Impact

- `index.html`: Styles and JavaScript logic for sticker rendering will be updated.
- No changes to API or data structures.
