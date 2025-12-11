# Email Configuration

Configure email settings to send notifications and communications to customers.

[image_email_settings_page]

## Accessing Email Settings

1. Navigate to **Admin > Settings**
2. Click on **Email** tab

## Email Driver

Select how emails are sent from your system.

| Driver | Description |
|--------|-------------|
| **SMTP** | Standard email protocol (recommended) |
| **Sendmail** | Server's sendmail program |
| **Mailgun** | Mailgun API service |
| **SES** | Amazon Simple Email Service |
| **Postmark** | Postmark email service |

[image_email_driver_select]

## SMTP Configuration

For SMTP driver, configure these settings:

| Setting | Description | Example |
|---------|-------------|---------|
| **Host** | SMTP server address | smtp.gmail.com |
| **Port** | SMTP port number | 587 |
| **Username** | SMTP username | your@email.com |
| **Password** | SMTP password | ******** |
| **Encryption** | Security protocol | TLS or SSL |

[image_smtp_settings_form]

### Common SMTP Settings

**Gmail:**
| Setting | Value |
|---------|-------|
| Host | smtp.gmail.com |
| Port | 587 |
| Encryption | TLS |

> **Note:** For Gmail, you may need to enable "Less secure app access" or use an App Password.

**Outlook/Office 365:**
| Setting | Value |
|---------|-------|
| Host | smtp.office365.com |
| Port | 587 |
| Encryption | TLS |

**Custom Mail Server:**
Contact your hosting provider for SMTP settings.

## Sender Information

Configure the default sender for all outgoing emails.

| Setting | Description |
|---------|-------------|
| **From Address** | Email address shown as sender |
| **From Name** | Name shown as sender |

[image_sender_settings]

### From Address

The email address that appears in the "From" field. Use a valid email address that you control.

Example: `noreply@yourcompany.com` or `support@yourcompany.com`

### From Name

The name that appears alongside the email address.

Example: `RepairCore` or `Your Company Name`

## Testing Email

After configuring settings:

1. Click **Save Settings**
2. Click **Send Test Email** (if available)
3. Check your inbox for the test email

If the test fails:
- Verify SMTP credentials
- Check firewall settings
- Try different port (465 for SSL, 587 for TLS)

## Troubleshooting

### Emails Not Sending

- Verify SMTP credentials are correct
- Check if your hosting allows outgoing SMTP
- Try using port 465 with SSL encryption
- Check spam/junk folder

### Emails Going to Spam

- Use a professional email domain (not free email)
- Set up SPF and DKIM records for your domain
- Avoid spam trigger words in subject lines

### Connection Timeout

- Check if port is blocked by firewall
- Try alternative ports (25, 465, 587, 2525)
- Contact hosting provider

## Saving Changes

1. Fill in all required fields
2. Click **Save Settings**
3. Send a test email to verify

[image_save_email_settings]

---

Next: [Authentication](authentication.md)
