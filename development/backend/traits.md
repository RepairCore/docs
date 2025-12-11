# Traits

RepairCore uses several traits to provide reusable functionality across models.

## Available Traits

### HasSlug

Located at `App\Traits\HasSlug`. Automatically generates URL-friendly slugs.

```php
use App\Traits\HasSlug;

class Post extends BaseModel
{
    use HasSlug;
    
    protected function slugOptions(): array
    {
        return [
            'source' => 'title',      // Field to generate slug from
            'field' => 'slug',        // Field to store slug
            'unique' => true,         // Ensure uniqueness
            'separator' => '-',       // Word separator
        ];
    }
}
```

### HasMeta

Located at `App\Traits\HasMeta`. Provides key-value metadata storage.

```php
use App\Traits\HasMeta;

class RepairOrder extends BaseModel
{
    use HasMeta;
}

// Usage
$order->setMeta('custom_field', 'value');
$value = $order->getMeta('custom_field', 'default');
$order->deleteMeta('custom_field');
```

### HasSafeCode

Located at `App\Traits\HasSafeCode`. Generates unique, safe codes for entities.

```php
use App\Traits\HasSafeCode;

class RepairOrder extends BaseModel
{
    use HasSafeCode;
    
    protected static function codePrefix(): string
    {
        return 'RO';
    }
    
    protected static function codeLength(): int
    {
        return 8;
    }
}

// Generates codes like: RO-20241211-0001
```

### HasStatus

Located at `App\Traits\HasStatus`. Provides status management helpers.

```php
use App\Traits\HasStatus;

class Part extends BaseModel
{
    use HasStatus;
}

// Usage
$part->isActive();
$part->isDraft();
Part::active()->get();
```

### HasStockManagement

Located at `App\Traits\HasStockManagement`. Used by Part model for stock operations.

```php
use App\Traits\HasStockManagement;

class Part extends BaseModel
{
    use HasStockManagement;
}

// Methods available:
$part->adjustStock($amount, $reason, $refId, $parentRefId, $description);
$part->deductStockForRepair($quantity, $repairItemId, $repairOrderId);
$part->returnStockFromRepair($quantity, $repairItemId, $repairOrderId, $reason);
$part->setInitialStock($quantity, $description);
$part->manualAdjustment($amount, $description);
$part->hasStock($quantity);
$part->canFulfillOrder($quantity);
$part->fulfillBackorders($repairItemIds);
```

### ManagesPartStock

Located at `App\Traits\ManagesPartStock`. Used by RepairOrder model for part stock management.

```php
use App\Traits\ManagesPartStock;

class RepairOrder extends BaseModel
{
    use ManagesPartStock;
}

// Methods available:
$order->addPartWithStock($part, $quantity, $attributes);
$order->removePartWithStock($repairItem);
$order->updatePartQuantityWithStock($repairItem, $newQuantity);
$order->returnAllPartStock($reason, $statusLabel);
$order->hasBackorderedItems();
$order->getTotalBackorderQty();
```

### RepairOrderPermissions

Located at `App\Traits\RepairOrderPermissions`. Provides permission checking for repair orders.

```php
use App\Traits\RepairOrderPermissions;

class RepairOrder extends BaseModel
{
    use RepairOrderPermissions;
}

// Methods available:
$order->canViewOrder($user);
$order->canEditOrder($user);
$order->canDeleteOrder($user);
$order->canChangeStatus($user);
$order->canAssign($user);
$order->canAddPayment($user);
```

### Notifiable

Located at `App\Traits\Notifiable`. Extends Laravel's notifiable trait with custom functionality.

```php
use App\Traits\Notifiable;

class User extends Authenticatable
{
    use Notifiable;
}
```

## Creating Custom Traits

### Best Practices

1. **Single Responsibility** - Each trait should handle one concern
2. **No State Conflicts** - Avoid property name collisions
3. **Document Methods** - Add PHPDoc for all public methods
4. **Use Abstract Methods** - For required implementations

### Example Custom Trait

```php
<?php

namespace App\Traits;

trait HasPriority
{
    public function setPriority(string $priority): void
    {
        $this->priority = $priority;
        $this->save();
    }
    
    public function isHighPriority(): bool
    {
        return $this->priority === 'high';
    }
    
    public function scopeHighPriority($query)
    {
        return $query->where('priority', 'high');
    }
    
    public static function getPriorityOptions(): array
    {
        return [
            'low' => __('low'),
            'normal' => __('normal'),
            'high' => __('high'),
            'urgent' => __('urgent'),
        ];
    }
}
```

## Trait Location

All traits are stored in:
```
repair-core/app/Traits/
├── HasMeta.php
├── HasSafeCode.php
├── HasSlug.php
├── HasStatus.php
├── HasStockManagement.php
├── ManagesPartStock.php
├── Notifiable.php
└── RepairOrderPermissions.php
```

---

Next: [Helpers](helpers.md)
