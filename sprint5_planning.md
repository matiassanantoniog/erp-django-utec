# Sprint 5 Planning — ERP Django
## Semanas W16–W18 · Espiral 6: Celery e Integraciones

## Sprint 5 — Estado final W18

| HU | Estado | Pts |
|---|---|---|
| HU-E6-01 a HU-E6-06 | ✅ Completadas | 18/18 |

## Hito M6 — ALCANZADO ✅
- Tareas: ejecutadas sin bloquear la petición
- Scheduler: CELERY_BEAT_SCHEDULE activo (correr_programadas / Beat)
- Correo: enviar_confirmacion_pedido → enviado post-pago
- Alerta: verificar_stock_bajo → correo al admin
- Reporte: crontab(8,0) → 8:00 AM diario (día anterior)
- Tests: Ran 172 tests → OK
- Fecha: ___/___/_____


**Sprint Goal:**
Al finalizar el Sprint 5, el ERP ejecutará tareas pesadas de forma
asíncrona con Celery: correos de confirmación, alertas de
stock bajo y reporte diario de ventas.

## Sprint Backlog — actualización W17

| Tarea | Estado |
|---|---|
| pip install celery redis flower | ✅ W16 |
| core/celery.py + tareas placeholder | ✅ W16 |
| pip install django-anymail | ✅ W17 |
| EMAIL_BACKEND por variable de entorno (consola / anymail / SMTP) | ✅ W17 |
| correo_enviado en Pedido + migración 0004 | ✅ W17 |
| Template confirmacion_pedido.html + .txt (correo de pago) | ✅ W17 |
| Template alerta_stock.html + .txt (correo de stock bajo) | ✅ W17 |
| enviar_confirmacion_pedido: correo real + idempotencia atómica | ✅ W17 |
| verificar_stock_bajo: alerta al admin | ✅ W17 |
| Comando probar_correos | ✅ W17 |
| 9 tests con mail.outbox | ✅ W17 |
| Celery Beat + tareas programadas | ⏳ W18 |
**Total Sprint 5:** 18 puntos

## DoD — Sprint 5
- celery -A core worker -P solo → procesa tareas sin error
- Pago confirmado → tarea de correo en la cola (no espera)
- Correo de confirmación generado una sola vez por pedido (W17)
- Alerta de stock enviada cuando stock < umbral (W17)
- Reporte diario ejecutado a las 8:00 AM (W18)
- python manage.py test → ≥ 155 tests OK al cierre de W16