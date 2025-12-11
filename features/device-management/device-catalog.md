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
2. Click **Create Device**
3. Select customer
4. Fill in device details
5. Click **Save**

[image_create_device]

### From Customer Profile

1. Open customer profile
2. Go to **Devices** tab
3. Click **Add Device**
4. Fill in device details
5. Click **Save**

### From Repair Order

1. When creating a repair order
2. After selecting customer, click **Add New Device**
3. Fill in device details
4. Device is created and selected

## Device Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Customer** | Device owner | Yes |
| **Device Type** | Category (Phone, Laptop, Tablet, etc.) | Yes |
| **Brand** | Manufacturer (Apple, Samsung, etc.) | No |
| **Model** | Model name/number | No |
| **Serial Number** | Device serial or IMEI | No |
| **Color** | Device color | No |
| **Purchase Date** | When customer bought device | No |
| **Notes** | Additional notes | No |

[image_device_form]

## Device Types

Common device types:
- **Phone** - Mobile phones
- **Tablet** - Tablets and iPads
- **Laptop** - Laptops and notebooks
- **Desktop** - Desktop computers
- **Watch** - Smartwatches
- **Console** - Gaming consoles
- **Other** - Other devices

## Editing a Device

1. Find the device in the list
2. Click **Edit** or the device name
3. Modify the information
4. Click **Save**

## Device Details Page

Click a device to view its details:

[image_device_detail]

### Information

- Device type, brand, model
- Serial number
- Customer information
- Purchase date

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
