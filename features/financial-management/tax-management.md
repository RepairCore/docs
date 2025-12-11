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

[image_create_tax_class]

### Tax Class Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Name** | Display name (e.g., "VAT 10%") | Yes |
| **Code** | Unique code (e.g., "VAT_10") | Yes |
| **Rate** | Tax percentage (0-100) | Yes |
| **Tax Inclusive** | Prices already include tax | No |
| **Calculation Method** | Per item or subtotal | Yes |
| **Rounding Mode** | How to round tax amounts | Yes |
| **Status** | Active or Inactive | Yes |

## Tax Types

### Tax Exclusive (Default)

Prices do NOT include tax. Tax is added on top.

**Example:**
- Part price: 100,000
- Tax rate: 10%
- Tax amount: 10,000
- Customer pays: 110,000

### Tax Inclusive

Prices already include tax. Tax is calculated from the inclusive price.

**Example:**
- Part price (inclusive): 110,000
- Tax rate: 10%
- Price before tax: 100,000
- Tax amount: 10,000

## Calculation Methods

### Per Item

Tax is calculated on each line item separately.

**Example:**
```
Item 1: 100,000 × 10% = 10,000 tax
Item 2: 200,000 × 10% = 20,000 tax
Total Tax: 30,000
```

### Subtotal

Tax is calculated on the order subtotal.

**Example:**
```
Subtotal: 300,000
Tax: 300,000 × 10% = 30,000
```

## Rounding Modes

| Mode | Description | Example (10.5) |
|------|-------------|----------------|
| **Round** | Standard rounding | 11 |
| **Ceiling** | Always round up | 11 |
| **Floor** | Always round down | 10 |

## Default Tax Classes

Set default tax classes in **Settings > Tax**:

- **Default for Parts** - Applied to new parts
- **Default for Services** - Applied to new services

Individual parts and services can override the default.

[image_default_tax_classes]

## Editing a Tax Class

1. Find the tax class in the list
2. Click **Edit**
3. Modify the fields (Code cannot be changed)
4. Click **Save**

## Deleting a Tax Class

1. Find the tax class in the list
2. Click **Delete**
3. Confirm deletion

> **Warning:** Deleting a tax class may affect items that use it.

## Toggle Status

Click the status badge to toggle between Active and Inactive.

Inactive tax classes:
- Cannot be selected for new items
- Still apply to existing orders

## Enable/Disable Tax

To disable tax globally:

1. Go to **Settings > Tax**
2. Uncheck **Enable Tax**
3. Save

When disabled, no tax is calculated on any orders.

---

Next: [Users](../user-management/users-roles.md)
