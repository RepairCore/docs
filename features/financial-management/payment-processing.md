# Payment Processing

Record and track customer payments for repair orders.

[image_payments_section]

## Overview

RepairCore tracks payments for each repair order. Record partial or full payments and view payment history.

## Recording a Payment

1. Open a repair order
2. Go to **Payment** tab
3. Click **Add Payment**
4. Fill in payment details
5. Click **Save**

[image_add_payment_form]

### Payment Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Amount** | Payment amount | Yes |
| **Payment Method** | How payment was made | Yes |
| **Date** | Payment date | Yes |
| **Reference** | Transaction reference | No |
| **Notes** | Additional notes | No |

## Payment Methods

Common payment methods:
- **Cash** - Cash payment
- **Card** - Credit/debit card
- **Bank Transfer** - Wire transfer
- **Mobile Payment** - Mobile wallet (MoMo, ZaloPay, etc.)
- **Other** - Other methods

## Payment Status

Orders show payment status based on balance:

| Status | Description |
|--------|-------------|
| **Unpaid** | No payments recorded |
| **Partial** | Some payment received, balance remaining |
| **Paid** | Full amount paid |
| **Overpaid** | Paid more than total (refund may be needed) |

[image_payment_status_badges]

## Viewing Payments

### On Order

Open a repair order and go to **Payment** tab to see:
- Total amount due
- Amount paid
- Balance remaining
- Payment history

### Payment History

Each payment shows:
- Date
- Amount
- Payment method
- Reference
- Notes
- Recorded by

[image_payment_history]

## Editing a Payment

1. Open the repair order
2. Go to **Payment** tab
3. Find the payment in history
4. Click **Edit**
5. Modify details
6. Click **Save**

## Deleting a Payment

1. Open the repair order
2. Go to **Payment** tab
3. Find the payment in history
4. Click **Delete**
5. Confirm deletion

> **Warning:** Deleting a payment updates the order balance.

## Generating Receipt

After recording payment:

1. Open the repair order
2. Click **Receipt** button
3. PDF opens in new tab
4. Print or download

[image_receipt_button]

---

Next: [Tax Classes](tax-management.md)
