# Repair Orders

Complete guide to managing repair orders in RepairCore.

[image_repair_orders_list]

## Overview

Repair orders track the entire lifecycle of a repair from customer intake to final delivery. Each order contains customer information, device details, parts used, services performed, and payment records.

## Viewing Repair Orders

Navigate to **Admin > Repair Orders** to see all orders.

[image_repair_orders_index]

### List Features

- **Search** - Find orders by code, customer name, or device
- **Filter** - Filter by status, date range, technician
- **Sort** - Sort by date, status, customer
- **Bulk Actions** - Change status or delete multiple orders

## Creating a Repair Order

1. Navigate to **Admin > Repair Orders**
2. Click **Create New Order**
3. Fill in the order information
4. Click **Save**

[image_create_repair_order]

### Step 1: Customer & Device

Select or create a customer and their device:

1. **Search Customer** - Type customer name or phone
2. **Create New** - Click to add new customer if not found
3. **Select Device** - Choose from customer's devices or add new

[image_customer_device_section]

### Step 2: Problem Description

Enter the reported problem:
- **Problem Description** - What the customer reported
- **Condition Notes** - Device condition at intake
- **Priority** - Low, Normal, High, or Urgent

### Step 3: Add Parts & Services

Add parts and services to the order:

**Adding Parts:**
1. Click **Add Part**
2. Search for part by name or SKU
3. Enter quantity
4. Part is added with price and tax

**Adding Services:**
1. Click **Add Service**
2. Search for service
3. Adjust price if needed

[image_parts_services_section]

### Step 4: Save Order

Click **Save** to create the order. An order code is automatically generated.

## Order Statuses

| Status | Description |
|--------|-------------|
| **Draft** | Order being created |
| **Pending** | Awaiting diagnosis or approval |
| **In Progress** | Repair work in progress |
| **Waiting Parts** | Waiting for parts to arrive |
| **Completed** | Repair finished |
| **Delivered** | Device returned to customer |
| **Cancelled** | Order cancelled |

[image_order_status_flow]

### Changing Status

1. Open the repair order
2. Go to **Status** tab
3. Select new status
4. Add notes (optional)
5. Click **Update Status**

## Order Tabs

### Customer & Device

View and edit customer and device information.

### Parts & Services

Manage parts and services on the order:
- Add/remove items
- Adjust quantities
- View pricing and tax

### Status

Change order status and view status history.

### Assignment

Assign technicians to work on the order:
1. Click **Assign Technician**
2. Select technician from list
3. Add notes (optional)

[image_assignment_section]

### Diagnostic

Record diagnostic findings:
- Problem diagnosis
- Recommended repairs
- Estimated cost

### Payment

Record customer payments:
1. Click **Add Payment**
2. Enter amount
3. Select payment method
4. Add notes (optional)

[image_payment_section]

### Delivery

Record delivery information:
- Delivery date
- Received by
- Delivery notes

### Labels

Assign labels to organize orders:
- Click to add/remove labels
- Labels help filter and categorize orders

### Progress

View and add progress log entries:
1. Click **Add Progress**
2. Enter description of work done
3. Add time spent (optional)
4. Attach photos (optional)

[image_progress_section]

### Warranty

Configure warranty for the order:
- Warranty period (months)
- Warranty notes
- View warranty expiry date

## Generating Documents

Generate professional documents from orders:

| Document | Description |
|----------|-------------|
| **Quotation** | Price quote for customer approval |
| **Invoice** | Final invoice with all charges |
| **Receipt** | Payment receipt |
| **Warranty** | Warranty certificate |

[image_document_buttons]

### How to Generate

1. Open the repair order
2. Click the document button (Quotation, Invoice, etc.)
3. PDF opens in new tab
4. Print or download

## Deleting Orders

1. Open the repair order
2. Click **Delete** button
3. Confirm deletion

> **Note:** Deleted orders are soft-deleted and can be restored if needed.

---

Next: [Order Workflow](order-workflow.md)
