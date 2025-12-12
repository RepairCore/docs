# Part Categories

Organize your parts into categories for easier management.

[image_part_categories_list]

## Overview

Part categories help organize your inventory. Categories can be nested (parent-child) for hierarchical organization.

## Viewing Categories

Navigate to **Admin > Parts > Part Categories** to see all categories.

## Creating a Category

1. Navigate to **Admin > Parts > Part Categories**
2. Fill in the form on the left side
3. Click **Save**

### Category Fields

| Field | Description | Required |
|-------|-------------|----------|
| **Name** | Category name | Yes |
| **Slug** | Category slug | No |
| **Parent** | Parent category (for nesting) | No |
| **Description** | Category description | No |
| **Status** | Active or Inactive | Yes |

## Nested Categories

Create a hierarchy by setting a parent category:

```
Screens
├── Phone Screens
│   ├── iPhone Screens
│   └── Samsung Screens
└── Tablet Screens
```

### Creating Nested Categories

1. Create the parent category first
2. When creating child category, select the parent
3. Child appears indented under parent

## Editing a Category

1. Find the category in the list
2. Click **Edit** button
3. Modify the information
4. Click **Save**

## Deleting a Category

1. Find the category in the list
2. Click **Delete** button
3. Confirm deletion

> **Warning:** Deleting a parent category will also delete all child categories. Parts in deleted categories will become uncategorized.

## Using Categories

### Filtering Parts

On the Parts list page, use the category filter to show only parts in a specific category.

### Assigning Parts to Categories

When creating or editing a part, select the category from the dropdown.

---

Next: [Part Brands](part-brands.md)
