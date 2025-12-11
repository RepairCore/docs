# Roles & Permissions

Control what users can access and do in the system.

[image_roles_list]

## Overview

Roles define what a user can do. Each role has a set of permissions that grant access to specific features.

## Viewing Roles

Navigate to **Admin > Roles** to see all roles.

[image_roles_index]

## Creating a Role

1. Navigate to **Admin > Roles**
2. Click **Create Role**
3. Enter role name and description
4. Select permissions
5. Click **Save**

[image_create_role]

### Role Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Name** | Role name | Yes |
| **Description** | Role description | No |
| **Permissions** | What this role can do | Yes |

## Default Roles

| Role | Description |
|------|-------------|
| **Super Admin** | Full access to everything |
| **Admin** | Administrative access (most features) |
| **Technician** | Manage repairs and orders |
| **Receptionist** | Customer intake and basic orders |

> **Note:** Default roles cannot be deleted but can be modified.

## Permissions

Permissions control access to specific features:

### Repair Orders

| Permission | Description |
|------------|-------------|
| View Orders | See repair orders |
| Create Orders | Create new orders |
| Edit Orders | Modify existing orders |
| Delete Orders | Delete orders |
| Change Status | Update order status |
| Assign Technicians | Assign staff to orders |
| Add Payments | Record payments |

### Customers

| Permission | Description |
|------------|-------------|
| View Customers | See customer list |
| Create Customers | Add new customers |
| Edit Customers | Modify customer info |
| Delete Customers | Delete customers |

### Inventory

| Permission | Description |
|------------|-------------|
| View Parts | See parts catalog |
| Create Parts | Add new parts |
| Edit Parts | Modify parts |
| Delete Parts | Delete parts |
| Adjust Stock | Manual stock adjustments |

### Services

| Permission | Description |
|------------|-------------|
| View Services | See service catalog |
| Create Services | Add new services |
| Edit Services | Modify services |
| Delete Services | Delete services |

### Users

| Permission | Description |
|------------|-------------|
| View Users | See user list |
| Create Users | Add new users |
| Edit Users | Modify users |
| Delete Users | Delete users |
| Manage Roles | Create and edit roles |

### Settings

| Permission | Description |
|------------|-------------|
| View Settings | Access settings pages |
| Edit Settings | Modify settings |

## Editing a Role

1. Find the role in the list
2. Click **Edit**
3. Modify name, description, or permissions
4. Click **Save**

## Deleting a Role

1. Find the role in the list
2. Click **Delete**
3. Confirm deletion

> **Warning:** Users with the deleted role will lose their permissions.

## Assigning Roles to Users

1. Edit the user
2. Select role from dropdown
3. Save

A user can have one role at a time.

[image_assign_role]

---

Next: [Notification Templates](../notifications/templates.md)
