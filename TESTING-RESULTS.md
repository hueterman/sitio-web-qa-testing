# TESTING-RESULTS.md

**Proyecto:** sitio-web-qa-testing
**PR:** feature/improve-html-accessibility → main
**QA Engineer:** Pedro Huete Toral

## Resumen ejecutivo

Los 6 tests de la batería de QA han sido ejecutados. **6/6 PASSED ✓**

---

## TEST 1: Validez HTML

**Herramienta:** W3C Markup Validator + validador local (nu-html-checker)

- **Opción 1 (W3C Validator, validator.w3.org):** Documento verde — *"Document checking completed. No errors or warnings to show."*
- **Opción 2 (nu-html-checker, CLI local):** `No validation errors found`.

**Criterio de éxito:** 0 errores, máximo 3 warnings permitidos.
**Resultado: ✅ PASS** (0 errores, 0 warnings en ambas herramientas)

---

## TEST 2: Auditoría de Accesibilidad (WAVE)

**Herramienta:** Extensión WAVE para Chrome

**Resultado del panel:**
| Errores | Errores de contraste | Alertas | Features | Elementos estructurales | ARIA |
|---|---|---|---|---|---|
| 0 | 0 | 0 | 6 | 18 | 1 |

**Criterio de éxito:** 0 errores rojos, máximo 5 alertas amarillas.
**Resultado: ✅ PASS** (0 errores, 0 alertas — mejor que el mínimo exigido)

---

## TEST 3: Estrés Responsive

**Herramienta:** Chrome DevTools → Device Mode

**320px (Móvil):**
- [x] Sin scroll horizontal
- [x] Botones ≥48px
- [x] Texto ≥14px legible
- [x] Navegación adaptada (apilada verticalmente, un ítem por línea)

**768px (Tablet):**
- [x] Grid de 2 columnas en Features
- [x] Navegación en línea horizontal
- [x] Espaciado adecuado

**1440px (Desktop):**
- [x] Grid de 3 columnas en Features
- [x] Max-width del contenedor respetado (contenido centrado, no a sangre completa)

**Criterio de éxito:** Diseño fluido sin roturas en los 3 anchos.
**Resultado: ✅ PASS**

---

## TEST 4: Contraste de Color (WCAG)

**Herramienta:** Cálculo de ratio WCAG a partir de los colores definidos en `styles.css` (recomendable verificar también con Color Contrast Analyzer / webaim.org).

| Combinación | Ratio | Nivel |
|---|---|---|
| Texto cuerpo `#111827` sobre blanco `#ffffff` | 17.74:1 | AAA |
| Texto cuerpo `#111827` sobre fondo `#f9fafb` | 16.98:1 | AAA |
| Enlaces `#1e40af` sobre blanco | 8.72:1 | AAA |
| Texto secundario `#6b7280` sobre blanco | 4.83:1 | AA |
| Texto blanco sobre header azul `#2563eb` | 5.17:1 | AA |
| Texto blanco sobre azul oscuro `#1e40af` | 8.72:1 | AAA |

**Criterio de éxito:** Ratio mínimo 4.5:1 (AA).
**Resultado: ✅ PASS** (todas las combinaciones superan el mínimo AA)

---

## TEST 5: Navegación por Teclado (Focus)

**Herramienta:** Tecla TAB

**Acción:** Navegación completa de la web sin ratón — links, botones, inputs del formulario e ítems de navegación.

**Criterio de éxito:** Recuadro (outline) azul grueso visible en el elemento seleccionado en todo momento.
**Resultado: ✅ PASS**

---

## TEST 6: Rendimiento (Lighthouse)

**Herramienta:** Chrome DevTools → Lighthouse, modo Mobile

| Ejecución | Performance | Accessibility | Best Practices | SEO |
|---|---|---|---|---|
| 1ª (ventana normal) | 74 | 69 | 69 | 91 |
| 2ª (ventana incógnito) | **100** | **100** | **96** | 100 |

**Nota:** La primera ejecución estaba contaminada por una extensión de Chrome (Aitopia) que inyecta elementos en el DOM de cualquier página visitada, penalizando falsamente Accessibility y Best Practices. Se repitió en incógnito (sin extensiones) para obtener una medición limpia. Los 96 puntos de Best Practices se deben a 3 errores de red (`ERR_CONNECTION_CLOSED`) por imágenes de `via.placeholder.com`, servicio actualmente caído — sin impacto en el criterio de aceptación.

**Criterio de éxito:** >90 en Performance, Accessibility y Best Practices.
**Resultado: ✅ PASS**

---

## Resumen para el Code Review (Review General del PR)

```
### QA Testing Summary
All 6 tests PASSED ✓

**Responsive**:
- 320px ✓ (vertical layout, touch-friendly)
- 768px ✓ (2-column grid)
- 1440px ✓ (3-column grid, max-width respected)

**Accessibility**:
- HTML5 valid ✓ (validator.w3.org + local nu-html-checker)
- WAVE audit: 0 errors ✓ (0 alerts)
- Color contrast: up to 17.74:1 ✓ (WCAG AAA in most pairs)
- Focus indicators: Visible 3px outline ✓ (TAB navigation confirmed)

**Performance**:
- Lighthouse (incognito): Performance 100, A11y 100, BestPrac 96

### Approved for merge!
```
