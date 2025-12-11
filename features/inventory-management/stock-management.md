# Stock Management

RepairCore provides comprehensive stock management with automatic tracking, backorder support, and detailed logging.

## Overview

The stock management system:
- Tracks stock levels for all parts
- Automatically deducts stock when parts are added to repair orders
- Returns stock when parts are removed or orders are cancelled
- Supports backorder functionality
- Maintains detailed stock movement logs

## Stock Tracking

### Part Stock Fields

Each part has the following stock-related fields:
- **quantity_in_stock** - Current available stock
- **low_stock_threshold** - Alert threshold for low stock
- **reorder_quantity** - Suggested reorder amount

### Stock Adjustments

Stock can be adjusted through:
1. **Repair Orders** - Automatic deduction/return
2. **Manual Adjustment** - Admin manual changes
3. **Initial Stock** - Setting initial inventory

## Stock Logs

All stock movements are recorded in the `stock_logs` table.

### Log Entry Fields

| Field | Description |
|-------|-------------|
| part_id | The part being adjusted |
| quantity_change | Amount changed (+/-) |
| quantity_before | Stock before change |
| quantity_after | Stock after change |
| reason | Reason code |
| ref_id | Reference ID (e.g., repair_item_id) |
| parent_ref_id | Parent reference (e.g., repair_order_id) |
| description | Human-readable description |
| created_by | User who made the change |

### Reason Codes

| Code | Description |
|------|-------------|
| initial_stock | Initial stock setup |
| manual_adjustment | Manual admin adjustment |
| repair_item_add | Part added to repair order |
| repair_item_remove | Part removed from repair order |
| repair_item_update | Part quantity updated |
| order_cancel | Order cancelled, stock returned |
| backorder_fulfill | Backorder fulfilled |

## Backorder Support

When stock is insufficient, RepairCore can handle backorders.

### Settings

Configure in **Admin > Settings > Inventory**:
- **allow_backorder** - Enable/disable backorder functionality

### How Backorders Work

1. Part added to order with quantity > available stock
2. Available stock is deducted immediately
3. Remaining quantity is marked as backorder
4. When stock arrives, backorders can be fulfilled

### Fulfilling Backorders

1. Navigate to **Admin > Parts > [Part] > Backorders**
2. Select orders to fulfill
3. Click "Fulfill Selected"
4. Stock is deducted and backorder quantities updated

## HasStockManagement Trait

Located at `App\Traits\HasStockManagement`. Used by the Part model.

### Methods

```php
// Adjust stock with logging
$part->adjustStock($amount, $reason, $refId, $parentRefId, $description);

// Deduct stock for repair
$part->deductStockForRepair($quantity, $repairItemId, $repairOrderId, $description);

// Return stock from repair
$part->returnStockFromRepair($quantity, $repairItemId, $repairOrderId, $reason, $description);

// Set initial stock
$part->setInitialStock($quantity, $description);

// Manual adjustment
$part->manualAdjustment($amount, $description);

// Check stock availability
$part->hasStock($quantity);

// Check if backorder allowed
Part::isBackorderAllowed();

// Calculate backorder quantity
$part->calculateBackorderQty($requestedQty);

// Check if can fulfill order
$part->canFulfillOrder($quantity);

// Get available for order
$part->getAvailableForOrder($requestedQty);

// Fulfill backorders for selected items
$part->fulfillBackorders($repairItemIds);
```

## ManagesPartStock Trait

Located at `App\Traits\ManagesPartStock`. Used by the RepairOrder model.

### Methods

```php
// Add part with automatic stock management
$result = $order->addPartWithStock($part, $quantity, $attributes);
// Returns: ['success' => bool, 'message' => string, 'repair_item' => RepairItem|null]

// Remove part and return stock
$result = $order->removePartWithStock($repairItem);

// Update part quantity with stock adjustment
$result = $order->updatePartQuantityWithStock($repairItem, $newQuantity);

// Return all stock (for order cancellation)
$order->returnAllPartStock($reason, $statusLabel);

// Check if order has backordered items
$order->hasBackorderedItems();

// Get total backorder quantity
$order->getTotalBackorderQty();
```

## Usage Examples

### Adding Part to Order

```php
$result = $order->addPartWithStock($part, 2, [
    'description' => 'Screen replacement',
    'unit_price' => 150000,
]);

if (!$result['success']) {
    // Handle error
    session()->flash('error', $result['message']);
}
```

### Cancelling Order

```php
// Return all stock when cancelling
$order->returnAllPartStock(
    StockLog::REASON_ORDER_CANCEL,
    __('Order Cancelled')
);
```

### Manual Stock Adjustment

```php
// Add stock
$part->manualAdjustment(10, 'Received from supplier');

// Remove stock
$part->manualAdjustment(-5, 'Damaged items removed');
```

## Stock Reports

Navigate to **Admin > Reports > Inventory** for:
- Current stock levels
- Low stock alerts
- Stock movement history
- Export to Excel/CSV

### Report Features

- Filter by part category, brand
- Date range for movements
- Export stock logs
- View backorder status

## Settings

| Setting | Description |
|---------|-------------|
| allow_backorder | Allow orders when stock insufficient |
| low_stock_notification | Send alerts for low stock |
| stock_tracking_enabled | Enable/disable stock tracking |

---

Next: [Parts Catalog](parts-catalog.md)
