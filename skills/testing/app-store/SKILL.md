---
name: app-store
description: Pre-submission check for iOS App Store guidelines. Payments/IAP compliance, privacy manifests, login flows, metadata quality, binary validation. Use before submitting to Apple.
disable-model-invocation: true
model: opus
effort: high
allowed-tools: Read, Grep, Glob, Bash
---

# App Store Readiness Check

## 1. Payment Compliance
- No external payment links in app (Apple rule)
- If using web payments: proper user flow
- In-app purchases configured correctly
- Subscription management accessible

## 2. Privacy
- Privacy manifest (PrivacyInfo.xcprivacy)
- Data usage declarations accurate
- Required purpose strings for permissions
- Privacy policy URL in metadata

## 3. Login & Account
- Sign in with Apple if third-party login exists
- Account deletion functionality available
- Guest mode if applicable

## 4. Metadata Quality
- Screenshots for all required device sizes
- App description clear and accurate
- Age rating correctly set
- Keywords relevant

## 5. Technical
- No crashes on launch
- Works offline gracefully
- IPv6 compatible
- Minimum iOS version justified