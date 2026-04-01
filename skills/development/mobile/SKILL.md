---
name: mobile
description: React Native and Expo mobile development. Navigation, native modules, platform-specific code, app store preparation. Don't use for web React or backend development.
model: sonnet
effort: medium
allowed-tools: Read, Write, Edit, Bash, Grep, Glob
paths: "**/*.tsx,**/app.json,**/eas.json"
---

# Mobile Development

## React Native Patterns
- Expo managed workflow preferred
- React Navigation for routing
- AsyncStorage for local persistence
- Platform.select for iOS/Android differences

## Performance
- FlatList for long lists (not ScrollView)
- Image caching (expo-image or fast-image)
- Avoid inline styles in render
- Minimize bridge calls

## Native Features
- react-native-track-player for audio
- expo-notifications for push
- expo-file-system for file operations
- expo-secure-store for sensitive data

## App Store Readiness
- Proper app icons (all sizes)
- Splash screen configuration
- Privacy manifest (iOS)
- Required permissions justification
- Test on real devices before submission