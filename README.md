# Hotdesks Sign-In App

Hotdesks is a lightweight sign-in application designed for shared workspaces, tablets, and hotdesk stations. It provides a fast, touch-friendly way for users to register their presence on a shared device and logs each sign-in to a central Google Sheet.

![image](https://github.com/user-attachments/assets/d063b959-7fb8-44c3-9e97-e0c7657b1ec3)


---

## 🔧 What It Does

- Launches in fullscreen on startup
- Prompts users to enter their name or select from recently used names
- Logs sign-ins to a shared Google Sheet with timestamp and device name
- Automatically hides the UI after sign-in and displays a floating overlay with the signed-in user
- Reopens the sign-in screen automatically when the device is unlocked

---

## ✅ Key Features

- **Google Sheets Logging**  
  All sign-ins are recorded in real time using a secure service account connection.

- **Quick Sign-In Buttons**  
  Remembers the last two signed-in users for faster repeat use.

- **Session Awareness**  
  Detects unlock events and re-displays the sign-in prompt if no one is signed in.

- **Accessibility Options**  
  High-contrast mode toggle for improved legibility.

- **Auto-Update Support**  
  Checks for updates and can apply them automatically without reinstalling.

---

## 🔄 What's New (Latest Version)

- **Overlay Session Tab**  
  A new always-on-top floating tab appears after sign-in:
  - Shows the current user
  - Tracks session time
  - Tap to sign out
  - Can be moved around the screen

- Improved scaling for smaller tablet screens
- More responsive layout and colour refinements

---

## 🖥 Deployment

- The app is provided as a compiled `.exe` and is ready to run on any Windows 10+ device.
- Designed for tablet use in **fullscreen/kiosk environments**
- Place your `google_creds.json` in the same directory if not bundled
- Logs and cached user data are stored in the user's `AppData\Roaming\hotdesks` folder

---

## 🛠 Admin Commands (via local TCP)

IT staff can send JSON admin commands to the running app over a local TCP connection on port `5050`.

Supported commands:

```json
{ "action": "force_update" }
{ "action": "force_relogin" }
{ "action": "send_message", "text": "Message to user" }
{ "action": "set_overlay_opacity", "opacity": 0.7 }
