# Livewire Components

RepairCore uses Livewire 3 for reactive UI components, with a custom namespace configuration.

## Namespace Configuration

**Important:** Livewire components use `App\Http\Livewire\` namespace, NOT the default `App\Livewire\`.

```
repair-core/app/Http/Livewire/
├── BaseComponent.php
├── Device/
├── Frontend/
├── Installer/
├── Part/
├── RepairOrder/
└── TaxClass/
```

## BaseComponent

All Livewire components should extend `BaseComponent`:

```php
<?php

namespace App\Http\Livewire\RepairOrder;

use App\Http\Livewire\BaseComponent;

class StatusSection extends BaseComponent
{
    public $order;
    
    public function mount($order)
    {
        $this->order = $order;
    }
    
    public function render()
    {
        return view('livewire.repair-order.status-section');
    }
}
```

## Creating Components

### 1. Create Component Class

```php
<?php

namespace App\Http\Livewire\Part;

use App\Http\Livewire\BaseComponent;
use App\Models\Part;

class StockAdjustment extends BaseComponent
{
    public Part $part;
    public int $quantity = 0;
    public string $description = '';
    
    protected $rules = [
        'quantity' => 'required|integer|not_in:0',
        'description' => 'required|string|max:500',
    ];
    
    public function mount(Part $part)
    {
        $this->part = $part;
    }
    
    public function adjust()
    {
        $this->validate();
        
        $this->part->manualAdjustment($this->quantity, $this->description);
        
        session()->flash('success', __('stock_adjusted_successfully'));
        $this->reset(['quantity', 'description']);
    }
    
    public function render()
    {
        return view('livewire.part.stock-adjustment');
    }
}
```

### 2. Create View

```blade
{{-- resources/views/livewire/part/stock-adjustment.blade.php --}}
<div>
    <form wire:submit="adjust">
        <div class="mb-3">
            <label class="form-label">{{ __('quantity') }}</label>
            <input type="number" wire:model="quantity" class="form-control">
            @error('quantity') <span class="text-danger">{{ $message }}</span> @enderror
        </div>
        
        <div class="mb-3">
            <label class="form-label">{{ __('description') }}</label>
            <textarea wire:model="description" class="form-control"></textarea>
            @error('description') <span class="text-danger">{{ $message }}</span> @enderror
        </div>
        
        <button type="submit" class="btn btn-primary" wire:loading.attr="disabled">
            <span wire:loading wire:target="adjust">
                <i class="fas fa-spinner fa-spin"></i>
            </span>
            {{ __('save') }}
        </button>
    </form>
</div>
```

### 3. Use Component

```blade
<livewire:part.stock-adjustment :part="$part" />
```

## Existing Components

### Repair Order Components

Located at `App\Http\Livewire\RepairOrder\`:

| Component | Description |
|-----------|-------------|
| EditRepairOrder | Main repair order edit page |
| CustomerDeviceSection | Customer and device selection |
| PartsServicesSection | Parts and services management |
| StatusSection | Order status management |
| AssignmentSection | Technician assignment |
| PaymentSection | Payment recording |
| DiagnosticSection | Diagnostic notes |
| DeliverySection | Delivery information |
| LabelsSection | Label management |
| RepairProgressSection | Progress log entries |
| WarrantySection | Warranty information |

### Tax Class Components

Located at `App\Http\Livewire\TaxClass\`:

| Component | Description |
|-----------|-------------|
| ManageTaxClasses | CRUD for tax classes |

### Part Components

Located at `App\Http\Livewire\Part\`:

| Component | Description |
|-----------|-------------|
| BackorderList | Manage backorders |

### Frontend Components

Located at `App\Http\Livewire\Frontend\`:

| Component | Description |
|-----------|-------------|
| OrderTracking | Customer order tracking |
| ContactForm | Contact form |

## Full Page Components

For frontend, prefer full-page Livewire components:

```php
<?php

namespace App\Http\Livewire\Frontend;

use App\Http\Livewire\BaseComponent;
use Livewire\Attributes\Layout;

#[Layout('frontend.layouts.app')]
class OrderTracking extends BaseComponent
{
    public string $trackingCode = '';
    public $order = null;
    
    public function search()
    {
        $this->order = RepairOrder::where('code', $this->trackingCode)->first();
    }
    
    public function render()
    {
        return view('livewire.frontend.order-tracking');
    }
}
```

Register in routes:

```php
Route::get('/track', \App\Http\Livewire\Frontend\OrderTracking::class)
    ->name('frontend.track');
```

## Component Communication

### Events

```php
// Dispatch event
$this->dispatch('orderUpdated', orderId: $this->order->id);

// Listen in another component
#[On('orderUpdated')]
public function handleOrderUpdated($orderId)
{
    $this->loadOrder($orderId);
}
```

### Parent-Child

```php
// In parent
<livewire:child-component :data="$data" @saved="handleSaved" />

public function handleSaved($data)
{
    // Handle child event
}

// In child
$this->dispatch('saved', $data);
```

## Loading States

```blade
{{-- Button loading --}}
<button wire:loading.attr="disabled" wire:target="save">
    <span wire:loading wire:target="save">
        <i class="fas fa-spinner fa-spin"></i>
    </span>
    {{ __('save') }}
</button>

{{-- Section loading --}}
<div wire:loading.class="opacity-50">
    Content here
</div>
```

## Validation

```php
protected $rules = [
    'name' => 'required|string|max:255',
    'email' => 'required|email',
];

protected $messages = [
    'name.required' => 'Please enter a name.',
];

public function save()
{
    $this->validate();
    // Save logic
}
```

## Best Practices

1. **Extend BaseComponent** - Always extend the base component
2. **Use Correct Namespace** - `App\Http\Livewire\`, not `App\Livewire\`
3. **Organize by Module** - Group components in module folders
4. **Permission Checks** - Check permissions in mount() or actions
5. **Loading States** - Show loading indicators for async actions
6. **Flash Messages** - Use session flash for success/error messages
7. **Validation** - Define rules and validate before saving

---

Next: [Blade Templates](blade.md)
