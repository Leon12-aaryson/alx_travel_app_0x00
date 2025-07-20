# ALX Travel App - Django Project Configuration

This directory contains the main Django project configuration for the ALX Travel App.

## Project Overview

The ALX Travel App is a Django-based web application for managing travel property listings, bookings, and reviews. This project demonstrates Django best practices including database modeling, API serialization, and data seeding.

## Project Structure

```text
alx_travel_app/
├── __init__.py          # Python package initialization
├── settings.py          # Django project settings
├── urls.py             # Main URL configuration
├── wsgi.py             # WSGI application entry point
├── asgi.py             # ASGI application entry point
└── README.md           # This documentation file
```

## Configuration Files

### settings.py

Main Django settings file containing:

- **Database Configuration**: SQLite3 database setup
- **Installed Apps**: Django apps and third-party packages
- **Middleware**: Security and session middleware
- **Templates**: Template engine configuration
- **Static Files**: Static file serving configuration
- **Security Settings**: Secret key and debug settings

**Key Settings:**

- `DEBUG = True` (development mode)
- `DATABASES`: SQLite3 configuration
- `INSTALLED_APPS`: Includes `listings` and `rest_framework`
- `DEFAULT_AUTO_FIELD = 'django.db.models.BigAutoField'`

### urls.py

Main URL configuration file:

- Root URL patterns
- Admin interface URLs
- API endpoint routing (when implemented)

### wsgi.py

WSGI (Web Server Gateway Interface) application entry point:

- Used for production deployment
- Configures Django application for WSGI servers

### asgi.py

ASGI (Asynchronous Server Gateway Interface) application entry point:

- Used for async-capable servers
- Supports WebSocket connections

## Dependencies

### Core Django

- **Django 5.2.4**: Web framework
- **asgiref 3.9.1**: ASGI utilities
- **sqlparse 0.5.3**: SQL parsing utilities

### Third-party Packages

- **djangorestframework 3.16.0**: REST API framework

## Development Setup

### Prerequisites
- Python 3.8+
- pip package manager

### Installation Steps

1. Create virtual environment: `python3 -m venv venv`
2. Activate virtual environment: `source venv/bin/activate`
3. Install dependencies: `pip install -r requirements.txt`
4. Run migrations: `python manage.py migrate`
5. Seed database: `python manage.py seed`
6. Start development server: `python manage.py runserver`

## API Configuration

The project is configured to use Django REST Framework for API development:

```python
INSTALLED_APPS = [
    # ... Django apps
    'rest_framework',
    'listings',
]
```

### API Features
- **Serializers**: JSON data serialization/deserialization
- **ViewSets**: RESTful API views
- **Authentication**: User authentication system
- **Permissions**: Access control mechanisms

## Database Configuration

### Current Setup
- **Database Engine**: SQLite3
- **Database File**: `db.sqlite3` (in project root)
- **Migrations**: Applied for all apps

### Models Available
- **User**: Django's built-in user model
- **Listing**: Property listings with full details
- **Booking**: Property booking system
- **Review**: User review and rating system

## Security Considerations

### Development Settings
- `DEBUG = True` (should be False in production)
- `SECRET_KEY` (should be kept secret in production)
- `ALLOWED_HOSTS = []` (configure for production)

### Production Recommendations
1. Set `DEBUG = False`
2. Use environment variables for `SECRET_KEY`
3. Configure `ALLOWED_HOSTS`
4. Use HTTPS in production
5. Set up proper database (PostgreSQL recommended)

## Deployment

### WSGI Deployment
For traditional WSGI servers (Gunicorn, uWSGI):
```bash
gunicorn alx_travel_app.wsgi:application
```

### ASGI Deployment
For async-capable servers (Daphne, Uvicorn):
```bash
uvicorn alx_travel_app.asgi:application
```

## Testing

### Running Tests
```bash
python manage.py test
```

### System Check
```bash
python manage.py check
```

## Management Commands

### Available Commands
- `python manage.py migrate` - Apply database migrations
- `python manage.py seed` - Populate database with sample data
- `python manage.py createsuperuser` - Create admin user
- `python manage.py runserver` - Start development server

### Custom Commands
- `seed` - Database seeding command in `listings` app

## Troubleshooting

### Common Issues
1. **Database errors**: Run `python manage.py migrate`
2. **Import errors**: Check virtual environment activation
3. **Permission errors**: Check file permissions
4. **Port conflicts**: Use different port with `--port` flag

### Debug Mode
When `DEBUG = True`:
- Detailed error pages
- SQL query logging
- Static file serving

## Contributing

1. Follow Django coding style guidelines
2. Add tests for new features
3. Update documentation
4. Use meaningful commit messages

## License

This project is part of the ALX Software Engineering curriculum.

## Author

Created as part of ALX Software Engineering program.
