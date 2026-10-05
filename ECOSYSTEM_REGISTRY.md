# 🌐 Registro de Ecosistema — WoWPeru_Carbonite

Ficha técnica oficial de registro en la infraestructura multi-addon de **WoW Perú - Reino Andino**.

---

## 1. Identidad del Addon

| Campo | Valor |
|---|---|
| **Nombre Técnico** | `Carbonite` |
| **Título en Cliente** | `|cFFD4AF37WoW Perú|r - Carbonite 3.34 HD` |
| **Versión** | `3.34-WP` |
| **Tipo de Sistema** | Suite Integral de Cartografía Satelital, Navegación y Rastreo de Misiones |
| **Repositorio GitHub** | [DarckRovert/WoWPeru_Carbonite](https://github.com/DarckRovert/WoWPeru_Carbonite) |
| **Directorio de Instalación** | `Interface\AddOns\Carbonite\`, `CarboniteItems\`, `CarboniteNodes\`, `CarboniteTransfer\` |

---

## 2. Persistencia de Datos

| Variable Global | Tipo | Ámbito | Propósito |
|---|---|---|---|
| `NxData` | Tabla Lua (`SavedVariables`) | Por Cuenta | Guarda configuración global de ventanas, skins, atajos y opciones generales |
| `NxCombatOpts` | Tabla Lua (`SavedVariables`) | Por Cuenta | Opciones de seguimiento en combate |
| `NxMapOpts` | Tabla Lua (`SavedVariables`) | Por Cuenta | Configuración del mapa satelital, capas de iconos y rutas |
| `NxCData` | Tabla Lua (`SavedVariablesPerCharacter`) | Por Personaje | Historial de misiones completadas y waypoints locales |

---

## 3. Matriz de Integración del Ecosistema

| Sistema Coexistente | Modo de Interacción | Flujo de Datos |
|---|---|---|
| **`WoWPeru_Companion`** | Telemetría / Detección P2P | Detecta estado cargado y coordina presencia del jugador. |
| **`WoWPeru_DragonflightUI`** | Coexistencia Gráfica | Respeta anclajes de minimapa y marcos de acción modernos. |
| **`WoWPeru_IntiObjGPS`** | Navegación Andina | Complementa la navegación con waypoints de objetivos y nodos especiales. |
| **`WoWPeru_RaidSuite`** | Liberación de Combat Log | Prioriza la captura de eventos tácticos sin interferencias. |

---

## 4. Garantías de Rendimiento & Hardening

- **Cero Nil-Crashes:** Eliminados más de 15,000 errores de runtime en ordenamiento de misiones (`F()`) y mapeo de zonas (`InT1`, `ITCZ`).
- **Tema Oscuro Integrado:** El menú de opciones y ventanas fijas cargan con fondo carbón translúcido (`0x1F1F1FE0`), corrigiendo el bug de fondo blanco de WoW 3.3.5a.
- **Hardware de Cabina:** Optimizado para no generar tirones de framerate en equipos de bajo rendimiento con gráficos integrados.
