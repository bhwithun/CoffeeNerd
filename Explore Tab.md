# Coffee Nerd - Explore Tab Description

## Tab Overview
The Explore Tab serves as the app's primary discovery hub, immersing users in a full-screen interactive map experience tailored for finding independent coffee shops, roasters, and specialty cafés. As the default landing tab upon app launch, it prioritizes quick, location-based exploration while upholding privacy—no data is shared externally, and offline caching ensures usability without connectivity. The tab integrates seamlessly with the app's coffee-themed aesthetics, featuring subtle "Old Paper" backgrounds layered with "Coffee Ring" stains, "Leather" edge textures, and "Brass" accents on interactive elements like buttons and markers. This creates a vintage library-journal vibe, making discovery feel like flipping through a well-worn coffee atlas.

The layout is minimalist: a dominant map view with top overlays for search and filters, ensuring unobstructed panning and zooming. Haptic feedback enhances interactions, such as a light vibration on marker taps or filter applications. Accessibility is key, with scalable text, high-contrast markers, and screen reader support for all elements.

## Key Components
- **Interactive Map View**:
  - Powered by Google Maps SDK, filling the screen (minus bottom tab bar).
  - Centers on user's location (via device GPS, with privacy-focused permission prompt on first use).
  - Displays clustered markers for coffee spots, customized with coffee-cup icons featuring "Brass" glows and "Leather" shadows.
  - Supports gestures: pinch-zoom, pan, and tap-to-select.
  - Floating "Recenter" button (brass-accented) to snap back to current position.
  - Offline: Loads cached tiles and last-known places with a subtle "Offline Mode" banner (old paper texture).

- **Search Bar**:
  - Top overlay with coffee-brown border and "Leather" texture.
  - Free-text input for queries like "coffee shop" or "roastery near me".
  - Autocomplete suggestions from Google Places API, displayed in a dropdown with distances and ratings.
  - On submit, refreshes markers and adjusts map bounds dynamically.

- **Filters Button**:
  - Icon (brass funnel) next to search bar.
  - Opens a modal sheet with toggles/sliders:
    - "Open Now" (time-based filter).
    - "Rating ≥4.0" (star threshold).
    - "Distance" (slider: 1-50km/miles, with optional units toggle).
  - Apply button with haptic confirmation; updates map in real-time.

- **Place Details Bottom Sheet**:
  - Triggered by marker tap; draggable with snap points (peek for quick info, expanded for full details).
  - Header: Place name, rating stars (brass-colored), and star button for favoriting (leather-textured).
  - Content sections:
    - Photo carousel (API-fetched, cached; framed with old paper edges).
    - Hours schedule (highlighted current status: open/closed with success/error colors).
    - Contact: Phone (tappable, brass icon), website (external link), directions (opens native maps app).
    - Actions: "Add Visit Note" (navigates to Journal pre-filled), "Favorite" (adds to Favorites tab).
  - Background: Old paper with faint coffee rings; dismiss with swipe for haptic feedback.

## User Interactions
- **Core Flow**: Launch app → Explore loads → Grant location → Map shows nearby spots → Search/filter → Tap marker → View details → Favorite or note.
- **Cross-Tab Links**: From Journal/Favorites, deep-link to center map on a shop.
- **Error Handling**: No location: Prompt modal; no internet: Cached view with warning.
- **Performance**: Fast rendering; debounce API calls for smooth experience.

This tab embodies the app's exploration focus, blending functionality with thematic design for an engaging, privacy-respecting user journey.
