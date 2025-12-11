# Users & Roles

Managing users, roles, and permissions in RepairCore.

## Overview

RepairCore uses a role-based access control (RBAC) system where:
- **Users** are assigned to one or more **Roles**
- **Roles** contain a set of **Permissions**
- Permissions control access to features and actions

## User Management

### Viewing Users

Navigate to **Admin > Users** to see all users.

**List Features:**
- Search by name or email
- Filter by role
- Bulk actions (activate, deactivate, delete)
- Pagination

### Creating Users

1. Navigate to **Admin > Users**
2. Click **Create User**
3. Fill in user details:
   - Name
   - Email
   - Password
   - Role(s)
   - Status (active/inactive)
4. Save

### User Fields

| Field | Description |
|-------|-------------|
| name | Full name |
| email | Email address (unique) |
| password | Hashed password |
| avatar | Profile image |
| phone | Contact phone |
| status | active, inactive |
| email_verified_at | Email verification timestamp |

### User Model

Located at `App\Models\User`.

**Relationships:**
- `roles()` - Assigned roles
- `meta()` - User metadata (UserMeta)
- `socialAccounts()` - Social login accounts
- `notificationPreferences()` - Notification settings

## Role Management

### Viewing Roles

Navigate to **Admin > Roles** to manage roles.

### Creating Roles

1. Navigate to **Admin > Roles**
2. Click **Create Role**
3. Enter role name and description
4. Select permissions
5. Save

### Default Roles

| Role | Description |
|------|-------------|
| Super Admin | Full access to all features |
| Admin | Administrative access |
| Technician | Repair and order management |
| Receptionist | Customer and order intake |
| Customer | Customer portal access |

### Role Model

Located at `App\Models\Role`.

**Fields:**
- name - Role name
- slug - URL-friendly identifier
- description - Role description
- is_system - System role (cannot be deleted)

## Permissions

### Permission Structure

Permissions follow the pattern: `{module}.{action}`

**Examples:**
- `users.view` - View users
- `users.create` - Create users
- `users.edit` - Edit users
- `users.delete` - Delete users

### Available Permissions

**User Management:**
- `users.view`, `users.create`, `users.edit`, `users.delete`
- `roles.view`, `roles.create`, `roles.edit`, `roles.delete`

**Repair Orders:**
- `repair-orders.view`, `repair-orders.create`, `repair-orders.edit`, `repair-orders.delete`
- `repair-orders.change-status`, `repair-orders.assign`, `repair-orders.add-payment`

**Inventory:**
- `parts.view`, `parts.create`, `parts.edit`, `parts.delete`
- `part-categories.view`, `part-categories.create`, `part-categories.edit`, `part-categories.delete`

**Services:**
- `services.view`, `services.create`, `services.edit`, `services.delete`
- `service-categories.view`, `service-categories.create`, `service-categories.edit`, `service-categories.delete`

**Customers:**
- `customers.view`, `customers.create`, `customers.edit`, `customers.delete`
- `devices.view`, `devices.create`, `devices.edit`, `devices.delete`

**Content:**
- `posts.view`, `posts.create`, `posts.edit`, `posts.delete`
- `pages.view`, `pages.create`, `pages.edit`, `pages.delete`

**Settings:**
- `settings.view`, `settings.edit`

**Reports:**
- `reports.view`, `reports.export`

### Checking Permissions

**In Controllers:**
```php
public function index()
{
    if (!auth()->user()->can('users.view')) {
        abort(403);
    }
    // ...
}
```

**In Blade:**
```blade
@can('users.create')
    <a href="{{ route('admin.users.create') }}">Create User</a>
@endcan
```

**In Livewire:**
```php
public function mount()
{
    if (!auth()->user()->can('repair-orders.edit')) {
        abort(403);
    }
}
```

## Routes

| Route | Method | Description |
|-------|--------|-------------|
| `admin/users` | GET | List users |
| `admin/users/create` | GET | Create user form |
| `admin/users/{user}` | GET | View user |
| `admin/users/{user}/edit` | GET | Edit user form |
| `admin/users/bulk-action` | POST | Bulk actions |
| `admin/roles` | GET | List roles |
| `admin/roles/create` | GET | Create role form |
| `admin/roles/{role}` | GET | View role |
| `admin/roles/{role}/edit` | GET | Edit role form |

---

Next: [Permissions](permissions.md)
