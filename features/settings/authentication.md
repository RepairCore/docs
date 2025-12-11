# Authentication Settings

Configure social login and authentication options for your repair shop.

[image_authentication_settings_page]

## Accessing Authentication Settings

1. Navigate to **Admin > Settings**
2. Click on **Authentication** tab

## Social Login

Enable users to log in using their social media accounts.

### Enable Social Login

Toggle **Enable Social Login** to allow or disable all social login options.

[image_social_login_toggle]

## Available Providers

### Google Login

Allow users to sign in with their Google account.

| Setting | Description |
|---------|-------------|
| **Enable Google** | Turn Google login on/off |
| **Client ID** | Your Google OAuth Client ID |
| **Client Secret** | Your Google OAuth Client Secret |

**How to get Google credentials:**
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing
3. Enable Google+ API
4. Create OAuth 2.0 credentials
5. Add your domain to authorized origins
6. Copy Client ID and Client Secret

[image_google_login_settings]

### Facebook Login

Allow users to sign in with their Facebook account.

| Setting | Description |
|---------|-------------|
| **Enable Facebook** | Turn Facebook login on/off |
| **App ID** | Your Facebook App ID |
| **App Secret** | Your Facebook App Secret |

**How to get Facebook credentials:**
1. Go to [Facebook Developers](https://developers.facebook.com/)
2. Create a new app
3. Add Facebook Login product
4. Configure OAuth settings
5. Copy App ID and App Secret

### Microsoft Login

Allow users to sign in with their Microsoft account.

| Setting | Description |
|---------|-------------|
| **Enable Microsoft** | Turn Microsoft login on/off |
| **Client ID** | Your Microsoft Application ID |
| **Client Secret** | Your Microsoft Client Secret |

### LinkedIn Login

Allow users to sign in with their LinkedIn account.

| Setting | Description |
|---------|-------------|
| **Enable LinkedIn** | Turn LinkedIn login on/off |
| **Client ID** | Your LinkedIn Client ID |
| **Client Secret** | Your LinkedIn Client Secret |

## Callback URLs

When configuring social providers, use these callback URLs:

| Provider | Callback URL |
|----------|--------------|
| Google | `https://yourdomain.com/auth/google/callback` |
| Facebook | `https://yourdomain.com/auth/facebook/callback` |
| Microsoft | `https://yourdomain.com/auth/microsoft/callback` |
| LinkedIn | `https://yourdomain.com/auth/linkedin/callback` |

> **Note:** Replace `yourdomain.com` with your actual domain.

## Security Notes

- Keep Client Secrets secure and never share them
- Only enable providers you actually need
- Regularly review and rotate credentials
- Test login flow after configuration changes

## Saving Changes

1. Configure provider settings
2. Click **Save Settings**
3. Test the login flow

[image_save_authentication_settings]

---

Next: [Common Issues](../../troubleshooting/common-issues.md)
