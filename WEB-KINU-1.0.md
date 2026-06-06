# WEB KINU 1.0 — Estado completo

> Documento maestro de la web KINU. Tema en Shopify: **"WEB KINU 1.0"**.
> Última actualización: 5 de junio de 2026.

---

## 1. Temas en Shopify (importante)
- **`WEB KINU 1.0`** → el tema BUENO, con todo lo de abajo. Es el que se publica.
- **`Shopify-Prueba-1/main`** → tema viejo (conectado a GitHub). Ya no se usa; ignorar o borrar.
- Regla: se **publica WEB KINU 1.0 una sola vez** y queda como el sitio en vivo. No se cambia de tema cada vez.

---

## 2. Secciones de la página
**Home:** Hero (video) → El problema → La revelación → Valor → El ritual → Ingrediente →
Reseñas → Bundles (con contador "envío gratis hoy") → Qué esperar + Garantía → FAQ → Footer.
Globales: Sticky cart (móvil) + Popup 14% OFF (Klaviyo).

**Producto:** constructor de packs (precio "antes" + ahorro + envío gratis), contador dorado,
pista de scroll, y comparativa "Nosotros vs Otros".

---

## 3. Píxeles / Ads (ya instalado)
- **Meta Pixel ID fijo:** `853778647311773`.
- **TikTok:** pendiente de pegar el ID.
- IDs editables en: *Configuración del tema → "KINU – Píxeles / Ads"*.

**Eventos que disparan:**
- Estándar: `PageView`, `ViewContent` (producto), `AddToCart`, `InitiateCheckout`, `Lead` (popup).
- Engagement: `Scroll25/50/75/90`, `ViewProblema/Ingrediente/Reviews/Pricing/Garantia/FAQ/Comparativa`,
  `ClickBuyCTA`, `Engaged30s`.
- ⚠️ **Purchase** NO se captura desde el tema → conectar el canal nativo de Meta (Apps → Facebook & Instagram) + TikTok para Conversions/Events API.

---

## 4. Velocidad (optimizado)
- Imágenes redimensionadas por CDN (de ~12 MB a <1 MB).
- Video del hero diferido + imagen LCP precargada.
- CSS de 12 secciones cargado async (no bloquea).
- Quitados scripts/CSS de Dawn sin usar; 1 sola fuente; preconnect al CDN.
- Pendiente real: comprimir el video del hero + póster.

---

## 5. Pendientes (Versión 2)
- [ ] Pegar **TikTok Pixel ID** y conectar canales nativos de Meta y TikTok (Purchase).
- [ ] **Reseñas reales** (las actuales son de ejemplo).
- [ ] Revisar legalmente los claims de salud (ya suavizados).
- [ ] Confirmar la garantía "30 noches o devolución".
- [ ] Comprimir el video del hero + póster.
- [ ] Automatizar Klaviyo (bienvenida + cupón).
- [ ] (Opcional) Suscripción mensual.

---

## 6. Flujo de trabajo (cómo editar, guardar, subir y publicar)

**Editar en vivo (preview local):**
```bash
shopify theme dev
```

**Guardar el código (respaldo en GitHub):**
```bash
git add -A
git commit -m "describe el cambio"
git push
```

**Subir cambios a la tienda (al tema WEB KINU 1.0):**
```bash
shopify theme push
```
→ elegir **"WEB KINU 1.0"** en la lista (no crear uno nuevo cada vez).

**Publicar (solo la primera vez, para dejarlo en vivo en kinu.lat):**
Admin → Online Store → Temas → **WEB KINU 1.0** → botón **"Publicar"**.

> Tras publicarlo, ya es el sitio en vivo. Para cambios futuros: edita local →
> `shopify theme push` a WEB KINU 1.0. **Siempre prueba antes con `shopify theme dev`**
> para no subir algo roto al sitio en vivo.
