# Biometric Authentication Integration Guide

## Platform Support

### iOS
- **Face ID**: iPhone X and later, iPad Pro 2018+
- **Touch ID**: iPhone 5s through 8/SE, various iPads
- **API**: LocalAuthentication framework (`LAContext`)
- **Fallback**: Device passcode, then app-level password

### Android
- **BiometricPrompt API**: Android 9+ (API 28)
- **Fingerprint**: Most devices since 2015
- **Face Recognition**: Pixel 4+, Samsung flagship devices
- **Fallback**: Device PIN/pattern, then app-level password

## Implementation Flow

1. User completes initial login with email + password
2. App prompts: "Enable biometric login?"
3. On consent, store encrypted auth token in secure keychain tied to biometric
4. On next app launch, prompt biometric scan
5. On success, retrieve token from keychain and validate expiry
6. If token expired, prompt password re-authentication
7. After 3 failed biometric attempts, fall back to password

## Security Considerations

- Biometric data never leaves the device (processed by Secure Enclave / TEE)
- Re-enrollment required after device biometric settings change
- Require password re-authentication after 30 days even with biometric
- Session timeout after 15 minutes of inactivity regardless of auth method
- Disable biometric auth on jailbroken/rooted devices

## Token Management with Biometrics

- Access Token: JWT, 15-minute expiry, stored in keychain
- Refresh Token: Opaque, 30-day expiry, bound to biometric enrollment
- Token refresh happens transparently before API calls
- Force re-authentication on password change from another device
