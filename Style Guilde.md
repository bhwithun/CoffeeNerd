# Coffee Nerd - UI Style Guide

## Guide Overview
This UI Style Guide defines the visual and interaction standards for Coffee Nerd Version 1, ensuring a clean, minimalist aesthetic that aligns with the app's privacy-first, coffee-enthusiast focus. The design emphasizes simplicity, readability, and subtle coffee-inspired elements to create an inviting experience without overwhelming users. Key principles include:
- **Minimalism**: Reduce clutter with ample white space, simple layouts, and focused content.
- **Coffee Theme**: Incorporate warm, earthy tones inspired by coffee (e.g., browns for accents) while keeping the interface neutral for broad appeal.
- **Coffee Ring Principle**: Integrate a "coffee stained" appearance through subtle, organic textures resembling coffee rings or spills. This adds a playful, authentic coffee-shop vibe without compromising usability—apply sparingly as background overlays, edge effects on cards/sheets, or faint watermarks on empty states/screens. Use semi-transparent PNG/SVG assets for stains (e.g., opacity 0.1–0.3) to evoke a lived-in, artisanal feel.
- **Old Paper Principle**: Incorporate an "old paper" appearance reminiscent of aged library books, with subtle yellowish tints, faint creases, parchment-like textures, and soft edge vignettes. This enhances the journaling and educational aspects, evoking a personal coffee notebook from a cozy library. Blend seamlessly with the Coffee Ring for a cohesive, vintage aesthetic—e.g., stains on aged paper backgrounds. Apply as low-opacity overlays to maintain modernity and readability.
- **Leather Principle**: Incorporate leather-bound book aesthetics through rich, textured overlays mimicking supple leather (e.g., subtle grain patterns, embossed edges). This adds a premium, tactile quality to elements like cards, tabs, or backgrounds, evoking the feel of a well-worn leather journal. Use earthy brown tones and blend with Old Paper for bound-page effects.
- **Brass Principle**: Integrate brass accents reminiscent of antique reading lamps, with metallic gold-bronze highlights for buttons, icons, borders, or decorative flourishes. This provides a warm, glowing elegance and subtle shine (e.g., via gradients or shadows), enhancing the library-inspired ambiance without overpowering the minimalist design.
- **Accessibility**: Support dynamic text scaling, high contrast for readability, and haptic feedback for interactions.
- **Consistency**: Uniform typography, colors, icons, and components across all screens and platforms.
- **Modes**: Full support for light and dark themes, with system-default as the initial setting (configurable in User Profile). Adjust "Coffee Ring," "Old Paper," "Leather," and "Brass" effects for visibility (e.g., muted textures and subtler metallics in dark mode with gentle glows).
- **Offline-Friendly**: Visual cues (e.g., subtle banners) for offline states without disrupting flow.

This guide is optimized for the specified single platform (to be confirmed: iOS or Android), using native UI kits for implementation (e.g., SwiftUI/UIKit for iOS, Jetpack Compose/Material for Android).

## Color Palette
- **Primary Accent (Coffee Brown)**: #6F4E37 (used for buttons, icons, highlights; evokes roasted coffee beans).
- **Secondary Accent**: #D2B48C (lighter tan for subtle elements like borders or hover states).
- **Coffee Stain Tones**: #A0522D (sienna for ring edges), #DEB887 (burlywood for faded spills)—blend into backgrounds for the "Coffee Ring" effect.
- **Old Paper Tones**: #FDFD96 (pale yellow for aged tint), #FAF0E6 (linen for parchment base)—apply as subtle gradients or overlays to evoke yellowed pages.
- **Leather Tones**: #8B4513 (saddle brown for deep leather), #A0522D (lighter grain highlights)—for textured backgrounds or bindings.
- **Brass Tones**: #B8860B (dark goldenrod for metallic accents), #DAA520 (goldenrod for glows)—used sparingly for highlights and edges.
- **Background**:
  - Light Mode: #FDFDFD (off-white base with old paper texture, leather grain overlays, and faint yellow tint; incorporate coffee stains and brass trims).
  - Dark Mode: #2A2A2A (muted gray base with subdued old paper creases, darker leather textures, muted stains, and subtle brass glows for contrast).
- **Text**:
  - Primary: #333333 (light) / #E0E0E0 (dark) – for body text.
  - Secondary: #666666 (light) / #A0A0A0 (dark) – for subtitles, metadata.
  - Accent Text: #FFFFFF on primary accent backgrounds.
- **Success/Positive**: #4CAF50 (e.g., open now indicators).
- **Warning/Neutral**: #FFC107 (e.g., offline banners).
- **Error/Negative**: #F44336 (e.g., permission denied alerts).
- **Neutral Grays**: #F5F5F5 (light backgrounds with old paper tint) / #333333 (dark backgrounds) for cards and sheets.

Colors are defined in platform-native theme files (e.g., ColorSets in Xcode for iOS, themes.xml for Android) for easy switching.

## Typography
- **Font Family**: Serif fonts for an old book feel (e.g., "Georgia" or system equivalents like "New York" on iOS, "Roboto Serif" on Android) for body text and headings; sans-serif fallback for UI elements like buttons. Integrate via platform font managers for consistency.
- **Sizes (Base: 16pt, scalable via user settings: Small -0.875x, Default 1x, Large 1.125x, Extra Large 1.25x)**:
  - Heading 1: 24pt, bold (e.g., screen titles).
  - Heading 2: 20pt, semi-bold (e.g., section headers).
  - Body: 16pt, regular (main content).
  - Caption: 14pt, regular (metadata like dates, distances).
  - Small: 12pt, regular (footnotes, tags).
- **Line Height**: 1.5x font size for readability, with subtle letter-spacing (0.5pt) to mimic printed pages.
- **Weight**: Bold for emphasis, regular for body; use italics sparingly for notes or quotes to enhance the library book vibe.
- **Accessibility**: Use dynamic type scaling; ensure contrast ratios ≥4.5:1 (WCAG AA compliant). Text overlays on "Old Paper," "Coffee Ring," "Leather," or "Brass" elements must maintain readability with adjustable opacity.

## Icons and Imagery
- **Icon Set**: Platform-native icons (e.g., SF Symbols for iOS, Material Icons for Android) with coffee-themed customizations (e.g., coffee-cup, map-marker, star for favorites). Apply subtle old paper texture, leather emboss, or brass shine to icon backgrounds.
  - Size: 24pt default; 32pt for prominent actions.
  - Color: Primary accent for active; secondary text for inactive, with brass highlights for emphasis.
- **Avatars**: Coffee-themed cartoons (e.g., beans, mugs) as SVG/PNG assets. Allow custom photo upload with circular cropping (128x128pt). Add faint old paper border, leather frame, or coffee ring effect.
- **Photos**: User-uploaded or API-fetched images compressed to <1MB, displayed in carousels or grids with aspect ratio preservation. Frame with subtle parchment edges or leather bindings.
- **Coffee Ring Assets**: Custom PNG/SVG files for stain textures (e.g., ring shapes, drip patterns) stored in assets folder. Use as background images with low opacity.
- **Old Paper Assets**: Custom PNG/SVG files for paper textures (e.g., creases, fibers, yellowed gradients) stored in assets folder. Layer over backgrounds for depth.
- **Leather Assets**: Custom PNG/SVG files for leather textures (e.g., grain patterns, stitching details) for bindings or panels.
- **Brass Assets**: Custom PNG/SVG files for metallic effects (e.g., lamp-like glows, rivets) for accents and dividers.
- **Placeholders**: Subtle coffee-brown outlines or icons for loading states, enhanced with faint "Old Paper," "Coffee Ring," "Leather," and "Brass" effects.

## Components and Layout
- **Buttons**: Rounded (8pt radius), primary accent background with white text; outline variant for secondary actions. Add subtle leather texture overlay and brass border glow. Haptic feedback on press.
- **Cards/Sheets**: Off-white/linen backgrounds with subtle shadows. Apply "Old Paper" texture as base (e.g., faint creases), "Leather" for bindings/edges, "Coffee Ring" as overlays on corners, and "Brass" for corner accents or clasps.
- **Navigation**: Bottom tab bar with icons only; active tab in primary accent. Optional subtle paper grain, leather wrap, or brass trim on tab backgrounds.
- **Lists/Grids**: Native list views for performance; grid views (e.g., favorites) with 2-3 columns based on screen width. Use soft separators mimicking book lines or leather-stitched dividers.
- **Forms**: Simple inputs with underline borders (coffee-brown focus); multi-select tags as chips. Backgrounds with light paper texture and brass highlights.
- **Maps**: Full-screen with overlays; custom markers (coffee cup icons with optional ring shadow, paper vignette, or brass pin).
- **Spacing**: Consistent margins/padding: 16pt base unit (e.g., screen edges), 8pt for internals, with irregular edges for old paper or leather-bound feel where appropriate.
- **Animations**: Subtle fades and slides (e.g., page-turn effects for transitions); keep under 300ms for snappiness.

## Interaction Guidelines
- **Gestures**: Platform-native gestures (e.g., pinch-zoom on maps; swipe-to-dismiss on sheets, with a subtle page-flip or leather-creak animation).
- **Feedback**: Haptic on success (e.g., favoriting); error vibration on failures.
- **Error States**: Non-intrusive banners in warning color, with optional "Old Paper" watermark (e.g., torn edge) or "Leather" frame for empty/error screens.
- **Loading**: Skeleton screens or spinners in secondary accent, blended with paper, stain, leather, and brass textures.
- **Accessibility Features**: VoiceOver/TalkBack compatibility; keyboard navigation support.

## Theme Implementation
- Use native appearance APIs for light/dark mode detection.
- Define global theme with "Coffee Ring," "Old Paper," "Leather," and "Brass" assets (e.g., as layered backgrounds or shaders).
- Export theme for reuse across views.

## Assets and Resources
- **Folder Structure**: Assets in platform-specific folders (e.g., Images.xcassets for iOS, res/drawable for Android), including coffee-stain, old-paper, leather-texture, and brass-effect PNGs.
- **Adaptive Icons**: Configure for app icons with subtle paper, ring, leather, and brass effects.
- **Testing**: Validate on simulators/emulators for color accuracy, scaling, mode switches, texture visibility, and principle integration.

This style guide ensures Coffee Nerd delivers a cohesive, user-friendly experience that feels premium, privacy-respecting, and delightfully immersive through the blended "Coffee Ring," "Old Paper," "Leather," and "Brass" principles. Apply it across all screens during development.
