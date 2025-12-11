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

### 2. Diagnostic & Assignment

Examine the device and assign work:
1. Assign to technician(s)
2. Diagnose the problem
3. Identify required parts/services
4. Add progress log with findings

### 3. Repair

Perform the repair:
1. Change status to "In Progress"
2. Add required parts (stock deducted automatically)
3. Add services performed
4. Log progress regularly
5. Update status as work progresses

[image_repair_stage]

### 4. Completion

Finish the repair:
1. Test device functionality
2. Document completion in progress log
3. Change status to "Completed"

### 5. Payment & Delivery

Complete the order:
1. Generate invoice
2. Record payment
3. Deliver device to customer
4. Change status to "Delivered"

## Order Statuses

| Status | Description |
|--------|-------------|
| **Draft** | Order created, not yet submitted |
| **Pending** | Awaiting diagnostic or work |
| **In Progress** | Repair work underway |
| **Completed** | Repair finished, awaiting payment/pickup |
| **Delivered** | Device returned to customer |
| **Cancelled** | Order cancelled |

[image_status_flow]

## Changing Status

1. Open the repair order
2. Click the status dropdown
3. Select new status
4. Save

## Tips for Efficient Workflow

1. **Document everything** - Add photos and detailed notes
2. **Update status promptly** - Keep records current
3. **Log progress** - Track work performed
4. **Use assignments** - Distribute work among technicians

---

Next: [Technician Assignments](assignments.md)
