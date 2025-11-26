# Order Workflow

Understanding the repair order lifecycle and workflow.

## Standard Workflow

### 1. Intake
- Customer brings device
- Staff creates order
- Document device condition
- Capture problem description

### 2. Diagnostic
- Technician examines device
- Document findings
- Identify required parts/services
- Estimate repair time

### 3. Quote Generation
- System calculates costs
- Parts + Services + Tax
- Generate quote document
- Send to customer

### 4. Customer Approval
- Customer reviews quote
- Approves or declines
- Via email link or in-person

### 5. Assignment
- Order assigned to technician
- Priority set
- Expected completion date

### 6. Repair
- Technician performs repair
- Log progress updates
- Update status
- Document work performed

### 7. Quality Check
- Supervisor reviews work
- Test device functionality
- Verify repair quality
- Approve or request rework

### 8. Payment
- Generate invoice
- Customer pays
- Record payment
- Update order status

### 9. Delivery
- Notify customer
- Schedule pickup
- Deliver device
- Get customer signature

### 10. Follow-up
- Send satisfaction survey
- Request review
- Warranty information

## Custom Workflows

### Express Repair
- Skip diagnostic
- Pre-approved services
- Same-day completion

### Mail-in Repair
- Customer ships device
- Remote communication
- Ship back when complete

### Warranty Repair
- Verify warranty status
- No payment required
- Special handling

## Status Transitions

```
Draft → Pending → Approved → In Progress → Quality Check → Completed → Delivered
                     ↓
                 Cancelled
```

## Automation

### Automatic Notifications
- Status changes
- Payment reminders
- Completion notifications
- Delivery ready alerts

### Automatic Actions
- Status updates based on events
- Assignment based on workload
- Priority escalation

---

Next: [Order Tracking](order-tracking.md)
