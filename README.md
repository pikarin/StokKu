# Stokku — Inventory Management (Laravel 12 + Filament)

A web-based inventory management application designed to help retail businesses and warehouses manage inventory efficiently, in real time, and in an integrated way.


## Project Overview

Stokku is a Laravel 12 application that leverages FilamentPHP to provide a modern, responsive admin panel for managing products, stock levels, and related catalog data. It uses SQLite for effortless local development and TailwindCSS for styling.


## Technologies Used

- PHP 8.3
- Laravel 12
- FilamentPHP (Admin Panel)
- SQLite (local development database)
- Vite + TailwindCSS
- Pest (testing)


## Prerequisites

- PHP 8.3+ with required PHP extensions for Laravel
- Composer 2.x
- Node.js 20+ and npm 10+
- SQLite (preinstalled on most systems)


## Quick Start

1) Clone and install dependencies

```bash
git clone <your-repo-url> stokku
cd stokku
composer install
npm install
```

2) Configure environment

```bash
cp .env.example .env
php artisan key:generate
```

3) Use SQLite for local development

- Ensure the SQLite database file exists:

```bash
mkdir -p database
touch database/database.sqlite
```

- In your .env, set the connection to SQLite:

```ini
DB_CONNECTION=sqlite
# The following are ignored by sqlite but keep them commented to avoid confusion
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=database/database.sqlite
# DB_USERNAME=null
# DB_PASSWORD=null
```

4) Run database migrations (and seed if you add seeders)

```bash
php artisan migrate
```

5) Build frontend assets

```bash
# During development
npm run dev

# For production builds
npm run build
```

Tip: This project also provides a convenience script that runs the PHP server, queue worker, logs, and Vite in parallel:

```bash
composer run dev
```

6) Serve the application

```bash
php artisan serve
```

Open the app in your browser at http://localhost:8000

## Running Tests

This project uses Pest.

```bash
php artisan test
```

You may also create a `.env.testing` to isolate your testing database/config.


## Troubleshooting

- Vite manifest error: If you encounter "Unable to locate file in Vite manifest", run:

```bash
npm run build
# or
npm run dev
```

- Cache/config issues: Clear Laravel caches during local setup:

```bash
php artisan optimize:clear
```

- SQLite path: Ensure `database/database.sqlite` exists and your `.env` is set to `DB_CONNECTION=sqlite`.


## Useful Scripts

- Start everything for local development: `composer run dev`
- Run the test suite: `composer test` or `php artisan test`
- Build assets: `npm run build`
