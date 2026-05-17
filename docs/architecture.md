# Arquitectura Propuesta

## Capas
- HTTP (Controllers, Requests, Resources)
- Application (Services / Actions)
- Domain (Models y reglas)
- Infrastructure (Persistence, Files, Logs)

## Tablas
- users
- roles / permissions (spatie)
- vehicles
- garage_movements
- inspections
- inspection_items
- destinations
- incidents
- vehicle_photos
- activity_logs

## Reglas clave
- Solo `admin` gestiona usuarios.
- `operador` registra entradas/salidas según permisos.
- `supervisor` consulta y audita.
- Todas las acciones usan policy por recurso.
- IDs nunca se exponen sin autorización.

## Seguridad
- Validación por Form Request.
- Autorización con policies y permisos.
- Carga de archivos con validación MIME y tamaño.
- Rate limit por token y por IP.
- Logs de actividad por evento.
