# Sprint 4 Planning — ERP Django
## Semanas W13–W15 · Espiral 5: E-commerce y Pagos

**Sprint Goal:**
Al finalizar el Sprint 4, el ERP tendrá catálogo filtrable,
carrito de compras y pago completo con Stripe sandbox,
actualizando automáticamente el estado del pedido.

## HUs seleccionadas

## Sprint Backlog — actualización W13

| Tarea | Estado |
|---|---|
| Catálogo + carrito + context processor | ✅ W13 |
| pip install stripe | ✅ W14 |
| STRIPE_* en settings.py y .env | ✅ W14 |
| checkout_utils.py (calcular_totales, obtener_cliente) | ✅ W14 |
| CheckoutView (GET/POST) con PaymentIntent | ✅ W14 |
| Template checkout.html con Stripe.js Card Element | ✅ W14 |
| pago_exitoso: vaciar carrito + template | ✅ W14 |
| pago_error: template con causas y reintento | ✅ W14 |
| Tests con unittest.mock.patch | ✅ W14 |
| Webhooks + actualizar estado pedido | ⏳ W15 |
| Descontar stock al confirmar pago | ⏳ W15 |

**Total Sprint 4:** 26 puntos

## DoD — Sprint 4
- GET /catalogo/ → 200 sin autenticación con lista de productos
- Filtrar por categoría → solo productos de esa categoría
- Agregar producto al carrito → contador en navbar se incrementa
- Tarjeta de prueba Stripe 4242... → pedido cambia a "pagado"
- Webhook verifica firma → stock se descuenta
- python manage.py test → ≥ 131 tests OK