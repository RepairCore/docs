# Architecture Overview

Understanding RepairCore's architecture and design patterns.

## System Architecture

### High-Level Architecture

RepairCore follows a modern MVC (Model-View-Controller) architecture with additional layers for better separation of concerns.

```
┌─────────────────────────────────────────┐
│          Presentation Layer             │
│  (Livewire Components, Blade Views)     │
└─────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────┐
│          Application Layer              │
│     (Controllers, Middleware)           │
└─────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────┐
│          Business Logic Layer           │
│      (Services, Helpers, Traits)        │
└─────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────┐
│          Data Access Layer              │
│      (Models, Repositories)             │
└─────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────┐
│          Database Layer                 │
│      (MySQL/PostgreSQL)                 │
└─────────────────────────────────────────┘
```

## Design Patterns

### Repository Pattern

Abstraction layer for data access, providing a clean interface between business logic and data persistence.

### Service Layer Pattern

Business logic is encapsulated in service classes, keeping controllers thin and focused on HTTP concerns.

### Base Model Pattern

Shared functionality across all models through a `BaseModel` class:
- Automatic audit trails (createdBy, updatedBy)
- Soft deletes
- Timestamps
- Common query scopes

### Trait-Based Composition

Reusable functionality through PHP traits:
- `HasSlug` - Automatic slug generation
- `HasMeta` - Flexible metadata support
- `Auditable` - Audit trail tracking

### Helper Pattern

Utility functions organized in helper classes:
- `FormHelper` - Form rendering
- `SettingHelper` - Settings access
- `CurrencyHelper` - Currency formatting

## Technology Stack

### Backend

**Laravel 12**
- Core framework
- Routing and middleware
- Eloquent ORM
- Authentication (Fortify)
- Queue system
- Task scheduling

**PHP 8.2+**
- Type safety
- Modern syntax
- Performance improvements

### Frontend

**Livewire 3.6**
- Full-page reactive components
- Server-side rendering

**Bootstrap 5.3**
- Responsive grid system
- UI components
- Utility classes

**Alpine.js**
- Lightweight JavaScript framework
- Interactive UI elements
- Form enhancements

**Vite 7**
- Fast build tool
- Hot module replacement
- Asset bundling

### Database

**MySQL 8.0+ / PostgreSQL 13+**
- Relational data storage
- ACID compliance
- Full-text search

**Eloquent ORM**
- Query builder
- Relationships
- Migrations

## Request Lifecycle

1. **HTTP Request** → Web server receives request
2. **Routing** → Laravel router matches URL to controller
3. **Middleware** → Authentication, CSRF, rate limiting
4. **Controller** → Handles request, calls services
5. **Service Layer** → Business logic execution
6. **Model/Repository** → Data access
7. **Database** → Query execution
8. **Response** → View rendering (Blade/Livewire)
9. **HTTP Response** → Sent to client

## Security Architecture

### Defense in Depth

Multiple layers of security:
- Input validation
- CSRF protection
- XSS prevention
- SQL injection prevention
- Rate limiting
- Authentication & authorization

### Authentication Flow

1. User submits credentials
2. Laravel Fortify validates
3. Session created
4. Optional 2FA verification
5. User authenticated

### Authorization

Role-based access control (RBAC):
- Users have roles
- Roles have permissions
- Controllers check permissions

## Performance Architecture

### Optimization Strategies

**Query Optimization**
- Eager loading to prevent N+1 queries
- Database indexing
- Query caching

**Asset Optimization**
- Minified CSS/JS
- Asset bundling
- Lazy loading

**Caching Strategy**
- Application cache
- Query result cache
- View cache

## Scalability Considerations

### Horizontal Scaling

- Stateless application design
- Session storage in database/Redis
- Queue workers on separate servers

### Vertical Scaling

- Database optimization
- PHP-FPM tuning
- Caching layers

---

Next: [Project Structure](project-structure.md)
