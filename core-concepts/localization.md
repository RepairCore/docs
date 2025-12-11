# Localization

Understanding RepairCore's internationalization and localization features.

## Overview

RepairCore is built with full internationalization support using Laravel's translation system with a **single JSON file** approach.

## Translation System

### Translation Functions

**In PHP/Blade**
```php
__('manage_users')
__('order_created_successfully')
__('welcome_name', ['name' => $user->name])
```

**In JavaScript**
```javascript
// Use Laravel's translation helper
window.translations.manage_users
```

### Translation Keys

**Format**
- Use **slugified keys** (snake_case)
- All keys in a single JSON file
- No module prefixes like `post.`, `user.`
- Descriptive and complete slugs

**Examples:**
```php
// CORRECT
__('manage_posts')
__('post_created_successfully')
__('delete_selected')
__('published_at')

// WRONG - Don't use these formats
__('Manage Posts')        // Not slugified
__('post.manage')         // Has prefix
__('manage-posts')        // Uses hyphens
```

**Key Naming Patterns:**
- **List/Manage**: `manage_[resource]` → "Manage Posts"
- **CRUD Actions**: `[action]_[resource]` → "create_post", "edit_post"
- **Status**: `status_[status]` → "status_draft", "status_active"
- **Messages**: `[resource]_[action]_[result]` → "post_created_successfully"
- **Form Fields**: `[resource]_[field]` → "post_title", "post_slug"
- **Placeholders**: `[action]_[resource]_[field]` → "enter_post_title"
- **Dates/Times**: Use underscores → "published_at", "created_at"

## Language Files

### Location

All translations are stored in a **single JSON file**:
```
repair-core/resources/lang/
├── en.json              # English translations (primary)
├── vi.json              # Vietnamese translations
└── ...
```

**Important:** Do NOT use PHP language files (`.php`). All translations must be in JSON format.

### JSON File Structure

```json
{
  "manage_posts": "Manage Posts",
  "create_post": "Create Post",
  "post_created_successfully": "Post created successfully",
  "delete_selected": "Delete Selected",
  "status_draft": "Draft",
  "status_active": "Active"
}
```

### Language Management

RepairCore includes a built-in Language Management system in the admin panel:
- **Admin > Languages** - Manage available languages
- Create, edit, delete languages
- Edit translations directly in the admin panel
- Build/export language files

## Adding New Languages

### Via Admin Panel (Recommended)

1. Navigate to **Admin > Languages**
2. Click **Add New Language**
3. Fill in language details (name, code, native name)
4. Save and start translating

### Manual Method

1. Create a new JSON file: `resources/lang/{locale}.json`
2. Copy content from `en.json`
3. Translate all values
4. Register the language in admin panel

## Setting Default Language

### In Configuration

Edit `config/app.php`:
```php
'locale' => 'en',
'fallback_locale' => 'en',
```

### In Environment

Edit `.env`:
```env
APP_LOCALE=en
APP_FALLBACK_LOCALE=en
```

### Via Admin Panel

Navigate to **Admin > Languages** and click "Set as Default" for the desired language.

## Translation in Views

### Blade Templates

```blade
<h1>{{ __('welcome') }}</h1>
<p>{{ __('hello_name', ['name' => $user->name]) }}</p>
```

### Pluralization

```blade
{{ trans_choice('apples_count', 10) }}
```

In JSON file:
```json
{
  "apples_count": "{0} There are none|{1} There is one|[2,*] There are :count"
}
```

## Translation in JavaScript

### Passing Translations

In Blade layout:
```blade
<script>
    window.translations = @json(app('translator')->getLoader()->load(app()->getLocale(), '*', '*'));
</script>
```

In JavaScript:
```javascript
console.log(window.translations.welcome);
```

## Translation in Livewire

### In Component Class

```php
public function save()
{
    session()->flash('message', __('order_saved_successfully'));
}
```

### In Component View

```blade
<div>
    <h2>{{ __('edit_order') }}</h2>
    <button>{{ __('save') }}</button>
</div>
```

## Translation in Notifications

### Email Templates

Email templates support translations:

```blade
{{ __('your_order_is_ready', ['code' => $order->code]) }}
```

### Notification Classes

```php
public function toMail($notifiable)
{
    return (new MailMessage)
        ->subject(__('order_status_update'))
        ->line(__('your_order_has_been_updated'))
        ->action(__('view_order'), $url);
}
```

## Best Practices

### 1. Always Use Translation Functions

❌ Bad:
```php
echo "Welcome to RepairCore";
```

✅ Good:
```php
echo __('welcome_to_repaircore');
```

### 2. Use Slugified Keys

❌ Bad:
```php
__('Welcome to RepairCore')  // Not slugified
__('welcome.message')        // Has dot prefix
```

✅ Good:
```php
__('welcome_to_repaircore')
```

### 3. Provide Context with Parameters

```php
__('order_created_by_user', [
    'code' => $order->code,
    'user' => $user->name
])
```

### 4. Keep Translations Consistent

Use the same translation key for the same concept across the application.

### 5. Add New Keys to JSON File

When adding new translatable strings, add them to `en.json` immediately.

## Language Switching

### User Preference

Users can select their language in:
- Profile Settings > Language

### Session-Based

Store language preference in session:
```php
session(['locale' => 'vi']);
app()->setLocale(session('locale'));
```

## RTL Support

For right-to-left languages (Arabic, Hebrew):

### 1. Detect RTL Language

```php
$rtl = in_array(app()->getLocale(), ['ar', 'he']);
```

### 2. Apply RTL Class

```blade
<html dir="{{ $rtl ? 'rtl' : 'ltr' }}">
```

## Built-in Language Management

RepairCore includes a comprehensive Language Management system:

### Features
- **Create/Edit Languages** - Add new languages with name, code, native name
- **Translation Editor** - Edit translations directly in admin panel
- **Build System** - Generate optimized language files
- **Import/Export** - Load translations from JSON files
- **Bulk Actions** - Delete multiple languages at once
- **Set Default** - Configure default application language

### Admin Routes
- `admin/languages` - List all languages
- `admin/languages/{language}/edit` - Edit language translations
- `admin/languages/{language}/build` - Build language file
- `admin/languages/{language}/set-default` - Set as default

---

Next: [Features Overview](../features/repair-management/repair-orders.md)
