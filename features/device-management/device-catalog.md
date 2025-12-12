# Devices

Manage customer devices that come in for repair.

[image_devices_list]

## Overview

Devices are linked to customers and repair orders. Each device stores information like brand, model, serial number, and repair history.

## Viewing Devices

Navigate to **Admin > Devices** to see all devices.

### List Features

- **Search** - Find by model, serial number, or customer
- **Filter** - Filter by device type, brand
- **Sort** - Sort by date, customer name

## Creating a Device

### From Devices Page

1. Navigate to **Admin > Devices**
2. Click **Add Device**
3. Select customer
4. Fill in device details
5. Click **Save**

[image_create_device]


### From Repair Order

1. When creating a repair order
2. Click **Quick Create**
3. Fill in device details
4. Device is created and selected

[image_quick_create_device]

## Device Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Customer** | Device owner | Yes |
| **Device Type** | Category (Phone, Laptop, Tablet, etc.) | Yes |
| **Brand** | Manufacturer (Apple, Samsung, etc.) | No |
| **Model** | Model name/number | No |
| **Serial Number** | Device serial | No |
| **IMEI** | Device IMEI | No |
| **Condition** | Device condition | No |
| **Accessories** | Device accessories | No |
| **Password/Pattern** | Device password/pattern | No |
| **Notes** | Additional notes | No |
| **Status** | Device status | No |

## Editing a Device

1. Find the device in the list
2. Click **Edit** or the device name
3. Modify the information
4. Click **Save**

## Device Details Page

Click a device to view its details:

[image_device_detail]

### Repair History

View all repair orders for this device:
- Order code
- Problem description
- Status
- Date
- Amount

Click an order to view details.

## Deleting a Device

1. Open device details
2. Click **Delete** button
3. Confirm deletion

> **Note:** Deleting a device does not delete associated repair orders.

---

Next: [Parts Catalog](../inventory-management/parts-catalog.md)
