# Common Issues

Solutions to frequently encountered problems.

## Login Issues

### Cannot Log In

**Symptoms:** Login page shows error or redirects back.

**Solutions:**
1. Check email and password are correct
2. Ensure account is active (not deactivated)
3. Clear browser cache and cookies
4. Try a different browser

### Forgot Password

1. Click **Forgot Password** on login page
2. Enter your email address
3. Check email for reset link
4. Click link and set new password

> **Note:** Reset links expire after 60 minutes.

## Email Issues

### Emails Not Sending

**Symptoms:** Customers not receiving notifications.

**Solutions:**
1. Go to **Settings > Email**
2. Verify SMTP settings are correct
3. Check SMTP host, port, username, password
4. Ensure encryption matches port (TLS: 587, SSL: 465)
5. Test by sending a test email

### Emails Going to Spam

**Solutions:**
1. Set up SPF record for your domain
2. Set up DKIM signing
3. Use a reputable SMTP provider
4. Avoid spam trigger words in templates

## Order Issues

### Cannot Create Order

**Symptoms:** Error when saving new order.

**Solutions:**
1. Ensure customer is selected
2. Ensure device is selected
3. Check all required fields are filled
4. Verify you have permission to create orders

### Status Not Changing

**Symptoms:** Order status won't update.

**Solutions:**
1. Check you have permission to change status
2. Refresh the page and try again
3. Check if order is locked

## Inventory Issues

### Stock Not Deducting

**Symptoms:** Stock doesn't decrease when adding parts to orders.

**Solutions:**
1. Verify stock tracking is enabled
2. Check the part has stock quantity set
3. Refresh and check stock history

### Negative Stock

**Symptoms:** Stock shows negative numbers.

**Solutions:**
1. Check if backorder is enabled (Settings > Inventory)
2. Review stock history for discrepancies
3. Perform manual stock adjustment

## Print Issues

### Invoice Not Printing

**Symptoms:** PDF doesn't generate or is blank.

**Solutions:**
1. Ensure pop-ups are allowed for the site
2. Try a different browser
3. Check if order has items added
4. Clear browser cache

### Labels Not Printing Correctly

**Solutions:**
1. Check label size settings
2. Verify printer paper size matches
3. Adjust browser print settings
4. Disable headers/footers in print dialog

## Performance Issues

### Slow Loading

**Symptoms:** Pages take long to load.

**Solutions:**
1. Clear browser cache
2. Check internet connection
3. Try a different browser
4. Contact support if persists

### Session Timeout

**Symptoms:** Getting logged out frequently.

**Solutions:**
1. Check "Remember Me" when logging in
2. Avoid long periods of inactivity
3. Check browser cookie settings

## Data Issues

### Missing Data

**Symptoms:** Records not showing in lists.

**Solutions:**
1. Check filters - clear all filters
2. Check search box - clear search
3. Check pagination - go to first page
4. Verify you have permission to view

### Duplicate Records

**Solutions:**
1. Use search to find duplicates
2. Merge or delete duplicate records
3. Use unique identifiers (email, phone)

---

Next: [Error Messages](error-messages.md)
