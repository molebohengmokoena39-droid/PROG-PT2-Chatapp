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
## Requirements

- **Java** 8 or higher (JDK)
- **Apache Ant** (or NetBeans IDE, which includes Ant)
- **org.json** library (for JSON message persistence)
---

## Getting Started

### Running in NetBeans

1. Open NetBeans IDE.
2. Go to **File → Open Project** and select the `CLoudCHat2` project folder.
3. Right-click the project and select **Clean and Build**.
4. Click **Run** (or press F6).

### Running with Ant (command line)

```bash
ant clean build
ant run
```
## Data Files

### `users.txt`
Stores registered users in CSV format:
```
username,password,phone,firstName,lastName
```
Example:
```
kyl_1,Ch&&sec@ke99!,+271234567890,Kyle,Smith
```

> **Note:** The current implementation does not deduplicate entries — registering the same username multiple times will append duplicate rows. This is a known issue.

### `messages.json`
Stores sent and stored messages as a JSON array. Each message object includes:

| Field | Description |
|---|---|
| `messageId` | Unique identifier for the message |
| `messageHash` | Hash string in the format `count:id:content` |
| `recipient` | Recipient phone number |
| `messageContent` | The message text |
| `numMessagesSent` | Running count of messages processed |
| `timestamp` | Unix timestamp (milliseconds) |

---

## Usage

1. **Launch** the application — the Login screen appears by default.
2. **Register** a new account via the Register panel, then return to Login.
3. **Log in** with your credentials to access the Chat panel.
4. In the Chat panel:
   - Enter a recipient phone number (format: `+27XXXXXXXXX`)
   - Type your message
   - Choose **Send Message**, **Store Message**, or **Disregard Message**
5. The message log updates automatically after each action.
6. Click **View All Stored Messages** to see the full message history.
