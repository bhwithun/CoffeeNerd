# Coffee Nerd - Learn Tab Description

## Tab Overview
The Learn Tab serves as the app's educational resource center, offering a static, fully offline FAQ on common coffee drinks and brew methods to deepen users' knowledge without external data reliance. Accessed via the bottom tab bar (icon: open book with "Leather" binding and "Brass" page edges, or a lightbulb with metallic glow), it features a searchable list of 25+ entries, each providing concise insights ideal for quick reference during coffee explorations. This tab embodies a vintage library reference section, with "Old Paper" backgrounds subtly marked by "Coffee Ring" stains, "Leather" textures on list items, and "Brass" accents on icons and highlights, creating an immersive, bookish atmosphere that aligns with the app's privacy-focused, enthusiast-driven design.

Content is hardcoded or stored locally (e.g., in JSON or SQLite for search efficiency), ensuring instant access and no API calls. The layout is straightforward: a full-screen searchable list with expandable entries, supporting accessibility via scalable text, high-contrast modes, and haptic feedback on selections. It integrates lightly with other tabs, such as linking drink terms to journal tags for cohesive use.

## Key Components
- **Searchable List**:
  - Vertical scrollable list of entries (e.g., Espresso, Pour-Over, Latte), sorted alphabetically or by category (drinks vs. methods).
  - Each list item: Icon (coffee-themed SVG with brass outline), title (heading font), and short teaser description (e.g., "A concentrated shot of coffee...").
  - Top search bar (leather-bordered) for real-time filtering by keywords (e.g., "fruity" or "brew time"), with results highlighting matches.
  - Background: Old paper texture with faint coffee rings for empty or filtered views.

- **Entry Details View**:
  - Tap item to expand into a full-screen detail (stack push or modal).
  - Content: Full short description (100-200 words), key differences (bullet list, e.g., vs. similar drinks), icon enlarged (with leather frame), and optional related terms (links to other entries).
  - "Brass" dividers separate sections; haptic on tap for engagement.
  - Back navigation via button or gesture.

- **Empty/Filtered State**:
  - If search yields no results: Gentle prompt on old paper background ("No matches found—try 'espresso' or browse all"), with "Clear Search" button (brass-accented).
  - Initial load shows full list; no true empty state since content is static.

## User Interactions
- **Core Flow**: Navigate to Learn → Search or scroll list → Tap entry → Read details → Back to list; haptic on expansions.
- **Discovery Flow**: Use search for specific queries (e.g., "difference between latte and cappuccino"); results update dynamically.
- **Cross-Tab Links**: Optional integration: Tap a taste tag or drink term to suggest journal entry (if nice-to-have global search enabled).
- **Offline Handling**: Always available, as all data is local—no banners needed.
- **Error Handling**: Minimal; invalid searches just show no results prompt.
- **Performance**: Instant loading from local assets; efficient string matching for search.

This tab underscores the app's educational pillar, combining informative content with thematic design for an enriching, fully private learning experience.
