# Coffee Nerd - Navigation Requirements

## Navigation Overview
Coffee Nerd employs a straightforward, intuitive navigation system designed to facilitate seamless exploration, journaling, and learning for coffee enthusiasts. The app uses a bottom tab bar as the primary navigation method, providing quick access to core features while maintaining a minimalist interface. This structure ensures users can switch between sections effortlessly, with deeper navigation handled via stacks, modals, and bottom sheets for details without overwhelming the main flow. All navigation adheres to platform-native conventions (e.g., back gestures on Android, swipe-to-dismiss on iOS) and incorporates haptic feedback for key transitions. The design prioritizes privacy and offline usability—no external links or accounts disrupt the experience.

Navigation is fully accessible, supporting dynamic font scaling, screen reader compatibility (e.g., VoiceOver on iOS, TalkBack on Android), and keyboard navigation where applicable. Transitions are smooth and fast (<300ms), with subtle animations (e.g., fades or slides) to enhance the coffee-themed, library-inspired aesthetic without distraction.

## Primary Navigation Structure
- **Bottom Tab Bar**: The central hub, always visible at the bottom of the screen (except in full-screen modals or maps). It features icon-only tabs for a clean look, with labels appearing on hover or selection in accessibility modes. Active tabs highlight in the primary coffee-brown accent, with optional subtle "Old Paper" texture or "Leather" binding effects per the style guide.
  - Tabs (in order from left to right):
    1. **Explore** (icon: map or compass): Opens the Explore & Maps screen.
    2. **Favorites** (icon: star or heart): Opens the Favorites list.
    3. **Journal** (icon: notebook or pen): Opens the Visit Journal tab.
    4. **Learn** (icon: book or lightbulb): Opens the Educational FAQ.
    5. **Profile** (icon: avatar or person): Opens the User Profile, with a nested link to Settings & About.
  - Tapping a tab switches views instantly, preserving state (e.g., map position in Explore).
  - Haptic feedback on tab selection for tactile confirmation.

## Secondary Navigation Elements
- **Stack Navigation**: Used for drilling down into details within tabs. For example:
  - From Explore: Tapping a map marker pushes a place details view (via bottom sheet or full screen).
  - From Journal: Tapping an entry pushes a detailed note view for editing.
  - Back navigation via platform-native buttons/gestures (e.g., back arrow or swipe).
- **Bottom Sheets/Modals**: Interactive overlays for non-disruptive actions.
  - Place details in Explore: Draggable bottom sheet (snap points: peek, half, full) with actions like favoriting or adding notes.
  - Filters in Explore: Modal overlay from filter icon, with apply/cancel buttons.
  - Avatar picker in Profile: Grid modal for selecting coffee-themed cartoons.
  - Dismiss via swipe-down or close button, with haptic feedback.
- **Deep Linking and Cross-Feature Navigation**:
  - Tapping a journal entry navigates to Explore, centering the map on the shop (with animation).
  - From place details: "Add Visit Note" pushes to Journal entry form, pre-populated with shop data.
  - Favorites list: Tapping a shop navigates to its map view in Explore.
  - Settings accessed via a gear icon in Profile or a dedicated sub-tab.
- **Search and Global Elements**:
  - Search bars (e.g., in Explore for places, in Learn for drinks) are top-placed overlays, with autocomplete and haptic on submission.
  - Optional nice-to-have: Global search modal (accessible via magnifying glass icon in tab bar) for cross-app queries on shops/notes.

## User Flows
- **Onboarding/First Launch**: Starts on Explore tab with a one-time location permission modal (explanatory text emphasizing privacy). No guided tour—users discover intuitively.
- **Discovery Flow**: User opens app → Explore tab loads with current location → Search/filter places → Tap marker → Bottom sheet for details → Favorite or add note → Switches to Favorites/Journal to view.
- **Journaling Flow**: From any shop (via Explore or Favorites) → "Add Visit" → Modal form for note entry → Saves locally → View in Journal tab as chronological list → Tap entry to edit or map.
- **Learning Flow**: Learn tab → Searchable list → Tap entry for expanded description (stack push) → Back to list.
- **Personalization Flow**: Profile tab → Edit avatar/name → Adjust theme/font → Nested Settings for about page/privacy info.
- **Offline Handling**: Navigation remains functional; unavailable features (e.g., real-time maps) show graceful banners without blocking paths.
- **Error/Edge Cases**: Permission denials prompt modals with settings links; no internet shows cached data with navigation intact.

## Implementation Notes
- Use platform-native navigation libraries (e.g., UINavigationController/UITabBarController for iOS, Navigation Component/BottomNavigationView for Android).
- Ensure safe area handling for notches/status bars.
- Test for smooth performance on older devices, with lazy loading for tabs.
- Integrate style guide elements: "Coffee Ring" stains on empty tabs, "Old Paper" backgrounds, "Leather" tab textures, "Brass" icon glows.

This navigation system keeps the app simple and user-centric, aligning with non-functional requirements for fast, accessible, and haptic-enhanced interactions.
