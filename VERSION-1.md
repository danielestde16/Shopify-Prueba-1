# KINU — Versión 1 de la página

> Resumen de cómo quedó la **primera versión** de la tienda KINU.
> Fecha: 5 de junio de 2026.

---

## 1. Qué tiene la página (secciones)

### Página de inicio (home), en orden:
1. **Hero** — video de galaxia de fondo, gancho "Apaga la cabeza. Vuelve a dormir.", CTA "Quiero dormir mejor".
2. **El problema** — "¿con cuántas te identificas?".
3. **La revelación** — "No tienes un problema de sueño, tienes un problema de recuperación".
4. **Valor** — propuesta de valor (scroll-swap estilo Collider).
5. **El ritual** — "Dos cucharadas, en tu vaso de la noche, 30 min antes".
6. **Ingrediente** — citrato de magnesio + estudios (claims suavizados y atribuidos).
7. **Reseñas** — 6 testimonios (⚠️ aún de ejemplo, cambiar por reales).
8. **Bundles** — packs 1/2/3 tarros con ahorro + contador "Envío gratis hoy".
9. **Qué esperar + Garantía** — tarjetas de colores interactivas + "30 noches de garantía".
10. **FAQ** — preguntas que rompen objeciones.
11. **Footer**.
12. **Sticky cart** (móvil) + **Popup 14% OFF** (captura de email a Klaviyo).

### Página de producto:
- **Constructor de packs** (galería + selector 1/2/3 tarros, precio "antes" tachado + ahorro + envío gratis).
- **Contador** "Envío gratis hoy" (dorado).
- **Pista de scroll** "Por qué elegir KINU".
- **Comparativa "Nosotros vs Otros"** (KINU vs Melatonina vs Otros magnesios, interactiva).

---

## 2. Carrito
- Drawer propio de KINU (`KinuCart`) con ahorro y envío gratis.
- Logos de pago normalizados (Visa, Mastercard, PSE, Bancolombia, Bre-B), clicables → producto.

---

## 3. Optimizaciones de velocidad aplicadas
- Imágenes redimensionadas por URL del CDN (de ~12 MB a <1 MB).
- Quitados scripts/CSS de Dawn sin usar: cart-notification, búsqueda predictiva, search-form, animations.
- Solo 1 familia de fuente (Plus Jakarta Sans).
- Preconnect al CDN de Shopify, `fetchpriority` en imagen principal.
- Video del hero **diferido** (carga tras el primer pintado) + imagen LCP precargada.
- CSS de las 12 secciones below-fold cargado **async** (no bloquea el render).
- Animaciones de estrellas eliminadas.

---

## 4. Píxeles / Ads (instalado)
- Snippet `kinu-pixels.liquid` (Meta + TikTok + GA4), IDs en *Configuración del tema → "KINU – Píxeles / Ads"*.
- Eventos: **PageView, ViewContent, AddToCart, InitiateCheckout, Lead**.
- ⚠️ **Purchase** requiere conectar los canales nativos de Meta y TikTok (Conversions/Events API).
- ⚠️ El píxel solo aparece cuando hay un ID pegado **y** el tema está publicado.

---

## 5. Pendientes para la Versión 2 (decisiones del dueño)
- [ ] **Pegar los IDs de los píxeles** (Meta + TikTok) y conectar los canales nativos para Purchase.
- [ ] **Reseñas reales** (cambiar las de ejemplo por clientes reales o app tipo Judge.me).
- [ ] **Revisar legalmente los claims de salud** (aunque ya están suavizados).
- [ ] **Confirmar la garantía** "30 noches o devolución" (poder cumplirla).
- [ ] **Comprimir el video del hero** y subir un "póster" (fotograma).
- [ ] **Automatizar Klaviyo** (flujo de bienvenida + envío del cupón 14%).
- [ ] (Opcional) Suscripción mensual (modelo Athletic Greens).

---

## 5. Cómo trabajar este proyecto (recordatorio)
- **Desarrollo en vivo:** `shopify theme dev` (preview en `localhost:9292`).
- **Guardar código:** `git commit` (local) + `git push` (GitHub).
- **Subir a la tienda:** `shopify theme push --unpublished` (tema de prueba) → revisar → publicar desde el admin.
- ⚠️ No desarrollar sobre el tema publicado. El editor visual de Shopify puede sobrescribir los `templates/*.json`.
