# What's New

This page highlights the latest features and improvements in RepairCore.

## Latest Updates

### Version 1.0.0 (Current)

**Release Date:** December 2024

#### Core Features
- **Repair Order Management** - Complete lifecycle tracking with Livewire-based form
  - 11 Livewire sections for modular editing
  - Customer & device selection
  - Parts & services with automatic pricing
  - Progress logging with timeline
  - Warranty management
- **Multi-Tax Class System** - Flexible tax configuration
  - Multiple tax classes (VAT, Service Tax, etc.)
  - Tax-inclusive and tax-exclusive pricing
  - Per-item or subtotal calculation
  - Configurable rounding modes
- **Stock Management** - Comprehensive inventory control
  - Automatic stock deduction for repair orders
  - Backorder support
  - Stock movement logging
  - Low stock alerts
- **Notification System** - Keep users informed
  - Customizable email templates
  - In-app notifications
  - User notification preferences
- **Language Management** - Built-in translation system
  - Single JSON file approach
  - Admin panel translation editor
  - Multi-language support

#### Technical Stack
- **Backend:** Laravel 12, PHP 8.2+
- **Frontend:** Livewire 3.6, Bootstrap 5.3, Alpine.js
- **Database:** MySQL/PostgreSQL
- **Build Tool:** Vite 7

#### Key Improvements
- Livewire components use `App\Http\Livewire\` namespace
- Translation keys use slugified format (snake_case)
- Centralized breadcrumbs system
- FormHelper for consistent form rendering
- Trait-based stock management (HasStockManagement, ManagesPartStock)

---

## Recent Changes

### Documentation Updates (December 2024)
- Updated localization docs for single JSON file approach
- Complete tax management documentation
- Stock management with traits documentation
- Livewire components with correct namespace
- Settings pages documentation
- Users & roles with permissions

---

## Coming Soon

- Customer portal improvements
- API documentation
- Advanced reporting features
