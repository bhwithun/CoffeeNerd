# Coffee Nerd - Favorites Tab Description

## Tab Overview
The Favorites Tab acts as a personalized collection hub for users to curate and revisit their preferred coffee shops, roasters, and cafés. Accessible via the bottom tab bar (icon: star with "Brass" glow and "Leather" outline), it displays starred locations in both list and map views, allowing quick reference without re-searching. This tab emphasizes offline accessibility, pulling data from local SQLite storage for instant loading, even without internet. Thematically, it evokes a leather-bound bookmark section in an old coffee journal, with "Old Paper" backgrounds featuring subtle "Coffee Ring" stains, "Leather" card textures for shop entries, and "Brass" accents on buttons and toggles. The dual-view layout (grid list and embedded map) promotes flexibility—users can scan details in list mode or visualize clusters geographically.

The interface remains minimalist: a top toggle for view switching, with ample white space and scalable text for accessibility. Haptic feedback accompanies actions like unstarring or tapping entries, enhancing the tactile, book-like feel. This tab integrates closely with Explore (for adding favorites) and Journal (for linking visits), fostering a cohesive app experience.

## Key Components
- **View Toggle**:
  - Top bar switch (brass-styled segmented control) between "List" (default) and "Map" views.
  - List: Grid layout (2-3 columns, device-dependent) of shop cards, sorted by distance or alphabetical (user-sortable via dropdown).
  - Map: Embedded Google Maps view showing all favorites as clustered markers (custom coffee-cup icons with leather shadows and brass pins), zoomable and pannable.

- **Shop Cards (List View)**:
  - Each card: Compact, with "Old Paper" background, faint "Coffee Ring" overlay, and "Leather" border.
  - Content: Shop name (heading), address/distance (caption), rating stars (brass-colored), thumbnail photo (if cached), and unstar button.
  - Tap card: Opens place details bottom sheet (similar to Explore, with actions to add note or navigate to map).

- **Map View**:
  - Full-tab map (minus top toggle and bottom bar), centered on user's location or favorites bounding box.
  - Markers: Interactive, tapping reveals mini-bottom sheet with quick details and navigation options.
  - Floating "List View" button for quick switch back.

- **Empty State**:
  - If no favorites: Subtle illustration (coffee cup on old paper with ring stain) and prompt text ("Star shops from Explore to build your collection"), with button linking to Explore tab.

- **Search/Filter**:
  - Optional top search bar (leather-textured) for filtering favorites by name or tags.
  - Basic sorts: By date added, distance, or rating.

## User Interactions
- **Core Flow**: Navigate to Favorites → Toggle to list/map → Tap shop → View details → Unstar or add note (navigates to Journal pre-filled) → Changes sync locally.
- **Adding/Removing**: Star from Explore/Journal details sheets; updates reflect instantly with haptic.
- **Cross-Tab Links**: Tap shop in list/map → Deep-links to Explore, centering on location; view associated journal entries via details sheet.
- **Error Handling**: No favorites: Guiding prompt; offline: Full access to cached data.
- **Performance**: Lazy loading for images; fast SQLite queries for responsiveness.

This tab reinforces the app's personalization focus, blending curated content with thematic design for a premium, privacy-centric user journey.
