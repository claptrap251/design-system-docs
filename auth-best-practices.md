# Authentication Best Practices for Mobile Apps

## Overview

Modern mobile applications require robust authentication that balances security with user experience. This guide covers industry best practices for implementing login flows, credential management, and session handling.

## Credential Storage

- Never store passwords in plaintext or SharedPreferences
- Use the platform secure keychain (iOS Keychain Services, Android Keystore)
- Encrypt sensitive data at rest using AES-256-GCM
- Store JWT tokens in the secure keychain, not in cookies or localStorage

## Login Flow Security

- Implement rate limiting on login attempts (max 5 per minute)
- Lock accounts after consecutive failed attempts (5 failures = 15 min lockout)
- Use HTTPS for all authentication requests
- Validate email format client-side before sending to the server
- Never expose whether an email exists in error messages

## Password Requirements

- Minimum 12 characters recommended
- Require mix of uppercase, lowercase, numbers, and special characters
- Check against common password databases (Have I Been Pwned API)
- Enforce password history (no reuse of last 5 passwords)
- Show real-time password strength indicator during registration

## Multi-Factor Authentication

- Support TOTP (Time-based One-Time Password) as second factor
- SMS OTP as fallback (less secure but wider adoption)
- OTP expiry: 10 minutes maximum
- Rate limit OTP requests: 3 per hour per account
