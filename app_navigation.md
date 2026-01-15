# Coffee Nerd - Navigation Requirements

## Navigation Overview
Coffee Nerd implements a modern Android navigation system using Jetpack Navigation and Material 3 components, providing seamless exploration, journaling, and learning experiences for coffee enthusiasts. The app uses a bottom navigation bar as the primary navigation method, ensuring intuitive switching between core features while maintaining Material Design principles.

The implementation uses Jetpack Compose for modern declarative UI, with proper state management and lifecycle handling. Navigation is fully accessible with support for dynamic font scaling, screen reader compatibility (TalkBack), and keyboard navigation. Transitions are smooth with Material motion, enhancing the coffee-themed aesthetic.

## Implementation Status: ✅ FULLY IMPLEMENTED

### Technical Stack:
- **Jetpack Navigation Compose** for routing and back stack management
- **Material 3 NavigationBar** for bottom tab implementation
- **Composable destinations** for each tab screen
- **State preservation** across navigation changes
- **Deep linking support** (prepared for future implementation)

## Primary Navigation Structure

### **Bottom Navigation Bar**:
- **Material 3 NavigationBar** with coffee-themed colors
- **Always visible** at bottom of screen (except full-screen modals)
- **5 tabs** in order from left to right:
  1. **Explore** (Icons.Default.LocationOn): Interactive map and search
  2. **Favorites** (Icons.Default.Favorite): Saved coffee places
  3. **Journal** (Icons.Default.MenuBook): Visit logging and notes
  4. **Learn** (Icons.Default.Lightbulb): Coffee education content
  5. **Profile** (Icons.Default.Person): User settings and preferences
- **Active tab highlighting** with primary coffee-brown color
- **Icon-only design** for clean appearance
- **State preservation** - map position maintained when switching tabs

### **Navigation Host Setup**:
```kotlin
val navController = rememberNavController()

NavHost(navController = navController, startDestination = "explore") {
    composable("explore") { ExploreScreen() }
    composable("favorites") { FavoritesScreen() }
    composable("journal") { JournalScreen() }
    composable("learn") { LearnScreen() }
    composable("profile") { ProfileScreen() }
}
```

## Secondary Navigation Elements

### **Bottom Sheets & Modals**:
- **ModalBottomSheet** for place details in Explore tab
- **Expandable sheets** with snap points (partial/full screen)
- **Swipe-to-dismiss** gestures
- **Material motion** for smooth animations

### **Cross-Tab Navigation** (Prepared for Future Implementation):
- **Deep linking** infrastructure ready
- **Parameter passing** between screens
- **State restoration** when navigating back

## User Flows

### **Onboarding/First Launch**:
1. **App starts** → Explore tab loads automatically
2. **Location permission prompt** appears (Material 3 dialog)
3. **Map initializes** with user location or fallback
4. **No guided tour** - discover features intuitively

### **Discovery Flow**:
1. **Explore tab** → Map loads with location
2. **Search** → Type query (e.g., "italian", "coffee")
3. **Results appear** → Markers on map, camera adjusts
4. **Tap marker** → Bottom sheet with place details
5. **Actions** → Save, directions, call (placeholders)

### **Tab Switching Flow**:
- **Instant switching** between tabs
- **State preservation** (map position maintained)
- **Smooth transitions** with Material motion
- **Back navigation** via system back button

## Implementation Details

### **Navigation Component Integration**:
```kotlin
// Bottom Navigation Items
val items = listOf(
    BottomNavItem("Explore", Icons.Default.LocationOn, "explore"),
    BottomNavItem("Favorites", Icons.Default.Favorite, "favorites"),
    BottomNavItem("Journal", Icons.Default.MenuBook, "journal"),
    BottomNavItem("Learn", Icons.Default.Lightbulb, "learn"),
    BottomNavItem("Profile", Icons.Default.Person, "profile")
)

// Navigation Bar Composable
NavigationBar {
    items.forEach { item ->
        NavigationBarItem(
            icon = { Icon(item.icon, contentDescription = item.label) },
            label = { Text(item.label) },
            selected = currentRoute == item.route,
            onClick = { navController.navigate(item.route) }
        )
    }
}
```

### **Screen Implementations**:
- **ExploreScreen**: Full-screen map with search overlay
- **FavoritesScreen**: Placeholder with Material 3 cards
- **JournalScreen**: Placeholder with list layout
- **LearnScreen**: Placeholder with educational content structure
- **ProfileScreen**: Placeholder with settings options

### **Accessibility Features**:
- **TalkBack support** for screen readers
- **Dynamic font scaling** via Material 3
- **High contrast support** for visibility
- **Keyboard navigation** for TV/remote input
- **Content descriptions** on all interactive elements

## Performance Optimizations

- **Lazy loading** of tab content
- **State preservation** during navigation
- **Memory management** for map resources
- **Smooth animations** without blocking UI thread
- **Background processing** for location updates

## Future Enhancements (Not Yet Implemented)

- **Deep linking** from external sources
- **Cross-tab navigation** with parameters
- **Navigation animations** beyond default Material motion
- **Bottom sheet navigation** for complex flows
- **Search integration** across tabs

## Error Handling

- **Navigation failures** gracefully handled with fallbacks
- **Invalid routes** redirect to home tab
- **State loss** during configuration changes prevented
- **Memory pressure** handled with proper cleanup

This navigation implementation provides a solid foundation for the app's user experience, following Android best practices and Material Design guidelines while maintaining the coffee-themed aesthetic.
