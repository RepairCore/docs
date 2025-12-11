# Repair Orders

Complete guide to managing repair orders in RepairCore.

## Overview

Repair orders are the core entity in RepairCore, tracking the entire lifecycle of a repair from intake to delivery. The repair order system is built with Livewire components for a reactive, seamless editing experience.

## Creating a Repair Order

### From Admin Panel

1. Navigate to **Admin > Repair Orders**
2. Click **Create New Order**
3. The Livewire-based form opens with multiple sections
4. Fill in required information across tabs
5. Save the order

### Order Form Sections

The repair order form is organized into tabbed sections, each managed by a Livewire component:

| Section | Component | Description |
|---------|-----------|-------------|
| Customer & Device | CustomerDeviceSection | Select/create customer and device |
| Parts & Services | PartsServicesSection | Add parts and services with pricing |
| Status | StatusSection | Manage order status |
| Assignment | AssignmentSection | Assign technicians |
| Diagnostic | DiagnosticSection | Diagnostic notes and findings |
| Payment | PaymentSection | Record payments |
| Delivery | DeliverySection | Delivery information |
| Labels | LabelsSection | Assign workflow labels |
| Progress | RepairProgressSection | Progress log entries |
| Warranty | WarrantySection | Warranty information |

## Order Statuses

- **Draft** - Order being created
- **Pending** - Awaiting approval/diagnosis
- **In Progress** - Repair in progress
- **Waiting Parts** - Waiting for parts
- **Completed** - Repair finished
- **Delivered** - Returned to customer
- **Cancelled** - Order cancelled

## Order Fields

### Basic Information
- **Order code** - Auto-generated unique code (e.g., RO-20241211-0001)
- **Customer** - Linked customer record
- **Device** - Device being repaired
- **Status** - Current order status
- **Priority** - Low, Normal, High, Urgent

### Financial Information
- **Subtotal** - Sum of parts and services
- **Tax** - Calculated based on tax classes
- **Discount** - Applied discount amount
- **Total** - Final amount
- **Paid amount** - Total payments received
- **Balance** - Remaining amount due

### Dates
- **Created date** - Order creation timestamp
- **Expected completion** - Estimated completion date
- **Actual completion** - When repair was completed
- **Delivery date** - When delivered to customer

### Warranty Information
- **Warranty months** - Warranty period
- **Warranty expires at** - Calculated expiry date
- **Warranty notes** - Additional warranty terms
- **Warranty number** - Generated warranty certificate number

### Additional Information
- **Notes** - Customer-visible notes
- **Internal notes** - Staff-only notes
- **Custom fields** - Via metadata system (HasMeta trait)

## Parts & Services Management

### Adding Parts

Parts are added through the PartsServicesSection component:
1. Search for part by name or SKU
2. Select quantity
3. Part is added with automatic stock deduction
4. Tax is calculated based on part's tax class

**Stock Management:**
- Stock is automatically deducted when parts are added
- Stock is returned when parts are removed
- Backorder support when stock is insufficient

### Adding Services

1. Search for service
2. Adjust price if needed
3. Service is added with tax calculation

## Progress Logging

Track repair progress with detailed logs:

1. Navigate to **Progress** tab
2. Click **Add Progress Log**
3. Enter:
   - Status update
   - Description of work done
   - Time spent (optional)
   - Attach photos (optional)
4. Save log entry

Progress logs create a timeline of the repair process.

## Document Generation

Generate professional documents from repair orders:

### Available Documents

| Document | Route | Description |
|----------|-------|-------------|
| Quotation | `repair-orders/{id}/quotation` | Price quote for customer |
| Invoice | `repair-orders/{id}/invoice` | Final invoice |
| Receipt | `repair-orders/{id}/receipt` | Payment receipt |
| Warranty | `repair-orders/{id}/warranty` | Warranty certificate |

### Generating Documents

1. Open repair order
2. Click document button (Quotation, Invoice, Receipt, Warranty)
3. PDF is generated and displayed
4. Download or print

## Permissions

The RepairOrderPermissions trait provides granular permission checking:

| Permission | Description |
|------------|-------------|
| `repair-orders.view` | View orders |
| `repair-orders.create` | Create orders |
| `repair-orders.edit` | Edit orders |
| `repair-orders.delete` | Delete orders |
| `repair-orders.change-status` | Change order status |
| `repair-orders.assign` | Assign technicians |
| `repair-orders.add-payment` | Record payments |

### Permission Methods

```php
$order->canViewOrder($user);
$order->canEditOrder($user);
$order->canDeleteOrder($user);
$order->canChangeStatus($user);
$order->canAssign($user);
$order->canAddPayment($user);
```

## Routes

| Route | Method | Description |
|-------|--------|-------------|
| `admin/repair-orders` | GET | List orders |
| `admin/repair-orders/create` | GET | Create form (Livewire) |
| `admin/repair-orders/{id}` | GET | View order |
| `admin/repair-orders/{id}/edit` | GET | Edit form (Livewire) |
| `admin/repair-orders/{id}` | DELETE | Delete order |

## Model

Located at `App\Models\RepairOrder`.

### Traits Used
- **SoftDeletes** - Soft delete support
- **HasMeta** - Key-value metadata
- **HasSafeCode** - Unique code generation
- **ManagesPartStock** - Stock management for parts
- **RepairOrderPermissions** - Permission checking

### Relationships
- `customer()` - Customer record
- `device()` - Device being repaired
- `items()` - Repair items (parts/services)
- `assignments()` - Technician assignments
- `progressLogs()` - Progress log entries
- `labels()` - Assigned labels

---

Next: [Order Workflow](order-workflow.md)
