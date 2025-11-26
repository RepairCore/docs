# Localization

Understanding RepairCore's internationalization and localization features.

## Overview

RepairCore is built with full internationalization support using Laravel's translation system.

## Translation System

### Translation Functions

**In PHP/Blade**
```php
__('Manage Users')
__('Order created successfully')
__('Welcome, :name', ['name' => $user->name])
```

**In JavaScript**
```javascript
// Use Laravel's translation helper
trans('messages.welcome')
```

### Translation Keys

**Format**
- Use original English text as keys
- Not short keys or slugified strings
- Example: `__('Manage Users')` not `__('manage.users')`

**Benefits**
- More readable code
- Easier to understand context
- Default fallback is the key itself

## Language Files

### Location

Language files are stored in:
```
repair-core/resources/lang/
├── en/
│   ├── messages.php
│   ├── validation.php
│   └── auth.php
├── es/
├── fr/
└── ...
```

### Auto-Generation

Language files can be auto-generated from source code using a tool (to be implemented).

**Process:**
1. Scan codebase for `__()` calls
2. Extract translation strings
3. Generate language files
4. Translators fill in translations

## Adding New Languages

### 1. Create Language Directory

```bash
mkdir resources/lang/es
```

### 2. Copy English Files

```bash
cp -r resources/lang/en/* resources/lang/es/
```

### 3. Translate Strings

Edit the files in `resources/lang/es/` and translate the strings.

### 4. Configure Available Languages

Update settings in admin panel:
- Settings > General > Languages

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

### Per User

Users can select their preferred language in their profile settings.

## Translation in Views

### Blade Templates

```blade
<h1>{{ __('Welcome') }}</h1>
<p>{{ __('Hello, :name', ['name' => $user->name]) }}</p>
```

### Pluralization

```blade
{{ trans_choice('messages.apples', 10) }}
```

In language file:
```php
'apples' => '{0} There are none|{1} There is one|[2,*] There are :count',
```

## Translation in JavaScript

### Passing Translations

In Blade:
```blade
<script>
    window.translations = {
        'welcome': '{{ __('Welcome') }}',
        'goodbye': '{{ __('Goodbye') }}'
    };
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
    session()->flash('message', __('Order saved successfully'));
}
```

### In Component View

```blade
<div>
    <h2>{{ __('Edit Order') }}</h2>
    <button>{{ __('Save') }}</button>
</div>
```

## Translation in Notifications

### Email Templates

Email templates support translations:

```blade
{{ __('Your order :code is ready', ['code' => $order->code]) }}
```

### Notification Classes

```php
public function toMail($notifiable)
{
    return (new MailMessage)
        ->subject(__('Order Status Update'))
        ->line(__('Your order has been updated.'))
        ->action(__('View Order'), $url);
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
echo __('Welcome to RepairCore');
```

### 2. Use Original Text as Keys

❌ Bad:
```php
__('welcome.message')
```

✅ Good:
```php
__('Welcome to RepairCore')
```

### 3. Provide Context with Parameters

```php
__('Order :code created by :user', [
    'code' => $order->code,
    'user' => $user->name
])
```

### 4. Keep Translations Consistent

Use the same translation for the same concept across the application.

### 5. Test All Languages

Ensure all translations are complete and make sense in context.

## Language Switching

### User Preference

Users can select their language in:
- Profile Settings > Language

### URL-Based

Optionally support language in URL:
```
/en/orders
/es/orders
```

### Session-Based

Store language preference in session:
```php
session(['locale' => 'es']);
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

### 3. RTL Styles

Include RTL-specific styles when needed.

## Translation Tools

### Recommended Tools

- **POEditor** - Online translation management
- **Lokalise** - Translation platform
- **Laravel Translation Manager** - Package for managing translations

### Custom Tool

RepairCore will include a custom tool to:
- Extract translation strings from code
- Generate language files
- Track missing translations
- Export/import translations

---

Next: [Features Overview](../features/repair-management/repair-orders.md)
