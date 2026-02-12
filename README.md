# morality_code

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.


## RBAC (User vs Administrator)

On launch, the app shows a **login mode selector**:
- **Login as User**
- **Login as Administrator**

The login mode is an **intent** only. After sign-in, the app checks the authenticated user's role from Firestore:
- `users/{uid}.role == "admin"` → treated as **ADMIN**
- any other value → treated as **USER**

### Admin provisioning (secure)
To create an admin, set the Firestore user document:

- Collection: `users`
- Document: `{uid}`
- Field: `role: "admin"`

No UI exists to elevate privileges inside the app.

### Feedback
- Users can submit feedback (Completion screen → **Submit Feedback**).
- Admins can view all feedback (Admin login → opens **User Feedback (Admin)** screen).
- Feedback is stored in Firestore collection: `feedback`.
