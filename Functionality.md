# 🧠 What Is InkDrop?
InkDrop is a real-time, collaborative writing platform—think of it as a focused, writer-first version of Google Docs, but with:
- Real-time multi-user editing
- Version tracking
- Tagging and mentions
- Role-based access
- Notifications
- Clean, minimal UI

It’s ideal for writers, editors, bloggers, students, or teams that work together on long-form documents.

## 🧱 Core Functionality (How It Works)

## 🔄 Real-time Collaboration
- Users connect to a "document room" via WebSocket
- As one user types, all others see changes instantly
- Typing indicators show who's editing
- Backend uses Django Channels + Redis to broadcast updates

## 🗂️ Document Management
- Users can create, rename, or delete documents
- Each document has its own version history
- Users can tag documents with categories
- Mentions (@username) notify collaborators

## 👥 Role-Based Access
- Admin: Owns the document, can invite/remove users, assign roles
- Editor: Can modify the document
- Reader: Can only view the document

## 🔔 Notifications
Notifications are triggered on:
- Mentions (@someone)
- Document shared with you
- Document updated by another user
- Delivered in-app and optionally via email (future)



## 🧭 Site Structure (Pages & What They Do)
1. **Login/Register Page**
- Email + password authentication using JWT
- Option to invite new users via email

2. **Dashboard (Home)**
- Displays list of all documents the user can access
- Filter/sort by tags, last updated, ownership
- Create new document or join existing ones

3. **Document Editor Page**
*Route: /documents/:id/*
This is the core of InkDrop — the real-time editor.
🔧 Features:
- Rich text editor (e.g., using Quill.js or Slate.js)
- Live typing & syncing via WebSocket
- See active users in the room
- Mentions autocomplete (@username)
- Toolbar: bold, italics, headers, links, undo/redo
- "Save Version" button (optional auto-save)
- Tag editor + collaborators list

4. **Version History Page**
*Route: /documents/:id/versions/*
- View all previous saved versions
- See who saved what and when
- Compare versions (basic diff view)
- Revert to older version

5. **Document Settings Page**
*Route: /documents/:id/settings/*
- Rename document
- Manage tags
- Manage collaborators:
    - Add by username/email
    - Assign role (Admin, Editor, Reader)
    - Delete document

6. **Notifications Page**
*Route: /notifications/*
- List of recent notifications e.g., “@you was mentioned in ‘Chapter 4 Draft’”
- Mark notifications as read/unread

7. **User Profile Page**
*Route: /profile/*
- View and update user info
- List of owned documents
- List of shared documents
- Option to change password or delete account