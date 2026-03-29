# Offline Mode Security Considerations

## Data At Rest

- All cached data encrypted using AES-256 with device-derived key
- Encryption key stored in secure keychain, not in app bundle
- SQLite database encryption via SQLCipher
- Max cache size: 50MB, auto-purge data older than 90 days

## What Can Be Cached

- Account balances (last fetched timestamp shown)
- Recent transactions (last 90 days)
- Payee/contact list
- User profile information
- Downloaded statements

## What Must NOT Be Cached

- Full account numbers (show last 4 digits only)
- Authentication tokens (stored separately in keychain)
- Password or PIN
- Biometric templates

## Offline Queue Security

- Queued operations (transfers, payments) encrypted at rest
- Execute in FIFO order on network restore
- Conflict resolution: server state wins for balances
- Require re-authentication before executing queued transactions

## Network Restore

- Verify server certificate on reconnection (prevent MITM)
- Pull fresh data before showing cached data as current
- Show clear "offline" indicator and stale data timestamps
- Invalidate cached data if offline for more than 7 days
