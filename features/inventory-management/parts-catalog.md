# Parts Catalog

Manage your inventory of parts and components.

[image_parts_list]

## Overview

The parts catalog stores all parts and components you use for repairs. Each part tracks pricing, stock levels, and usage history.

## Viewing Parts

Navigate to **Admin > Inventory > Parts** to see all parts.

### List Features

- **Search** - Find by name, SKU, or barcode
- **Filter** - Filter by category, brand, stock status
- **Sort** - Sort by name, price, stock level
- **Bulk Actions** - Update status or delete multiple parts

[image_parts_index]

## Creating a Part

1. Navigate to **Admin > Inventory > Parts**
2. Click **Create Part**
3. Fill in part details
4. Click **Save**

[image_create_part]

### Part Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Name** | Part name | Yes |
| **SKU** | Stock keeping unit code | No |
| **Category** | Part category | No |
| **Brand** | Part brand/manufacturer | No |
| **Cost Price** | Your purchase cost | No |
| **Selling Price** | Price charged to customers | Yes |
| **Tax Class** | Tax applied to this part | No |
| **Stock Quantity** | Current stock level | No |
| **Low Stock Threshold** | Alert when stock falls below | No |
| **Barcode** | Barcode/UPC code | No |
| **Description** | Part description | No |

## Pricing

### Cost Price

The price you pay to purchase this part from suppliers. Used for profit calculations.

### Selling Price

The price charged to customers when this part is used in a repair.

### Tax Class

Select the tax class to apply to this part. If not set, the default tax class for parts is used (configured in Settings > Tax).

[image_part_pricing]

## Stock Management

### Current Stock

The quantity currently available in your inventory.

### Low Stock Threshold

When stock falls to or below this level, the part appears in low stock alerts.

### Stock Adjustments

To manually adjust stock:
1. Open part details
2. Click **Adjust Stock**
3. Enter adjustment amount (positive to add, negative to subtract)
4. Enter reason for adjustment
5. Click **Save**

[image_stock_adjustment]

### Automatic Stock Deduction

When you add a part to a repair order:
- Stock is automatically deducted
- A stock log entry is created

When you remove a part from an order:
- Stock is automatically returned
- A stock log entry is created

### Backorder

If backorder is enabled (in Settings > Inventory):
- Parts can be added to orders even when out of stock
- Backorder quantity is tracked

## Stock History

View all stock movements for a part:

1. Open part details
2. Go to **Stock History** tab

Shows:
- Date and time
- Quantity change
- Reason (order, adjustment, etc.)
- Related order (if applicable)

[image_stock_history]

## Editing a Part

1. Find the part in the list
2. Click **Edit** or the part name
3. Modify the information
4. Click **Save**

## Deleting a Part

1. Open part details
2. Click **Delete** button
3. Confirm deletion

> **Note:** Deleting a part does not affect existing repair orders that used it.

---

Next: [Part Categories](part-categories.md)
