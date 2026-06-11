# PROG-PT2-Chatapp
A Java Swing desktop messaging application with user authentication and message management.

---

## Overview

CloudChat2 is a desktop chat application built with Java Swing. It provides user registration and login functionality, an # d allows authenticated users to compose, send, store, or disregard messages. Messages are persisted to a local JSON file, and users are stored in a plain text file.

---
## Features

- **User Registration** — Register with a username, name, phone number, and password
- **User Login** — Authenticate with username and password
- **Send Messages** — Send messages to recipients identified by phone number (e.g. `+27123456789`); limited to 50 characters
- **Store Messages** — Save messages locally for later sending; supports up to 250 characters
- **Disregard Messages** — Dismiss a composed message without sending or storing it
- **Message Log** — View a live scrolling log of all sent/stored messages in the chat panel
- **View All Messages** — Display the full list of stored/sent messages in a dialog
- **Message Metadata** — Each message is assigned a unique ID and a hash for reference
## Project Structure

```
CLoudCHat2/
├── src/
│   └── cloudchat2/
│       ├── Gui/
│       │   ├── Main.java              # Main JFrame, navigation controller
│       │   ├── NewLogin2.java         # Login panel
│       │   ├── NewRegistration.java   # Registration panel
│       │   └── ChatPanel.java         # Messaging UI panel
│       └── Logic/
│           ├── Login.java             # User authentication logic
│           ├── MessageSystem.java     # Message processing logic
│           └── Message.java           # Message model
├── data/
│   ├── users.txt                      # Persistent user store (CSV format)
│   └── messages.json                  # Persistent message store (JSON format)
├── build.xml                          # Apache Ant build file (NetBeans)
└── README.md
```
