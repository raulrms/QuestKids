# 🏰 Quest Kids — RPG de Hábitos

Aplicación web de página única (HTML + CSS + JS, sin dependencias externas de backend) que convierte los hábitos y tareas diarias de los niños en un juego de rol: misiones, niveles, monedas y una tienda de recompensas.

El proyecto nació como una réplica funcional de una página de Notion ("Quest Kids — RPG de Hábitos") usada como sistema de gamificación de hábitos en casa.

## ✨ Características

- **4 héroes** con nombre y clase propios (Guerrero / Druida), cada uno con su progreso independiente.
- **Sistema de niveles** basado en XP acumulada, con título narrativo por nivel (Aprendiz → Aventurero → Veterano → Héroe → Campeón → Leyenda).
- **Misiones diarias**, que se reinician automáticamente cada día.
- **Misiones épicas**, cada una con su propia frecuencia de reinicio: **diaria** o **semanal**.
- **Botón de deshacer** en cualquier misión completada, con confirmación de doble toque.
- **Tienda de recompensas** con historial de canjes.
- **Racha semanal**: completar todas las misiones diarias 7 días seguidos otorga un bonus extra de XP y monedas.
- **Barra lateral** con un resumen de cada héroe para cambiar de jugador.
- Diseño pensado para uso en móvil y en pantallas grandes.

## 🚀 Cómo usarlo

No requiere instalación ni servidor: es un único archivo HTML autocontenido.

1. Descarga `quest-kids.html`.
2. Ábrelo con cualquier navegador.
3. Elige el héroe activo y empieza a completar misiones.

## 💾 Persistencia de datos

Los datos se guardan con `localStorage`, local al navegador y dispositivo donde se abra el archivo.

- El progreso no se sincroniza automáticamente entre dispositivos.
- Borrar los datos de navegación también borrará el progreso del juego.

Está en estudio una versión con almacenamiento centralizado en red local y/o una versión empaquetada como app Android instalable.

## 🛠️ Estado del proyecto / mejoras en curso

| # | Mejora | Estado |
|---|--------|--------|
| 1 | Frecuencia propia (diaria/semanal) para misiones épicas | ✅ Hecho |
| 2 | Botón de deshacer en misiones completadas, con confirmación de doble toque | ✅ Hecho |
| 3 | Detección de días saltados sin abrir la app en el cálculo de racha semanal | ⏳ Pendiente |
| 4 | PIN o bloqueo de adulto para la tienda de recompensas y la edición de misiones | ⏳ Pendiente |
| 5 | Panel de edición de misiones y recompensas | ⏳ Pendiente |

## 📁 Estructura del proyecto

```
quest-kids.html   → aplicación completa (HTML + CSS + JS en un único archivo)
README.md         → documentación del proyecto
```

## 📌 Notas técnicas

- Sin frameworks ni dependencias externas de backend: HTML, CSS y JavaScript nativo.
- Tipografías vía Google Fonts (`Press Start 2P`, `Nunito`).
- Misiones, recompensas y niveles están definidos como datos dentro del propio script (`DAILY_MISSIONS`, `SPECIAL_MISSIONS`, `REWARDS`, `LEVELS`).

## 📄 Licencia

Proyecto de uso personal/familiar. Sin licencia formal definida.
