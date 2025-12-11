# Users

Manage staff accounts and access to the system.

[image_users_list]

## Overview

Users are staff members who can log in to the admin panel. Each user has a role that determines what they can access.

## Viewing Users

Navigate to **Admin > Users** to see all users.

[image_users_index]

### List Features

- **Search** - Find by name or email
- **Filter** - Filter by role, status
- **Bulk Actions** - Activate, deactivate, or delete multiple users

## Creating a User

1. Navigate to **Admin > Users**
2. Click **Create User**
3. Fill in user details
4. Click **Save**

[image_create_user]

### User Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Name** | Full name | Yes |
| **Email** | Email address (used for login) | Yes |
| **Password** | Login password | Yes |
| **Role** | User's role | Yes |
| **Phone** | Contact phone | No |
| **Avatar** | Profile picture | No |
| **Status** | Active or Inactive | Yes |

## Editing a User

1. Find the user in the list
2. Click **Edit** or the user name
3. Modify the information
4. Click **Save**

> **Note:** Leave password blank to keep the current password.

## Deleting a User

1. Find the user in the list
2. Click **Delete** button
3. Confirm deletion

> **Warning:** Deleted users cannot log in. Their activity history is preserved.

## User Status

| Status | Description |
|--------|-------------|
| **Active** | Can log in and use the system |
| **Inactive** | Cannot log in |

## Default Roles

| Role | Description |
|------|-------------|
| **Super Admin** | Full access to all features |
| **Admin** | Administrative access |
| **Technician** | Repair and order management |
| **Receptionist** | Customer and order intake |

[image_user_roles]

---

Next: [Roles & Permissions](permissions.md)
