# Coffee Nerd - Profile Tab Description

## Tab Overview
The Profile Tab acts as the app's personalization and configuration center, allowing users to customize their experience with avatars, names, themes, and font sizes, while providing access to settings and about information. Accessed via the bottom tab bar (icon: avatar silhouette with "Leather" framing and "Brass" outline, or a person icon with metallic accents), it presents a simple, vertically scrollable form-like layout drawing from local storage for instant, offline adjustments. This tab evokes a personalized frontispiece in a leather-bound coffee journal, featuring "Old Paper" backgrounds with subtle "Coffee Ring" stains, "Leather" textures on sections and buttons, and "Brass" highlights on selectors and icons, fostering a premium, library-inspired customization space that aligns with the app's privacy-centric ethos.

All changes save locally via SQLite, with no data transmission. The tab integrates Settings & About as a nested or expandable section, keeping the interface minimalist and accessible through scalable elements, high-contrast options, and haptic feedback on updates. It serves as a low-frequency utility tab, enhancing overall usability without core feature overlap.

## Key Components
- **Avatar Selection**:
  - Grid picker of fun coffee-themed cartoon avatars (e.g., animated beans, mugs, baristas; stored as local PNG/SVG assets with "Brass" borders).
  - Option to upload custom photo from device gallery/camera (circular crop, compressed <1MB, framed with "Leather" edging).
  - Current avatar displayed prominently at top (e.g., large circle with old paper background).

- **Name Field**:
  - Optional free-text input for user name (e.g., "Brian the Coffee Nerd"), with placeholder prompt on "Old Paper" texture.
  - Used for subtle personalization (e.g., journal headers if implemented), but fully optional.

- **Theme Preference Selector**:
  - Segmented control or radio buttons (brass-styled) for Light, Dark, or System modes.
  - Instant preview: Applies changes app-wide with a subtle fade animation and haptic confirmation.

- **Font Size Selector**:
  - Slider or dropdown (leather-textured) with options: Small, Default, Large, Extra Large.
  - Dynamic scaling applies immediately, ensuring accessibility compliance.

- **Settings & About Section**:
  - Expandable accordion or nested navigation link (brass arrow icon).
  - Appearance settings (redundant with theme/font for quick access).
  - About page details:
    - App name & version (dynamic from build info).
    - Install date & source (queried locally).
    - Privacy statements: “All data stored locally on this device” and “No data collected or transmitted” (static text with emphasis).
    - Privacy policy link (opens external browser if URL provided).
    - Credits (e.g., developers, libraries; scrollable list on old paper).

- **Empty/Custom States**:
  - Default view shows placeholders (e.g., generic avatar with coffee ring stain) and gentle prompts to personalize.

## User Interactions
- **Core Flow**: Switch to Profile → View current settings → Edit avatar (grid modal or picker) → Update name/theme/font → Changes apply instantly with haptic; navigate to Settings for deeper info.
- **Personalization Flow**: Select avatar → Confirm upload/crop (haptic on save); adjust theme → App refreshes visually.
- **Cross-Tab Links**: Minimal; theme/font changes propagate globally, affecting all tabs without navigation.
- **Error Handling**: Photo upload failures (e.g., permissions): Prompt modal with settings link; invalid inputs gracefully ignored.
- **Performance**: Lightweight local reads/writes; no heavy computations for snappy response.

This tab empowers user-driven customization, weaving thematic design with practical controls for a tailored, fully private app experience.
