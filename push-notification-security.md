# Push Notification Security

## Token Management

- FCM (Android) and APNs (iOS) tokens are device-specific
- Register token on each app launch (tokens can rotate)
- Associate token with user account server-side
- Remove token association on logout
- Never send sensitive data in notification payload (visible on lock screen)

## Notification Categories

### Silent / Background
- Data sync triggers
- Token refresh reminders
- No user-visible content

### Transactional (Always Delivered)
- Login from new device alert
- Password change confirmation
- Suspicious activity warning
- Transaction alerts (payment sent/received)

### Marketing (Opt-in Required)
- Feature announcements
- Promotional offers
- Respect quiet hours (10 PM - 7 AM user timezone)
- Max 5 non-critical per day
- Must include unsubscribe mechanism

## Deep Linking from Notifications

- Login alert → Security settings screen
- Transaction alert → Transaction detail screen
- Suspicious activity → Account freeze confirmation
- Validate deep link parameters to prevent injection

## Anti-Abuse

- Rate limit push delivery per device (no notification bombing)
- Detect and skip uninstalled apps (handle APNs feedback)
- Batch similar notifications (don't send 50 transaction alerts individually)
