# Stock Management

Track and manage your parts inventory.

## Overview

Stock management tracks the quantity of each part in your inventory. The system automatically adjusts stock when parts are used in repair orders.

## Key Features

- **Automatic Stock Tracking** - Stock is deducted when parts are added to orders
- **Stock History** - Complete history of all stock movements
- **Backorder Support** - Allow orders even when stock is insufficient
- **Low Stock Alerts** - Warnings when stock falls below threshold

## Viewing Stock

### On Parts List

The parts list shows current stock for each part:
- Green: Stock is healthy
- Yellow: Stock is low (at or below threshold) 

[image_parts_stock_status]

### On Part Details

Open a part to see detailed stock information:
- Current stock quantity
- Low stock threshold
- Stock history

## Stock Adjustments

### Automatic Adjustments

Stock is automatically adjusted when:
- **Part added to order** - Stock is deducted
- **Part removed from order** - Stock is returned
- **Order cancelled** - All parts stock is returned

### Manual Adjustments

To manually adjust stock:

1. Open the part details
2. Click **Adjust Stock**
3. Enter quantity:
   - Positive number to add stock (e.g., +10)
   - Negative number to subtract (e.g., -5)
4. Enter reason for adjustment
5. Click **Save**

[image_manual_stock_adjustment]

## Stock History

View all stock movements for a part:

1. Open part details
2. Go to **Stock History** tab

Each entry shows:
- Date and time
- Quantity change (+/-)
- Reason for change
- Related order (if applicable)
- Notes

[image_stock_history_tab]

## Backorder

When stock is insufficient but backorder is enabled:

### How It Works

1. Part has 5 in stock, order needs 8
2. System deducts available 5 (stock becomes 0)
3. Remaining 3 is marked as backorder
4. Order shows backorder indicator

### Enabling Backorder

1. Go to **Settings > Inventory**
2. Enable **Allow Backorder**
3. Save settings

### Viewing Backorders

Orders with backorders show a warning indicator. View backorder quantity on the order's parts list.

[image_backorder_indicator]

## Low Stock Alerts

### Setting Threshold

Each part can have its own low stock threshold:

1. Edit the part
2. Set **Low Stock Threshold** (e.g., 5)
3. Save

When stock falls to or below this level, the part is flagged.

### Default Threshold

Set a default threshold for new parts in **Settings > Inventory**.

### Viewing Low Stock

Low stock parts appear:
- On the dashboard widget
- In the parts list (filtered)
- With warning indicators

[image_low_stock_alert]

## Best Practices

1. **Set thresholds** - Configure low stock thresholds for important parts
2. **Regular audits** - Periodically verify physical stock matches system
3. **Use adjustments** - Record all stock changes with reasons
4. **Monitor backorders** - Fulfill backorders promptly

---

Next: [Service Catalog](../service-management/service-catalog.md)
