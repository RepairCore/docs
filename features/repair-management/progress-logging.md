# Progress Logging

Detailed activity tracking for repair orders.

## Overview

Progress logs provide a detailed timeline of all activities and status changes for a repair order.

## Creating Progress Logs

### Manual Logs

1. Open repair order
2. Click **Add Progress Log**
3. Fill in details:
   - Status update
   - Notes
   - Photos (optional)
   - Timestamp
4. Save log entry

### Automatic Logs

System automatically creates logs for:
- Status changes
- Assignment changes
- Payment received
- Documents generated

## Log Information

### Fields

**Status**
- Current order status
- Status change indicator

**Notes**
- Detailed description
- Work performed
- Issues found
- Next steps

**Photos**
- Before/after photos
- Problem documentation
- Repair documentation

**Metadata**
- Timestamp
- User who created log
- Visibility (internal/customer)

## Viewing Progress Logs

### In Admin Panel

**Timeline View**
- Chronological display
- All log entries
- Internal and customer-facing

**Filter Options**
- By date range
- By user
- By status
- Internal only

### In Customer Portal

**Customer View**
- Only customer-facing logs
- Simplified display
- Key updates only

## Log Types

### Status Updates
- Order status changed
- Progress milestones

### Work Performed
- Diagnostic results
- Repair actions
- Parts installed
- Testing completed

### Communication
- Customer contacted
- Customer feedback
- Special requests

### Issues
- Problems encountered
- Delays
- Additional work needed

## Best Practices

### For Technicians

1. **Log regularly** - Update after each work session
2. **Be detailed** - Describe work performed
3. **Add photos** - Document condition and work
4. **Mark visibility** - Internal vs customer-facing

### For Managers

1. **Review logs** - Monitor progress
2. **Quality check** - Ensure proper documentation
3. **Customer communication** - Use logs for updates

### Writing Good Logs

**Good Examples:**
- "Replaced LCD screen. Tested touch functionality. All working properly."
- "Diagnosed motherboard issue. Waiting for replacement part (ETA 2 days)."
- "Customer approved additional repair. Starting work on battery replacement."

**Bad Examples:**
- "Fixed it"
- "Working on it"
- "Done"

## Permissions

Required permissions:
- `progress-logs.view` - View logs
- `progress-logs.create` - Create logs
- `progress-logs.edit` - Edit logs
- `progress-logs.delete` - Delete logs

---

Next: [Assignments](assignments.md)
