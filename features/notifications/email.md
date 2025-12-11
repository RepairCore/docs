# Email Settings

Configure email delivery for notifications.

[image_email_settings]

## Overview

Email settings control how RepairCore sends notifications to customers and staff. Configure your SMTP server to enable email delivery.

## Accessing Email Settings

Go to **Settings > Email** to configure email delivery.

## Configuration

### Mail Driver

Select how emails are sent:

| Driver | Description |
|--------|-------------|
| **SMTP** | Standard email server (recommended) |
| **Sendmail** | Server's sendmail program |
| **Mailgun** | Mailgun API |
| **SES** | Amazon SES |
| **Postmark** | Postmark API |

### SMTP Settings

For SMTP driver, configure:

| Setting | Description | Example |
|---------|-------------|---------|
| **Host** | SMTP server address | smtp.gmail.com |
| **Port** | SMTP port | 587 |
| **Username** | SMTP username | your@email.com |
| **Password** | SMTP password | ••••••••• |
| **Encryption** | TLS or SSL | TLS |

### Sender Information

| Setting | Description |
|---------|-------------|
| **From Address** | Email address shown as sender |
| **From Name** | Name shown as sender |

## Common SMTP Configurations

### Gmail

```
Host: smtp.gmail.com
Port: 587
Encryption: TLS
Username: your@gmail.com
Password: App Password (not your Gmail password)
```

> **Note:** Gmail requires an App Password. Enable 2FA and create an App Password in Google Account settings.

### Outlook/Office 365

```
Host: smtp.office365.com
Port: 587
Encryption: TLS
Username: your@outlook.com
Password: Your password
```

### Custom SMTP

Contact your email provider for SMTP settings.

## Testing Email

After configuring:

1. Click **Send Test Email**
2. Enter a test email address
3. Click **Send**
4. Check if email arrives

[image_test_email]

## Troubleshooting

### Emails Not Sending

1. Verify SMTP credentials
2. Check host and port
3. Ensure encryption matches port (TLS: 587, SSL: 465)
4. Check firewall/hosting restrictions

### Emails Going to Spam

1. Use a reputable SMTP provider
2. Set up SPF record for your domain
3. Set up DKIM signing
4. Use consistent sender address

### Connection Timeout

1. Check if port is blocked by firewall
2. Try different port (587, 465, 25)
3. Contact hosting provider

---

Next: [General Settings](../settings/general.md)
