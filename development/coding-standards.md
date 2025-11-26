# Coding Standards

Code style and standards for RepairCore.

## Overview

RepairCore follows Laravel conventions and PSR-12 coding standards.

## PHP Standards

### PSR-12
- Follow PSR-12 coding style
- Use Laravel Pint for formatting: `./vendor/bin/pint`

### Laravel Conventions
- Model names: Singular, PascalCase (e.g., `RepairOrder`)
- Controller names: Plural, PascalCase + Controller (e.g., `RepairOrdersController`)
- Table names: Plural, snake_case (e.g., `repair_orders`)

## Code Style Rules

### Models
- All tables must have: timestamps, soft delete, createdBy, updatedBy
- No mass assignment - use manual attribute setting
- Use `fillByAttrs` from BaseModel when needed
- Status column: VARCHAR with "draft" as default

### Controllers
- Check permissions in all methods
- Validate using Laravel validator
- Never use mass assign
- Only use `store()` method for create/update

### Routes
- Never use `Route::resource`
- Define routes manually
- Only use `store()` with POST method

### Forms
- Reuse `\App\Helpers\FormHelper` for form fields
- Use `FormHelper::select2` for remote data selection

### Localization
- All strings must be translatable: `__('Text')`
- Use original text as keys, not short keys
- No need to create language files manually

## Frontend Standards

### Admin
- CSS/JS in `public_html/themes/admin`
- Views in `repair-core/resources/views/admin`
- Use Alpine.js for complex UI
- Edit and Create share same form

### Frontend
- CSS/JS in `public_html/themes/frontend`
- Views in `repair-core/resources/views/frontend`
- Use Livewire full-page components

### Livewire
- Namespace: `App\Http\Livewire\`
- Directory: `app/Http/Livewire/`

## Documentation

- All code must be in English
- Comments for complex logic
- PHPDoc blocks for classes and methods

---

Next: [Backend Development](backend/models.md)
