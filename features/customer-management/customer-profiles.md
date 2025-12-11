# Customer Profiles

Manage customer information and their devices.

[image_customers_list]

## Viewing Customers

Navigate to **Admin > Customers** to see all customers.

### List Features

- **Search** - Find by name, phone, or email
- **Filter** - Filter by status
- **Sort** - Sort by name, date, orders count
- **Bulk Actions** - Delete multiple customers

## Creating a Customer

1. Navigate to **Admin > Customers**
2. Click **Create Customer**
3. Fill in customer details
4. Click **Save**


### Customer Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Name** | Customer's full name | Yes |
| **Email** | Email address | No |
| **Phone** | Phone number | No |
| **Address** | Street address | No |
| **City** | City | No |
| **Notes** | Internal notes | No |

> **Tip:** At least one contact method (email or phone) is recommended.

## Editing a Customer

1. Find the customer in the list
2. Click **Edit** or the customer name
3. Modify the information
4. Click **Save**

## Customer Details Page

Click a customer name to view their profile:

[image_customer_detail]

### Overview Tab

- Customer information
- Contact details
- Total orders count
- Total spent

### Devices Tab

View all devices registered to this customer:
- Device name/model
- Serial number
- Last repair date


### Orders Tab

View all repair orders for this customer:
- Order code
- Device
- Status
- Date
- Amount

Click an order to view details.

## Deleting a Customer

1. Open customer profile
2. Click **Delete** button
3. Confirm deletion

> **Warning:** Deleting a customer will not remove their devices. Repair order history is preserved.

## Quick Customer Creation

When creating a repair order, you can create a new customer inline:
1. In the Customer field, click **Create New**
2. Enter customer details
3. Customer is created and selected

---

Next: [Devices](../device-management/device-catalog.md)
