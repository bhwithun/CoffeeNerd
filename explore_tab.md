# Coffee Nerd - Explore Tab Description

## Tab Overview
The Explore Tab serves as the app's primary discovery hub, featuring a full-screen interactive Google Maps experience for finding coffee shops, restaurants, and places likely to serve coffee. As the default landing tab, it provides location-based exploration with privacy-first design—all data stays local, with Google Places API (New) integration for real search results. The tab implements Material 3 design with custom coffee-themed colors, creating an engaging discovery experience.

The layout features a dominant map view with top search overlay and floating action buttons. Location permissions are requested on first use, with graceful fallbacks. The implementation uses Jetpack Compose for modern Android development.

## Implementation Status: ✅ FULLY IMPLEMENTED

### Key Features Implemented:
- **Google Places API (New)** integration with proper authentication
- **Smart coffee filtering** - searches for any cuisine but shows places likely to serve coffee
- **Visible map bounds search** - searches within what's currently visible on map
- **Real-time location services** with GPS permissions
- **Custom markers** with different colors for place types
- **Bottom sheet details** with place information and actions
- **Material 3 design** with coffee-themed colors

## Key Components

### **Interactive Map View**:
- **Google Maps Compose** integration filling screen minus bottom navigation
- **Location Services**: GPS-based positioning with permission prompts
- **Custom Markers**: Coffee cup icons with color coding by place type:
  - Coffee shops: Saddle brown (#8B4513)
  - Bakeries: Chocolate (#D2691E)
  - Roasteries: Dark brown (#654321)
  - Specialty cafes: Goldenrod (#DAA520)
  - Chains: Sienna (#A0522D)
  - Other: Dim gray (#696969)
- **Gestures**: Full pinch-zoom, pan, tap-to-select support
- **Floating Action Button**: "My Location" button to recenter on GPS position

### **Search Bar**:
- **Top overlay** with rounded Material 3 design
- **Real-time search** using Google Places API (New) Text Search
- **Smart filtering**: For coffee searches, shows all results; for other searches, prioritizes places likely to serve coffee (restaurants, cafes, bars, etc.)
- **Map bounds integration**: Searches within visible map area instead of current location
- **Loading states** with progress indicator during API calls

### **Place Details Bottom Sheet**:
- **Modal Bottom Sheet** triggered by marker tap
- **Snap points**: Expandable for full details
- **Content includes**:
  - Place name and address
  - Rating display (stars with gold color)
  - Price level indicators
  - Place type categorization
- **Action buttons**:
  - Directions (placeholder)
  - Call (placeholder)
  - Save/Favorite (placeholder)
- **Dismissible** with swipe gestures

## Technical Implementation

### **API Integration**:
```kotlin
// Google Places API (New) Text Search
val result = placesApiService.searchText(
    query = searchQuery,
    maxResults = 20,
    searchBounds = visibleBounds // Uses map viewport
)
```

### **Smart Coffee Filtering**:
```kotlin
val filteredPlaces = if (query.contains("coffee", ignoreCase = true)) {
    // Coffee searches: show all results
    response.places
} else {
    // Other searches: filter for coffee-friendly places
    response.places.filter { place ->
        place.types.contains("cafe") ||
        place.types.contains("bakery") ||
        place.types.contains("restaurant") ||
        place.types.contains("food") ||
        place.types.contains("bar") ||
        place.types.contains("meal_takeaway")
    }
}
```

### **Location Services**:
- **Permissions**: ACCESS_FINE_LOCATION and ACCESS_COARSE_LOCATION
- **FusedLocationProvider**: Current location with high accuracy
- **Fallback**: Last known location if current unavailable
- **Privacy**: Clear permission prompts explaining location usage

## User Interactions

### **Core Flow**:
1. **App Launch** → Explore tab loads → Location permission prompt
2. **Map Display** → Centers on user location (or fallback)
3. **Search** → Type query (e.g., "italian", "bakery", "coffee")
4. **Results** → Markers appear on map, camera adjusts to show all
5. **Tap Marker** → Bottom sheet with place details
6. **Actions** → Save, directions, call (placeholders for future implementation)

### **Search Examples**:
- **"coffee"** → Shows all coffee shops in visible area
- **"italian"** → Shows Italian restaurants (likely to serve coffee)
- **"bakery"** → Shows bakeries (coffee-focused)
- **"pizza"** → Shows pizza places, filtered to those serving coffee

### **Error Handling**:
- **No Location**: Uses default location (San Francisco), prompts for permissions
- **API Errors**: Graceful fallback, empty results with error logging
- **Network Issues**: API calls have timeouts and error handling
- **Permissions Denied**: Map still works, search uses default bounds

## Performance Optimizations

- **Debounced API calls** to prevent excessive requests during typing
- **Efficient marker rendering** with custom bitmaps
- **Lazy loading** of place details
- **Background processing** for location updates
- **Memory management** for map markers and bitmaps

## Future Enhancements (Not Yet Implemented)

- **Filters modal** for rating, open now, distance
- **Photo carousel** in place details
- **Hours display** with open/closed status
- **Cross-tab navigation** to Journal/Favorites
- **Offline caching** of search results
- **Autocomplete suggestions** in search bar

This implementation provides a solid foundation for coffee discovery with real Google Places data, smart filtering, and modern Android architecture.
