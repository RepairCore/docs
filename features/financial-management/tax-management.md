# Tax Management

RepairCore supports a flexible multi-tax class system for managing different tax rates and calculation methods.

## Overview

The tax system allows you to:
- Create multiple tax classes (e.g., VAT Standard, VAT Reduced, Service Tax)
- Set different tax rates for parts and services
- Configure tax-inclusive or tax-exclusive pricing
- Choose calculation and rounding methods

## Tax Classes

### What is a Tax Class?

A Tax Class defines a specific tax configuration with:
- **Name** - Display name (e.g., "VAT - Standard")
- **Code** - Unique identifier (e.g., "VAT_STD")
- **Rate** - Tax percentage (e.g., 10%)
- **Type** - Tax Inclusive or Tax Exclusive
- **Calculation Method** - Per item or on subtotal
- **Rounding Mode** - Round, Ceil, or Floor
- **Tax Number** - Optional tax registration number
- **Status** - Active or Inactive

### Managing Tax Classes

Navigate to **Admin > Settings > Tax** to manage tax classes.

**Creating a Tax Class:**
1. Click "Add New" button
2. Fill in tax class details
3. Save

**Editing a Tax Class:**
1. Click "Edit" on the tax class row
2. Update details (code is read-only after creation)
3. Save

**Deleting a Tax Class:**
1. Click "Delete" on the tax class row
2. Confirm deletion

### Default Tax Classes

You can set default tax classes for:
- **Parts** - Applied automatically when adding parts to orders
- **Services** - Applied automatically when adding services to orders

Configure defaults in **Admin > Settings > Tax**.

## Tax Calculation

### Tax Exclusive (Default)

Price does not include tax. Tax is added on top.

```
Subtotal: $100
Tax (10%): $10
Total: $110
```

### Tax Inclusive

Price already includes tax. Tax is extracted from the price.

```
Price (incl. tax): $110
Base Price: $100
Tax (10%): $10
```

### Calculation Methods

**Per Item:**
Tax is calculated for each line item, then summed.

**On Subtotal:**
Tax is calculated on the order subtotal.

### Rounding Modes

- **Round** - Standard rounding (default)
- **Ceil** - Always round up
- **Floor** - Always round down

## Helper Functions

### Check if Tax is Enabled

```php
if (tax_enabled()) {
    // Tax calculations apply
}
```

### Get Default Tax Classes

```php
// For parts
$taxClass = get_default_tax_class_for_parts();

// For services
$taxClass = get_default_tax_class_for_services();
```

### Calculate Tax

```php
// Using a specific tax class
$taxClass = get_tax_class($taxClassId);
$taxAmount = $taxClass->calculateTax($amount);

// Get price with tax
$priceWithTax = $taxClass->calculatePriceWithTax($amount);

// Get price without tax (from inclusive price)
$priceWithoutTax = $taxClass->calculatePriceWithoutTax($amount);
```

### Get Tax Data for Items

```php
// Returns tax details for an amount
$taxData = get_tax_data($amount, $taxClassId, 'part');
// Returns: ['tax_amount', 'tax_rate', 'tax_inclusive', 'tax_class_id', 'tax_class']
```

## TaxClass Model

Located at `App\Models\TaxClass`.

### Properties

| Property | Type | Description |
|----------|------|-------------|
| name | string | Display name |
| code | string | Unique code |
| description | string | Optional description |
| rate | decimal | Tax rate percentage |
| is_inclusive | boolean | Tax inclusive pricing |
| calculation_method | string | 'per_item' or 'subtotal' |
| rounding_mode | string | 'round', 'ceil', or 'floor' |
| tax_number | string | Tax registration number |
| status | string | 'active' or 'inactive' |

### Methods

```php
// Get active tax classes
TaxClass::active()->get();

// Get by code
TaxClass::byCode('VAT_STD');

// Calculate tax
$taxClass->calculateTax($amount);

// Apply rounding
$taxClass->applyRounding($amount);

// Calculate prices
$taxClass->calculatePriceWithTax($amount);
$taxClass->calculatePriceWithoutTax($amount);
```

## Settings

| Setting | Description |
|---------|-------------|
| tax_enabled | Enable/disable tax system |
| default_tax_class_for_parts | Default tax class ID for parts |
| default_tax_class_for_services | Default tax class ID for services |

## Livewire Component

Tax classes are managed via a Livewire component:
- **Component:** `App\Http\Livewire\TaxClass\ManageTaxClasses`
- **View:** `resources/views/livewire/tax-class/manage-tax-classes.blade.php`

Features:
- Search by name or code
- Pagination
- Modal form for create/edit
- Toggle status
- Delete with confirmation

---

Next: [Multi-Currency](multi-currency.md)
