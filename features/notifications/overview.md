# Notification System Overview

RepairCore includes a comprehensive notification system for keeping users and customers informed.

## Overview

The notification system supports:
- **Email notifications** - Sent via configured SMTP
- **Database notifications** - Stored in-app notifications
- **Customizable templates** - Edit notification content
- **User preferences** - Users control which notifications they receive

## Notification Types

### Order Notifications

| Event | Description |
|-------|-------------|
| Order Created | New repair order created |
| Status Changed | Order status updated |
| Order Completed | Repair completed |
| Order Ready | Ready for pickup |
| Payment Received | Payment recorded |

### System Notifications

| Event | Description |
|-------|-------------|
| Low Stock Alert | Part stock below threshold |
| Assignment | Technician assigned to order |
| New Customer | New customer registered |

## Notification Templates

### Managing Templates

Navigate to **Admin > Notification Templates** to customize notification content.

**Template Fields:**
- **Name** - Template identifier
- **Subject** - Email subject line
- **Body** - Notification content (supports variables)
- **Channels** - Email, database, or both
- **Status** - Active/inactive

### Template Variables

Use placeholders in templates that get replaced with actual values:

```
Hello {customer_name},

Your repair order #{order_code} status has been updated to: {status}.

{company_name}
```

**Available Variables:**
- `{customer_name}` - Customer's name
- `{order_code}` - Order code
- `{status}` - Current status
- `{company_name}` - Company name
- `{company_phone}` - Company phone
- `{tracking_url}` - Order tracking URL

### Initializing Default Templates

Click **Initialize Defaults** to create standard notification templates.

## User Preferences

### Managing Preferences

Navigate to **Admin > Notification Preferences** to configure which notifications users receive.

**Preference Options:**
- Enable/disable specific notification types
- Choose channels (email, in-app)
- Set notification frequency

### User-Level Settings

Users can manage their own preferences in their profile settings.

## In-App Notifications

### Viewing Notifications

Users see notifications via the bell icon in the admin header.

**Features:**
- Unread count badge
- Mark as read
- Mark all as read
- Delete notifications
- Delete all read

### Routes

| Route | Method | Description |
|-------|--------|-------------|
| `admin/notifications` | GET | List notifications |
| `admin/notifications/{id}/mark-as-read` | POST | Mark as read |
| `admin/notifications/mark-all-read` | POST | Mark all as read |
| `admin/notifications/{id}` | DELETE | Delete notification |
| `admin/notifications/unread-count` | GET | Get unread count |

## Sending Notifications

### Using NotificationHelper

```php
use function send_notification;

// Send notification to user
send_notification($user, 'order_status_changed', [
    'order' => $order,
    'status' => $newStatus,
]);
```

### Using Laravel Notifications

```php
use App\Notifications\OrderStatusChanged;

$user->notify(new OrderStatusChanged($order));
```

## Models

### NotificationTemplate

Located at `App\Models\NotificationTemplate`.

**Fields:**
- name, slug
- subject, body
- channels (json)
- variables (json)
- status

### NotificationPreference

Located at `App\Models\NotificationPreference`.

**Fields:**
- user_id
- notification_type
- email_enabled
- database_enabled

## Controllers

- `NotificationController` - In-app notification management
- `NotificationTemplateController` - Template CRUD
- `NotificationPreferenceController` - User preferences

---

Next: [Email Notifications](email.md)
