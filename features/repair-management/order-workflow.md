# Order Workflow

Understanding the repair order lifecycle.

[image_order_workflow]

## Overview

A repair order goes through several stages from intake to delivery. Understanding this workflow helps you manage repairs efficiently.

## Workflow Stages

### 1. Intake

When a customer brings a device:
1. Create a new repair order
2. Select or create customer
3. Add device information
4. Document the problem
5. Note device condition

[image_intake_stage]

### 2. Diagnostic

Examine the device:
1. Assign to technician
2. Diagnose the problem
3. Identify required parts/services
4. Estimate repair time
5. Add progress log

### 3. Quote & Approval

Get customer approval:
1. Add parts and services to order
2. System calculates total with tax
3. Generate quote document
4. Send to customer
5. Wait for approval

### 4. Repair

Perform the repair:
1. Change status to "In Progress"
2. Use required parts (stock deducted)
3. Perform services
4. Log progress regularly
5. Update status as work progresses

[image_repair_stage]

### 5. Quality Check

Verify the repair:
1. Test device functionality
2. Ensure repair quality
3. Document completion
4. Change status to "Completed"

### 6. Payment & Delivery

Complete the order:
1. Generate invoice
2. Record payment
3. Notify customer
4. Deliver device
5. Change status to "Delivered"

## Order Statuses

| Status | Description |
|--------|-------------|
| **Draft** | Order created, not yet submitted |
| **Pending** | Awaiting diagnostic or approval |
| **Approved** | Customer approved, ready for repair |
| **In Progress** | Repair work underway |
| **Completed** | Repair finished, awaiting payment/pickup |
| **Delivered** | Device returned to customer |
| **Cancelled** | Order cancelled |

[image_status_flow]

## Changing Status

1. Open the repair order
2. Click the status dropdown
3. Select new status
4. Add notes if needed
5. Save

> **Note:** Status changes are logged and may trigger notifications.

## Tips for Efficient Workflow

1. **Document everything** - Add photos and detailed notes
2. **Update status promptly** - Keep customers informed
3. **Log progress** - Track work performed
4. **Use assignments** - Distribute work among technicians
5. **Set priorities** - Handle urgent repairs first

---

Next: [Progress Logging](progress-logging.md)
