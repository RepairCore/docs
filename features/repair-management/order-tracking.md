# Order Tracking

Customer-facing order tracking system.

## Overview

RepairCore provides a secure order tracking system that allows customers to check their repair status without logging in.

## How It Works

### For Customers

1. Visit your website homepage
2. Enter order code in tracking form
3. Click "Track Order"
4. View order status and progress

### Security Features

**Rate Limiting**
- 5 attempts per minute per IP address
- Prevents brute force attacks

**Signed URLs**
- Time-limited access (5 hours default)
- Cryptographically signed
- Cannot be tampered with

**No Login Required**
- Customers don't need accounts
- Order code is sufficient
- Convenient access

## Tracking Page

### Information Displayed

**Order Details**
- Order code
- Device information
- Current status
- Expected completion date

**Progress Timeline**
- Status history
- Progress updates
- Timestamps

**Contact Information**
- Shop contact details
- Support options

### What Customers Cannot See

- Internal notes
- Pricing details (optional)
- Technician assignments
- Other sensitive data

## Configuration

### Settings

**Tracking URL Expiration**
- Default: 5 hours
- Configurable in settings

**Rate Limiting**
- Default: 5 attempts per minute
- Configurable per IP

**Information Display**
- Choose what customers can see
- Hide/show pricing
- Hide/show technician info

### Customization

**Tracking Page Design**
- Customize via Livewire component
- Located: `resources/views/livewire/frontend/order-tracking.blade.php`

**Email Notifications**
- Include tracking link in emails
- Automatic link generation

## Implementation

### Route

```php
Route::get('/track/{order:code}', OrderTracking::class)
    ->middleware(['throttle:5,1'])
    ->name('order.track');
```

### Livewire Component

```php
namespace App\Http\Livewire\Frontend;

class OrderTracking extends Component
{
    public $orderCode;
    public $order;
    
    public function mount($code)
    {
        $this->orderCode = $code;
        $this->loadOrder();
    }
    
    // ... implementation
}
```

## Best Practices

### For Shop Owners

1. **Update status regularly** - Keep customers informed
2. **Add progress notes** - Provide transparency
3. **Include tracking links** - In all customer emails
4. **Monitor access** - Check logs for suspicious activity

### For Customers

1. **Save tracking link** - Bookmark for easy access
2. **Check regularly** - Stay updated on progress
3. **Contact support** - If questions arise

---

Next: [Progress Logging](progress-logging.md)
