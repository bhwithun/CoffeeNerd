# Coffee Nerd - Journal Tab Description

## Tab Overview
The Journal Tab functions as the app's personal logging center, where users can review, edit, and add detailed visit notes for coffee shops, creating a chronological record of their coffee adventures. Accessed via the bottom tab bar (icon: notebook with "Leather" binding and "Brass" clasp accents), it presents a scrollable feed of entries sorted by date (newest first), drawing from local SQLite storage for complete offline access. This tab captures the essence of a vintage coffee diary, with "Old Paper" backgrounds adorned by faint "Coffee Ring" stains, "Leather" textures on entry cards, and "Brass" highlights on ratings and tags, evoking a well-thumbed leather-bound journal from a cozy library nook.

The layout is clean and focused: a full-screen list with a floating "Add New Visit" button for quick entries (tied to a shop or standalone). It supports accessibility through scalable fonts, high-contrast elements, and haptic feedback on actions like saving or deleting notes. Integration with other tabs allows seamless navigation, such as jumping to a shop's map view, reinforcing the app's interconnected, privacy-first ecosystem.

## Key Components
- **Chronological Feed**:
  - Vertical list of visit cards, using native list views for smooth scrolling.
  - Each card: "Old Paper" base with "Coffee Ring" overlays, "Leather" borders, and expandable sections.
  - Display: Date (prominent, brass-formatted), shop name/address (linked to map), drink ordered (headline), rating (brass stars), taste tags (chip-style, multi-colored for flavors), snippet of notes, and photo thumbnails (carousel if multiple, compressed <1MB).
  - Sorting: Default by date; optional filters for shop, rating, or tags via top dropdown (leather-textured).

- **Add/Edit Visit Form**:
  - Modal or full-screen sheet triggered by floating button or from other tabs (pre-populated with shop data).
  - Fields:
    - Date: Auto-populated (editable).
    - Shop: Dropdown/search from discovered/favorited places or manual entry.
    - Drink Ordered: Free-text input.
    - Rating: 1-5 star selector (brass icons with haptic on tap).
    - Taste Tags: Multi-select chips (predefined list: chocolate, fruity, nutty, floral, etc.; customizable via settings).
    - Notes: Multi-line text area.
    - Photos: Up to 5, via camera/gallery picker (with compression and previews).
  - Save button (brass-accented) with validation and haptic success feedback.

- **Entry Details View**:
  - Tap card to expand into full-screen detail (stack push).
  - Full notes, enlarged photo gallery (swipeable, with old paper frames), edit/delete buttons.
  - "View on Map" button: Deep-links to Explore, centering on shop.

- **Empty State**:
  - If no entries: Illustrative graphic (empty leather journal with coffee ring) and prompt ("Log your first visit from Explore or add one here"), with direct "Add New" button.

- **Search/Filter**:
  - Top search bar (leather-bordered) for querying by drink, notes, or tags.
  - Optional nice-to-have: Global search integration if implemented.

## User Interactions
- **Core Flow**: Switch to Journal → Scroll feed → Tap entry → View/edit details → Save changes (local SQLite update) → Optional map navigation.
- **Adding Entries**: From Explore/Favorites details sheets ("Add Visit Note" pre-fills shop) or directly in Journal; haptic on photo add or tag select.
- **Cross-Tab Links**: Tap shop in entry → Navigates to Explore map; favorites sync if shop starred.
- **Editing/Deleting**: Long-press card for context menu (edit/delete); confirm modals with haptic warnings.
- **Error Handling**: No photos permission: Prompt modal; offline: Unaffected, as all data local.
- **Performance**: Efficient SQLite queries; lazy-load photos for fast scrolling.

This tab highlights the app's journaling core, merging reflective logging with thematic design for a deeply personal, privacy-respecting coffee chronicle.
