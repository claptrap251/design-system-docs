# Session Security Guidelines

## Token Strategy

### Access Tokens
- Format: JWT (JSON Web Token)
- Expiry: 15 minutes
- Storage: Secure keychain (iOS) or Android Keystore
- Contains: user ID, roles, issue time
- Never store in cookies, localStorage, or UserDefaults

### Refresh Tokens
- Format: Opaque random string (not JWT)
- Expiry: 30 days
- Storage: Secure keychain, bound to device
- Server-side: stored as hashed value in database
- One-time use: issue new refresh token on each use

## Session Lifecycle

1. Login → issue access token + refresh token
2. API calls include access token in Authorization header
3. On 401 → use refresh token to get new access token
4. On refresh failure → redirect to login screen
5. Logout → invalidate refresh token server-side, clear keychain

## Concurrent Session Management

- Maximum 3 active sessions per account
- Show active sessions in security settings
- Allow remote session revocation
- Force logout on password change from any device
- New login on a 4th device invalidates the oldest session

## Inactivity Timeout

- Auto-lock app after 15 minutes of inactivity
- Prompt biometric or password to resume
- Background timer continues when app is backgrounded
- Do not auto-logout — just require re-authentication
