# Coffee Nerd - UI Style Guide

## Guide Overview
This UI Style Guide defines the visual and interaction standards for Coffee Nerd Android app, implemented with Material 3 Design and Jetpack Compose. The design emphasizes a modern, clean aesthetic with coffee-themed colors while maintaining Material Design principles for consistency and accessibility.

## Implementation Status: ✅ FULLY IMPLEMENTED

### Key Features Implemented:
- **Material 3 Design System** with custom coffee-themed color scheme
- **Jetpack Compose** for declarative UI development
- **Dynamic theming** with light/dark mode support
- **Custom typography** system with scalable fonts
- **Accessibility compliance** with TalkBack support
- **Consistent component library** across all screens

## Color Palette

### **Primary Color Scheme**:
```kotlin
// Color.kt - Custom color definitions
val CoffeeBrown = Color(0xFF6F4E37)      // Primary - Rich coffee brown
val CoffeeTan = Color(0xFFD2B48C)        // Secondary - Warm tan
val CoffeeDark = Color(0xFF3E2723)       // On-primary text
val CoffeeLight = Color(0xFFBCAAA4)      // Surface variants
```

### **Material 3 Color Scheme**:
- **Primary**: CoffeeBrown (#6F4E37) - buttons, active states, accents
- **Secondary**: CoffeeTan (#D2B48C) - secondary buttons, borders
- **Tertiary**: Goldenrod (#DAA520) - highlights, ratings, special elements
- **Surface**: Material defaults with coffee tint
- **Background**: Adaptive light/dark with coffee theming

### **Semantic Colors**:
- **Success**: Green (#4CAF50) - confirmations, positive states
- **Error**: Red (#F44336) - errors, warnings
- **Warning**: Orange (#FFC107) - cautions, offline states

## Typography System

### **Font Family**:
- **Body Font**: System default (Roboto) for readability
- **Display Font**: System serif for headings (optional enhancement)

### **Typography Scale** (Material 3):
```kotlin
// Type.kt - Typography definitions
val Typography = Typography(
    displayLarge = TextStyle(fontSize = 57.sp, lineHeight = 64.sp),
    displayMedium = TextStyle(fontSize = 45.sp, lineHeight = 52.sp),
    displaySmall = TextStyle(fontSize = 36.sp, lineHeight = 44.sp),
    headlineLarge = TextStyle(fontSize = 32.sp, lineHeight = 40.sp),
    headlineMedium = TextStyle(fontSize = 28.sp, lineHeight = 36.sp),
    headlineSmall = TextStyle(fontSize = 24.sp, lineHeight = 32.sp),
    titleLarge = TextStyle(fontSize = 22.sp, lineHeight = 28.sp),
    titleMedium = TextStyle(fontSize = 16.sp, lineHeight = 24.sp),
    titleSmall = TextStyle(fontSize = 14.sp, lineHeight = 20.sp),
    bodyLarge = TextStyle(fontSize = 16.sp, lineHeight = 24.sp),
    bodyMedium = TextStyle(fontSize = 14.sp, lineHeight = 20.sp),
    bodySmall = TextStyle(fontSize = 12.sp, lineHeight = 16.sp),
    labelLarge = TextStyle(fontSize = 14.sp, lineHeight = 20.sp),
    labelMedium = TextStyle(fontSize = 12.sp, lineHeight = 16.sp),
    labelSmall = TextStyle(fontSize = 11.sp, lineHeight = 16.sp)
)
```

### **Typography Features**:
- **Scalable fonts** via system settings
- **Consistent line heights** for optimal readability
- **Font weights** for hierarchy (Regular, Medium, Bold)

## Component Library

### **Material 3 Components Used**:
- **NavigationBar** - Bottom tab navigation
- **TopAppBar** - Search bars and headers
- **Card** - Content containers
- **Button** - Primary and secondary actions
- **TextField** - Input fields with coffee-themed styling
- **ModalBottomSheet** - Place details and overlays
- **FAB** - Floating action buttons

### **Custom Components**:
- **Coffee-themed markers** - Custom bitmaps for map pins
- **Rating stars** - Gold-colored star displays
- **Search overlay** - Rounded search bar with loading states

## Theme Implementation

### **Light Theme**:
```kotlin
// Theme.kt - Light color scheme
lightColorScheme(
    primary = CoffeeBrown,
    onPrimary = Color.White,
    primaryContainer = CoffeeLight,
    onPrimaryContainer = CoffeeDark,
    secondary = CoffeeTan,
    onSecondary = CoffeeDark,
    tertiary = Color(0xFFDAA520), // Goldenrod
    surface = Color(0xFFFEF7FF),
    onSurface = Color(0xFF1D1B1E),
    background = Color.White,
    onBackground = Color.Black
)
```

### **Dark Theme**:
```kotlin
// Theme.kt - Dark color scheme
darkColorScheme(
    primary = CoffeeBrown,
    onPrimary = Color.Black,
    primaryContainer = Color(0xFF4A3428),
    onPrimaryContainer = CoffeeLight,
    secondary = CoffeeTan,
    onSecondary = Color.Black,
    tertiary = Color(0xFFFFD700), // Lighter gold for dark mode
    surface = Color(0xFF0F0F0F),
    onSurface = Color.White,
    background = Color(0xFF0F0F0F),
    onBackground = Color.White
)
```

### **Dynamic Theming**:
- **System preference detection** for light/dark mode
- **Manual override** in profile settings (prepared)
- **Smooth transitions** between themes

## Layout Principles

### **Spacing System**:
- **Base unit**: 8.dp (Material 3 standard)
- **Common spacings**: 8.dp, 16.dp, 24.dp, 32.dp
- **Consistent margins** and padding throughout

### **Screen Layouts**:
- **Full-screen maps** with overlay controls
- **List layouts** with Material 3 cards
- **Bottom sheets** for details and actions
- **Responsive design** for different screen sizes

## Iconography

### **Material Icons Used**:
- **LocationOn** - Explore tab, location actions
- **Favorite** - Favorites tab, save actions
- **MenuBook** - Journal tab, notes
- **Lightbulb** - Learn tab, education
- **Person** - Profile tab, user settings
- **Search** - Search actions
- **Star** - Ratings and favorites

### **Custom Icons**:
- **Coffee cup markers** - Custom bitmaps for map pins
- **Rating stars** - Gold-colored star icons

## Accessibility Features

### **TalkBack Support**:
- **Content descriptions** on all interactive elements
- **Semantic labeling** for screen readers
- **Focus management** for keyboard navigation

### **Dynamic Type**:
- **System font scaling** support
- **Readable contrast ratios** (4.5:1 minimum)
- **Scalable UI elements**

### **Color Contrast**:
- **WCAG AA compliance** for text and backgrounds
- **High contrast mode** support
- **Color-blind friendly** color choices

## Performance Optimizations

- **Efficient Compose recompilation** with stable keys
- **Lazy loading** for lists and grids
- **Image optimization** for markers and thumbnails
- **Memory management** for bitmaps and resources

## Future Enhancements (Not Yet Implemented)

- **Custom font integration** (serif for headings)
- **Advanced theming** with user customization
- **Animation system** beyond Material defaults
- **Custom illustrations** for empty states
- **Advanced accessibility** features

## Implementation Files

- **Color.kt** - Custom color definitions
- **Theme.kt** - Material 3 theme setup
- **Type.kt** - Typography system
- **Component files** - Reusable composables

This implementation provides a solid, accessible, and maintainable design system that balances coffee theming with modern Android design principles.
