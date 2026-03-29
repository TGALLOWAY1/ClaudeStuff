# Mobile Standards

## Platform Guidelines

- Follow iOS Human Interface Guidelines for iOS apps
- Follow Material Design 3 guidelines for Android apps
- Use platform-native navigation patterns and UI components
- Respect platform conventions for gestures, haptics, and notifications

## Performance

- App should be interactive within 2 seconds of launch
- Minimize main thread work; offload heavy computation to background threads
- Optimize images: use appropriate formats (WebP), lazy load, and cache aggressively
- Limit network requests; batch API calls where possible
- Monitor and minimize memory usage; avoid retain cycles and memory leaks

## Offline & Networking

- Design for offline-first where applicable
- Cache critical data locally for instant access
- Show meaningful offline states rather than generic errors
- Handle network transitions (WiFi to cellular) gracefully
- Implement retry logic with exponential backoff for failed requests

## Security

- Store sensitive data in the platform keychain/keystore, not in plain storage
- Implement certificate pinning for API communication
- Use biometric authentication where appropriate
- Encrypt data at rest for sensitive information
- Obfuscate release builds; strip debug symbols

## Accessibility

- Support Dynamic Type / font scaling on both platforms
- Ensure all screens are navigable with VoiceOver (iOS) and TalkBack (Android)
- Provide sufficient color contrast and avoid conveying meaning through color alone
- Touch targets must be at least 44x44 points (iOS) / 48x48 dp (Android)
- Test with accessibility tools on both platforms

## Testing

- Write unit tests for business logic and view models
- Write UI tests for critical user flows
- Test on a range of device sizes and OS versions
- Profile for performance regressions before each release
