# System Requirements

## Minimum Requirements

### Server Requirements

**PHP Version**
- PHP 8.2 or higher

**PHP Extensions**
- BCMath
- Ctype
- cURL
- DOM
- Fileinfo
- JSON
- Mbstring
- OpenSSL
- PCRE
- PDO
- Tokenizer
- XML

### Database

**Supported Databases**
- MySQL 8.0 or higher
- PostgreSQL 13 or higher

### Web Server

**Supported Web Servers**
- Apache 2.4+ with mod_rewrite
- Nginx 1.18+

### Node.js & NPM

- Node.js 22.x (managed via Volta)
- NPM 10.x or higher

### Composer

- Composer 2.x

## Recommended Requirements

### For Production

**Server Specifications Minimum**
- 1+ CPU cores
- 2GB+ RAM
- 20GB+ disk space
- SSD storage recommended

**Server Specifications Recommended**
- 2+ CPU cores
- 4GB+ RAM
- 20GB+ disk space
- SSD storage recommended

**PHP Configuration**
- `memory_limit`: 256M or higher
- `max_execution_time`: 300
- `upload_max_filesize`: 20M
- `post_max_size`: 20M

### For Development

**Local Development**
- 1+ CPU core
- 2GB+ RAM
- 10GB+ disk space

## Browser Support

### Admin Panel
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### Customer Portal
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Additional Tools

### Development Tools
- Git 2.x
- Code editor (VS Code, PHPStorm, etc.)
- Terminal/Command line access

### Optional
- Redis (for caching and queues)
- Supervisor (for queue workers)
- SSL certificate (for HTTPS)

---

Next: [Installation](installation.md)
