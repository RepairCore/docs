# Service Catalog

Manage the repair services you offer to customers.

[image_services_list]

## Overview

The service catalog stores all repair services you provide. Each service has pricing and can be added to repair orders.

## Viewing Services

Navigate to **Admin > Services** to see all services.

### List Features

- **Search** - Find by name or description
- **Filter** - Filter by category, status
- **Sort** - Sort by name, price
- **Bulk Actions** - Update status or delete multiple services

## Creating a Service

1. Navigate to **Admin > Services**
2. Fill in service details
3. Click **Save**

### Service Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Name** | Service name | Yes |
| **Code** | Service code | No |
| **Category** | Service category | No |
| **Price** | Service price | Yes |
| **Tax Class** | Tax applied to this service | No |
| **Duration** | Estimated time (minutes) | No |
| **Description** | Service description | No |
| **Status** | Active or Inactive | Yes |

## Pricing

### Base Price

The standard price for this service. Can be adjusted when adding to an order.

### Tax Class

Select the tax class to apply. If not set, the default tax class for services is used (configured in Settings > Tax).

## Editing a Service

1. Find the service in the list
2. Click **Edit** or the service name
3. Modify the information
4. Click **Save**

## Deleting a Service

1. Open service details
2. Click **Delete** button
3. Confirm deletion

> **Note:** Deleting a service does not affect existing repair orders that used it.

## Using Services in Orders

When creating or editing a repair order:

1. Go to **Parts & Services** tab
2. Click **Add Service**
3. Search for the service
4. Service is added to the order

[image_add_service_to_order]

---

Next: [Service Categories](service-categories.md)
