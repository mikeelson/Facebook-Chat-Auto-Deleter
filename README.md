# Facebook Chat Auto Deleter

Automate deletion of Facebook Messenger conversations on `facebook.com/messages` at your request.  
When you press **Start**, the extension opens the thread menu → selects **Delete chat** → confirms.  
Includes Start/Stop controls, live **Deleted/Total** counters, and an optional delay between deletions.

## Features
- One-click **Start/Stop**
- **Deleted / Total** progress counters
- **Custom delay** between deletions (gentle on rate limits)
- Runs only on Messenger pages (`facebook.com/messages/*`)
- Lightweight; no sign-in required

## How to use
1. Install the extension from the Chrome Web Store.  
2. Open `https://www.facebook.com/messages/`.  
3. Click **Start Deletion** (pause anytime with **Stop**).

---

## Privacy Policy

**Overview.** This extension automates deletion of Facebook Messenger conversations on
`facebook.com/messages` when you request it.

**Data Collection.** We do **not** collect, transmit, or sell personal data.  
No message content is collected or stored.

**Permissions & Use.**
- **Host (`facebook.com/messages/*`)** – Access the Messenger page DOM to click the on-page *Delete chat* controls.
- **activeTab** – Temporary access only when you start the action.
- **scripting** – Runs the small on-page automation script after you press Start.
- **storage** – Saves local, non-personal settings (e.g., delay between deletions).
- **notifications (optional)** – Local status alerts (no personal data); can be disabled.

**Sharing.** No user data is shared with third parties.

**Security / Remote Code.** All code ships with the extension package.  
No remote code is loaded or executed. No `eval`/Function constructors are used.

**Changes.** Updates to this policy will be posted in this README.

**Contact.** support@yourdomain.com

---

## Developer notes (optional)

### Minimal Manifest (MV3)
Keep permissions tight for faster review. Example:
```json
{
  "manifest_version": 3,
  "name": "Facebook Chat Auto Deleter",
  "version": "1.0.0",
  "description": "Automates deleting Facebook Messenger chats from the Messages page.",
  "permissions": ["storage"],
  "content_scripts": [{
    "matches": ["https://www.facebook.com/messages/*"],
    "js": ["content.js"],
    "run_at": "document_idle"
  }]
}
