# Repair Orders

Complete guide to managing repair orders in RepairCore.

## Overview

Repair orders are the core entity in RepairCore, tracking the entire lifecycle of a repair from intake to delivery.

## Creating a Repair Order

### From Admin Panel

1. Navigate to **Repair Orders**
2. Click **Create New Order**
3. Fill in required information
4. Save the order

### Order Information

**Customer Details**
- Customer selection or creation
- Contact information
- Delivery preferences

**Device Information**
- Device type and model
- Serial number/IMEI
- Device condition
- Problem description

**Services & Parts**
- Add repair services
- Add required parts
- Pricing and tax calculation

**Assignment**
- Assign to technician
- Set priority
- Add labels

## Order Statuses

- **Draft** - Order being created
- **Pending** - Awaiting approval
- **In Progress** - Repair in progress
- **Completed** - Repair finished
- **Delivered** - Returned to customer
- **Cancelled** - Order cancelled

## Order Fields

### Basic Information
- Order code (auto-generated)
- Customer
- Device
- Status
- Priority

### Financial Information
- Subtotal
- Tax
- Discount
- Total
- Paid amount
- Balance

### Dates
- Created date
- Expected completion date
- Actual completion date
- Delivery date

### Additional Information
- Notes
- Internal notes
- Warranty information
- Custom fields (via metadata)

## Managing Orders

### Viewing Orders

**List View**
- Filter by status
- Search by order code or customer
- Sort by date, status, etc.
- Bulk actions

**Detail View**
- Complete order information
- Progress timeline
- Payment history
- Documents

### Updating Orders

1. Open order detail
2. Click **Edit**
3. Update information
4. Save changes

### Adding Progress Logs

1. Open order detail
2. Click **Add Progress Log**
3. Enter notes and status update
4. Attach photos if needed
5. Save

### Processing Payments

1. Open order detail
2. Click **Add Payment**
3. Enter payment details
4. Save payment record

### Generating Documents

**Invoice**
- Click **Generate Invoice**
- Download or email PDF

**Receipt**
- Click **Generate Receipt**
- Print or email

## Permissions

Required permissions:
- `repair-orders.view` - View orders
- `repair-orders.create` - Create orders
- `repair-orders.edit` - Edit orders
- `repair-orders.delete` - Delete orders

---

Next: [Order Workflow](order-workflow.md)
