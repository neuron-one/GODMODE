---
name: mobile-design
description: Mobile app design patterns for iOS and Android. Native navigation, touch targets, platform conventions, safe areas. Don't use for web-only interfaces.
user-invocable: false
model: sonnet
effort: medium
---

# Mobile Design

## Platform Conventions
- iOS: bottom tab bar, large titles, SF Symbols
- Android: material design, FAB, bottom navigation
- Both: pull-to-refresh, swipe gestures

## Touch Targets
- Minimum 44x44pt (iOS) / 48x48dp (Android)
- Spacing between targets: 8px minimum
- Primary actions within thumb reach zone

## Navigation
- Tab bar: 3-5 items max
- Stack navigation for drill-down
- Modal for focused tasks
- Gesture navigation support

## Safe Areas
- Respect notch/dynamic island
- Account for home indicator
- Keyboard avoidance for input forms

## Performance Feel
- Skeleton screens over spinners
- Optimistic updates
- Haptic feedback on actions
- 60fps animations