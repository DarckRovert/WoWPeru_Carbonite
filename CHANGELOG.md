# 📜 Historial de Cambios — WoWPeru_Carbonite

Registro detallado de versiones, correcciones de estabilidad y mejoras aplicadas a la edición de Carbonite para **WoW Perú**.

---

## [3.34-WP] — 2026-10-05 (Hardened Edition)

### 🎨 Mejoras Visuales & Estilo
- **Fix Fondo Blanco en Opciones (`NxOpts`):**
  - Solucionado el problema donde la ventana de opciones (`/carb options`) se dibujaba con fondo blanco brillante `#ECECEC`.
  - Inyección de `SetBackdropColor(0.12, 0.12, 0.12, 0.88)` y `SetBackdropBorderColor` en `Nx.Win:CrB1()`, `Nx.Win:ReB()`, `Nx.Opt:Cre()` y `Nx.Opt:Ope()`.
  - Implementado tema oscuro nativo estilo *Charcoal Dark Mode* consistente con el resto de la interfaz.

### 🛡️ Resiliencia & Errores de Runtime
- **Fix Nil-Comparison en Quest Tracker (`F()`):**
  - Resuelto el error `Carbonite.lua:18190: attempt to compare nil with number` que ocurría al ordenar misiones sin distancia finita, eliminando más de 15,000 errores de Lua por sesión.
- **Fix Nil Table Index en Mapeo de Zonas (`InT1`, `ITCZ`):**
  - Eliminados los crashes por `table index is nil` o `attempt to compare number with nil` al indexar IDs de mapas de mazmorras personalizadas o zonas fuera de rango en `Nx.Map.TCA`.
- **Blindaje de Contexto de Script `OnUpdate` (`Nx.Win:OnU`):**
  - Sustituida la dependencia exclusiva de la variable global `this` por `local this = self or this` y validación defensiva `if not this or not this.NxW then return end` para compatibilidad total con WoW 3.3.5a.

### ⚙️ Compatibilidad de Ecosistema
- Integración en el registro arquitectónico maestro de addons de WoW Perú (`ECOSYSTEM_MASTER_AUDIT.md`).
- Optimización de coexistencia con `WoWPeru_DragonflightUI` y `WoWPeru_Companion`.

---

## [3.34-Original] — 2010 (Carbon Based Creations)
- Última versión comunitaria oficial de Carbonite para Wrath of the Lich King 3.3.5a.
