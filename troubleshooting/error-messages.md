# Error Messages

Understanding and resolving error messages.

## Permission Errors

### "You do not have permission to access this page"

**Cause:** Your role doesn't have the required permission.

**Solution:** Contact your administrator to request access.

### "Unauthorized action"

**Cause:** Attempting an action your role cannot perform.

**Solution:** Check with your administrator about your permissions.

## Validation Errors

### "The email field is required"

**Cause:** Required field was left empty.

**Solution:** Fill in all required fields (marked with *).

### "The email has already been taken"

**Cause:** Email address already exists in the system.

**Solution:** Use a different email or find the existing record.

### "The field must be a valid email address"

**Cause:** Email format is incorrect.

**Solution:** Enter a valid email (e.g., name@example.com).

## Order Errors

### "Customer is required"

**Cause:** No customer selected for the order.

**Solution:** Select or create a customer before saving.

### "Device is required"

**Cause:** No device selected for the order.

**Solution:** Select or create a device for the customer.

### "Insufficient stock"

**Cause:** Part doesn't have enough stock.

**Solution:** 
- Check stock levels
- Enable backorder in settings
- Adjust quantity

## File Upload Errors

### "The file must be an image"

**Cause:** Uploaded file is not a valid image format.

**Solution:** Use JPG, PNG, GIF, or WebP format.

### "The file may not be greater than X kilobytes"

**Cause:** File size exceeds the limit.

**Solution:** Compress or resize the image before uploading.

## Session Errors

### "Your session has expired"

**Cause:** You've been inactive too long.

**Solution:** Log in again to continue.

### "CSRF token mismatch"

**Cause:** Page was open too long or browser issue.

**Solution:** Refresh the page and try again.

## Database Errors

### "Record not found"

**Cause:** The item you're looking for doesn't exist or was deleted.

**Solution:** 
- Check if the record was deleted
- Verify you have the correct ID
- Go back and select again

## Email Errors

### "Failed to send email"

**Cause:** Email configuration issue.

**Solution:**
1. Check Settings > Email
2. Verify SMTP credentials
3. Test email connection

## Payment Errors

### "Invalid payment amount"

**Cause:** Payment amount is invalid (zero, negative, or exceeds balance).

**Solution:** Enter a valid positive amount.

## General Errors

### "Something went wrong"

**Cause:** Unexpected server error.

**Solution:**
1. Refresh the page
2. Try the action again
3. Contact support if persists

### "Page not found (404)"

**Cause:** The page doesn't exist.

**Solution:**
- Check the URL
- Use navigation menu
- Go back to dashboard

### "Server error (500)"

**Cause:** Internal server problem.

**Solution:**
1. Wait a moment and try again
2. Contact support if persists

---

Next: [FAQ](../appendix/faq.md)
