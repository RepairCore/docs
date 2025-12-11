# Notification Templates

Customize the content of notifications sent to customers and staff.

[image_notification_templates]

## Overview

Notification templates define the content of emails and in-app notifications. Customize templates to match your brand and communication style.

## Viewing Templates

Navigate to **Admin > Notification Templates** to see all templates.

[image_templates_list]

## Template Fields

| Field | Description |
|-------|-------------|
| **Name** | Template name |
| **Subject** | Email subject line |
| **Body** | Message content |
| **Channels** | Email, In-App, or both |
| **Status** | Active or Inactive |

## Editing a Template

1. Find the template in the list
2. Click **Edit**
3. Modify subject and body
4. Click **Save**

[image_edit_template]

## Using Variables

Templates support variables that are replaced with actual values when sent.

### Example Template

```
Hello {customer_name},

Your repair order #{order_code} status has been updated to: {status}.

Thank you for choosing {company_name}!
```

### Available Variables

| Variable | Description |
|----------|-------------|
| `{customer_name}` | Customer's name |
| `{order_code}` | Order code |
| `{status}` | Current order status |
| `{device_info}` | Device brand and model |
| `{company_name}` | Your company name |
| `{company_phone}` | Your company phone |
| `{company_email}` | Your company email |
| `{tracking_url}` | Order tracking link |

## Default Templates

RepairCore includes default templates for common notifications:

| Template | Purpose |
|----------|---------|
| Order Created | Sent when new order is created |
| Status Changed | Sent when order status changes |
| Order Completed | Sent when repair is completed |
| Order Ready | Sent when order is ready for pickup |
| Payment Received | Sent when payment is recorded |

### Initialize Defaults

If templates are missing, click **Initialize Defaults** to create them.

[image_initialize_defaults]

## Enabling/Disabling Templates

Toggle the status to enable or disable a template:
- **Active** - Notifications are sent
- **Inactive** - Notifications are not sent

## Template Channels

Choose where notifications are sent:

- **Email** - Sent to customer's email
- **In-App** - Shown in notification bell (staff only)
- **Both** - Sent via both channels

---

Next: [Troubleshooting](../../troubleshooting/common-issues.md)
