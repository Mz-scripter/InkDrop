# InkDrop

InkDrop Project Breakdown
## User Story 1: Set Up Django Project
**Objective: Create the basic framework for the project.**

Learn:
- Setting up a Django project with a virtual environment.
- Create a project with multiple apps (users, documents, comments).
- Configure PostgreSQL as your database.
- Set up static and media files.

## User Story 2: User Registration & Authentication
**Objective: Implement user registration, login, and role-based authentication (RBAC).**

Learn:
- Django’s User model and custom user authentication.
- Implement role-based access control (RBAC).
- Use Django REST Framework (DRF) for user registration and login endpoints.
- Use JWT for authentication (or Session-based auth, if preferred).

## User Story 3: Build the Document Model
**Objective: Create a document model with version history, tags, and collaborators.**

Learn:
- Define models in Django (Document, Tag, UserCollaborator).
- Use Django’s ManyToMany fields for tags and collaborators.
- Implement version history using JSONField (for saving document versions).
- Set up migrations and apply them to PostgreSQL.

## User Story 4: Implement Tagging & Mentions System
**Objective: Create a way to tag users in documents and provide autocomplete for mentions.**

Learn:
- Create a Tag model and implement tags on documents.
- Use full-text search in PostgreSQL to search tags efficiently.
- Set up a mention system (@username) that triggers notifications.

## User Story 5: Real-Time Collaboration
**Objective: Enable real-time document editing with WebSockets.**

Learn:
- Set up Django Channels to handle WebSockets.
- Implement real-time synchronization for document editing using WebSockets.
- Broadcast changes to all connected clients when one user edits the document.

## User Story 6: Implement Notifications System
**Objective: Notify users when they are tagged in a document or when a document is updated.**

Learn:
- Set up Django signals to detect when a user is mentioned in a document.
- Use Celery and Redis to send asynchronous notifications.
- Store notifications in the database and allow users to view them.

## User Story 7: Version History & Document Recovery
**Objective: Allow users to see previous versions of a document and restore old versions.**

Learn:
- Use the versioning system you created in User Story 3.
- Display a list of previous versions and allow users to revert to them.
- Implement automatic saving of document versions in the database.

## User Story 8: Implement Document Permissions
**Objective: Control who can view/edit documents based on their role (admin, editor, reader).**

Learn:

- Implement custom permissions in Django REST Framework for documents.
- Set permissions on document views, edits, and deletions.
- Control document sharing via roles (admin can share, reader can view, etc.).

## User Story 9: Build the Frontend (Document Editing Interface)
**Objective: Create a user interface where users can edit, tag, and view documents.**

Learn:
- HTML/CSS and JavaScript for creating a dynamic interface.
- Integrate WebSockets to listen for real-time changes (using JavaScript or Vue.js).
- Implement a rich text editor (like Quill.js or TinyMCE) for document editing.

## User Story 10: Deploy the Project to DigitalOcean
**Objective: Deploy the project to DigitalOcean for live usage.**

Learn:
- Set up a DigitalOcean Droplet with Docker (optional).
- Install PostgreSQL and Redis on the server.
- Configure Nginx as a reverse proxy and Gunicorn for serving the app.
- Set up a CI/CD pipeline for automatic deployment (GitHub Actions or Jenkins).

## User Story 11: Add Tests & Final Refinements
**Objective: Ensure the app is stable and reliable with proper testing.**

Learn:
- Write tests for the document model, views, and WebSocket functionality.
- Set up pytest for testing Django apps.
- Perform load testing and optimize performance.

## User Story 12: Final Deployment and Monitoring
**Objective: Final deployment with logging and monitoring for errors.**

Learn:
- Set up Sentry for error tracking and CloudWatch for monitoring.
- Configure SSL (HTTPS) for the website.
- Set up auto-scaling and backups on DigitalOcean or AWS (optional).

