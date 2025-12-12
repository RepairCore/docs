# Invoice

Generate professional invoices from repair orders.

[image_invoice]

## Overview

RepairCore automatically generates invoices from repair orders. Invoices include all parts, services, taxes, and payment information.

## Generating an Invoice

1. Open a repair order
2. Click **Invoice** button
3. PDF opens in a new tab
4. Print or download

## Invoice Contents

### Header

- Company logo
- Company name and address
- Company tax number
- Invoice number and date

### Customer Information

- Customer name
- Customer address
- Customer phone/email

### Order Details

- Order code
- Order date
- Device information

### Items Table

| Column | Description |
|--------|-------------|
| **Item** | Part or service name |
| **Quantity** | Number of units |
| **Unit Price** | Price per unit |
| **Tax** | Tax amount |
| **Total** | Line total |

### Totals

- Subtotal (before tax)
- Tax breakdown by tax class
- Discount (if applied)
- **Grand Total**

### Payment Information

- Amount paid
- Balance due
- Payment history

### Footer

- Warranty information
- Terms and conditions
- Company contact details

## Invoice Number

Invoice numbers are automatically generated:
- Prefix: `INV`
- Date: `YYYYMMDD`
- Sequence: `0001`

Example: `INV202412120001`

## Status Requirements

Invoices can be generated when order status is:
- **Repairing** - Work in progress
- **Completed** - Repair finished
- **Delivered** - Device returned to customer

## Customizing Invoices

Invoice appearance is based on your settings:

1. **Company Information** - Set in Settings > Company
2. **Logo** - Upload in Settings > Company
3. **Tax Numbers** - Set in Settings > Company
4. **Terms** - Set in Settings > Company

## Printing Invoices

1. Generate the invoice (opens PDF)
2. Use browser's print function (Ctrl+P or Cmd+P)
3. Select printer or save as PDF

---

Next: [Receipt](receipt.md)
