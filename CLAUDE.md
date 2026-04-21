# Orion AI Consulting — Presentación Ejecutiva

## Descripción del proyecto
Presentación ejecutiva de 13 slides para Orion AI Consulting, una agencia de contenido con IA para marcas en LATAM. El objetivo es demostrar ROI y beneficios del servicio.

## Archivos principales
- `Orion AI Consulting.html` — Presentación completa (single-file HTML)
- `deck-stage.js` — Componente web para navegación y scaling de slides
- `uploads/Orion Consulting AI Logo.png` — Logo oficial
- `uploads/UGC Chica-influencer, infoproducto.mp4` — Video demo UGC / infoproducto
- `uploads/Avatar económico hablando a camara.mp4` — Video demo avatar económico

## Estructura de slides
1. Portada — Hero title + 3 KPIs animados
2. El Problema — 4 pain cards
3. Datos de Mercado — Dashboard 6 métricas
4. La Solución — 3 pilares
5. Réplica de Voz — Tabla FBI + onda de audio
6. Influencers IA — Tabla FBI + referencia Aitana López
7. **Demos en Vivo** — 3 placeholders de video reproducibles
8. Automatización de Contenido — Tabla FBI + capacidad
9. Conversión y Ventas — Tabla FBI + mockup DM
10. ROI Antes vs Después — Tabla comparativa
11. Capacidad Operativa — Dashboard barras de progreso
12. Ecosistema Integrado — Diagrama SVG circular
13. Cierre — Headline + 3 cards + logo

## Navegación
- Teclado: ← → para navegar, R para reiniciar
- Clic en flechas laterales en pantalla
- Dots de navegación en la parte inferior
- Posición guardada en localStorage

## Despliegue en producción

### Opción 1: Static hosting (Vercel, Netlify, GitHub Pages)
```bash
# Subir todos los archivos manteniendo la estructura de carpetas
# La presentación funciona como single-page sin build step
```

### Archivos necesarios para deploy:
```
/
├── Orion AI Consulting.html   (index)
├── deck-stage.js
├── uploads/
│   ├── Orion Consulting AI Logo.png
│   ├── UGC Chica-influencer, infoproducto.mp4
│   └── Avatar económico hablando a camara.mp4
```

### Opción 2: Renombrar index
Para servir como página principal, renombrar `Orion AI Consulting.html` → `index.html`

### Opción 3: Embeber en sitio existente
El deck puede embeberse en un iframe o integrarse en cualquier sitio web.

## Videos — Instrucciones de integración (slide 7)

El slide 7 tiene **3 placeholders** con comentarios HTML detallados. Para agregar cada video:

1. **VIDEO 1 — UGC Chica + Infoproducto**
   - Archivo fuente: `uploads/UGC Chica-influencer, infoproducto.mp4`
   - Renombrar a: `videos/ugc-chica.mp4`
   - Reemplazar el `<div class="gc vph">` con:
   ```html
   <video controls style="width:100%;height:100%;object-fit:contain;background:#000" preload="metadata">
     <source src="videos/ugc-chica.mp4" type="video/mp4">
   </video>
   ```

2. **VIDEO 2 — Avatar Económico hablando a cámara**
   - Archivo fuente: `uploads/Avatar económico hablando a camara.mp4`
   - Renombrar a: `videos/avatar-economico.mp4` (quitar tilde para evitar problemas)
   - Mismo patrón `<video>` apuntando a `videos/avatar-economico.mp4`

3. **VIDEO 3 — Influencer Real Clonada (voz + avatar)**
   - Archivo: `videos/influencer-clonada.mp4` (pendiente de agregar)
   - Mismo patrón `<video>` apuntando a `videos/influencer-clonada.mp4`

**Tip**: Busca en el HTML `VIDEO 1`, `VIDEO 2`, `VIDEO 3` para localizar exactamente dónde pegar cada `<video>` tag.

## Paleta de colores
```
--bg:     #070511   (fondo principal)
--bg2:    #0F0A1E   (fondo secundario)
--v:      #7B35F4   (violeta brand)
--c:      #00D4FF   (cian accent)
--g:      #00E5A0   (verde ROI)
--m:      #D132B8   (magenta)
--tx:     #F0EAFF   (texto principal)
--mu:     #9086A8   (texto muted)
```

## Fuentes
- Bebas Neue — Títulos display
- Outfit 300–800 — Body text
- JetBrains Mono — Datos / métricas / código

Cargadas desde Google Fonts (requiere conexión). Para uso offline, descargar y servir localmente.

## Personalización rápida
- **Cambiar datos en slides FBI (5,6,8,9)**: editar directamente el HTML en las secciones `<section data-label="...">`
- **Agregar video**: copiar el bloque `<video controls>` del slide 7 y ajustar la fuente
- **Cambiar colores**: modificar variables CSS en `:root { ... }` al inicio del `<style>`
- **Agregar slides**: insertar un nuevo `<section data-label="...">` dentro de `<deck-stage>` y actualizar `const N=13` → el número nuevo
