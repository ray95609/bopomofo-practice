## Context

The current sticker system relies on modern CSS (`aspect-ratio`) and automatic SVG sizing within Flexbox. However, these features behave inconsistently or are unsupported on older iPad devices and specific versions of Safari. The most critical issue is the "white box" bug where SVGs collapse to 0x0 size in WebKit when injected dynamically via `innerHTML` into a relative-sized Flexbox container.

## Goals / Non-Goals

**Goals:**
- Ensure stickers render correctly as icons instead of empty boxes on Safari.
- Maintain visual consistency across modern and legacy devices.
- Fix broken backdrop blur effects on Safari.

**Non-Goals:**
- Redesigning the sticker system or collection logic.
- Adding new stickers or animations.

## Decisions

### 1. Explicit SVG Dimensions
- **Decision**: Add `width="100%"` and `height="100%"` attributes to the `<svg>` root tag in the `getStickerSVG` function.
- **Rationale**: WebKit browsers (Safari) often fail to calculate the intrinsic size of SVGs inside Flex/Grid containers when only a `viewBox` is provided. Explicit percentages force the engine to fill the container.
- **Alternatives**: Using fixed pixel sizes (unsuitable for RWD) or using `<img>` tags with Data URIs (more complex to generate).

### 2. Aspect Ratio Fallback
- **Decision**: Use `min-height` and `width` on `.sticker-item` as a safe fallback for `aspect-ratio`.
- **Rationale**: `aspect-ratio` is only supported in Safari 15+. For older iPads, the container collapses without it.
- **Implementation**: Set `width: 100%` and a base `min-height` (e.g., 80px) or use the padding-bottom hack if perfect squareness is required on old devices.

### 3. Vendor Prefixes for Backdrop Filter
- **Decision**: Add `-webkit-backdrop-filter` to all elements using `backdrop-filter`.
- **Rationale**: Safari still requires the `-webkit-` prefix for backdrop filters to work.

### 4. SVG Display Mode
- **Decision**: Set `display: block` for SVGs inside `.sticker-svg-container`.
- **Rationale**: Default `inline` display can sometimes introduce unwanted whitespace or baseline shifts in Safari that interfere with centring.

## Risks / Trade-offs

- **[Risk]** Explicit width/height on SVG might interfere with some CSS overrides. → **Mitigation**: Keep CSS selectors specific and test on Chrome/Firefox to ensure no regression.
- **[Risk]** `min-height` fallback might not result in a perfect square on all screens. → **Mitigation**: Use `80px` as a sensible minimum for the grid layout defined in the CSS.
