# CarBack API (Laravel)

API REST segura para control de autos de garage.

## Stack
- PHP 8.3+
- Laravel 12
- Laravel Sanctum
- Laravel Socialite (Google OAuth)
- Spatie Laravel Permission (roles/permisos)

## Instalación
```bash
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan db:seed
php artisan storage:link
php artisan test
```

## Roles
- admin
- operador
- supervisor

## Módulos
- Usuarios (solo admin crea usuarios internos)
- Vehículos
- Movimientos de garage (entrada/salida)
- Inspecciones y checklist
- Fotos/evidencias
- Viajes/destinos
- Incidentes/fallas
- Auditoría de actividad

## Seguridad
- Auth con Sanctum
- OAuth Google para login
- Policies por recurso (evita IDOR)
- Form Requests estrictos
- Rate limiting en rutas API
- CORS restringido por `CORS_ALLOWED_ORIGINS`
- Validación de archivos: MIME y tamaño
- Storage seguro para evidencias

## Endpoints base
- `POST /api/v1/auth/google/redirect`
- `POST /api/v1/auth/google/callback`
- `POST /api/v1/auth/logout`
- `GET /api/v1/me`

- `GET /api/v1/vehicles`
- `POST /api/v1/vehicles`
- `GET /api/v1/vehicles/{vehicle}`
- `PUT /api/v1/vehicles/{vehicle}`
- `DELETE /api/v1/vehicles/{vehicle}`

- `POST /api/v1/garage-movements/entry`
- `POST /api/v1/garage-movements/{movement}/exit`
- `GET /api/v1/garage-movements`

## Notas
- Este commit deja una base arquitectónica y archivos de arranque para levantar el proyecto como API-first.
- Ver `docs/architecture.md` para diseño de tablas y reglas de autorización.
