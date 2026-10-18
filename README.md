# 🏰 Quest Kids — RPG de Hábitos

Aplicación web de página única (HTML + CSS + JS, sin dependencias externas de backend) que convierte los hábitos y tareas diarias de los niños en un juego de rol: misiones, niveles, monedas y una tienda de recompensas.

El proyecto nació como una réplica funcional de una página de Notion ("Quest Kids — RPG de Hábitos") usada como sistema de gamificación de hábitos en casa.

## ✨ Características

- **4 héroes** con nombre propio y **profesión e icono configurables** (botón ✏️ en la ficha).
- **Sistema de niveles** basado en XP acumulada, con título narrativo por nivel (Aprendiz → Aventurero → Veterano → Héroe → Campeón → Leyenda).
- **Misiones diarias**, que se reinician automáticamente cada día.
- **Misiones épicas**, cada una con su propia frecuencia de reinicio: **diaria** o **semanal**.
- **Botón de deshacer** en cualquier misión completada, con confirmación de doble toque (sin diálogos nativos del navegador, para funcionar también dentro de vistas previas en sandbox). Si el deshacer hace que deje de cumplirse la semana perfecta, también se retira el bonus semanal.
- **Tienda de recompensas** con confirmación de doble toque al canjear e historial de canjes.
- **Racha semanal**: completar todas las misiones diarias los 7 días de la semana otorga un bonus de +100 XP y +50 monedas. Un día sin completar rompe la racha.
- **Pestañas** (Diarias / Épicas / Tienda) y **mini-barra fija** con nivel, XP y monedas que aparece al hacer scroll.
- **Barra de héroes** con una miniatura de cada jugador, para cambiar de héroe con un toque (rejilla 2×2 en móvil).
- **Copia de seguridad**: descarga/restauración del progreso en JSON (o como texto copiable), con validación y confirmación antes de reemplazar datos.
- **Robustez**: detecta el cambio de día aunque la página lleve abierta desde ayer, sincroniza varias pestañas abiertas y, si el navegador bloquea `localStorage`, avisa en pantalla en vez de quedarse en blanco.

## 🚀 Cómo usarlo

No requiere instalación ni servidor: es un único archivo HTML autocontenido.

1. Descarga `quest-kids.html`.
2. Ábrelo con cualquier navegador (doble clic, o "Abrir con...").
3. Elige el héroe activo desde el desplegable o la barra lateral, y empieza a completar misiones.

## 💾 Persistencia de datos

Los datos (XP, monedas, misiones completadas, historial de canjes, icono y profesión) se guardan con `localStorage`, **local al navegador y dispositivo donde se abra el archivo**. Esto significa que:

- El progreso no se sincroniza automáticamente entre dispositivos distintos (por ejemplo, entre el móvil de un niño y una tablet). Para moverlo a mano, usa **Copia de seguridad → Descargar copia** y **Restaurar** en el otro dispositivo.
- Borrar los datos de navegación de ese navegador borra también el progreso: conviene descargar una copia de vez en cuando.
- Si los datos guardados estuvieran corruptos, la app arranca limpia y conserva el texto original bajo la clave `questKidsRPG_corrupto`.

Está en estudio una versión con almacenamiento centralizado en red local (servidor propio) y/o empaquetada como app Android instalable.

## 🛠️ Estado del proyecto / mejoras en curso

| # | Mejora | Estado |
|---|--------|--------|
| 1 | Frecuencia propia (diaria/semanal) para misiones épicas | ✅ Hecho |
| 2 | Botón de deshacer en misiones completadas, con confirmación de doble toque | ✅ Hecho |
| 3 | Detección de días saltados en el cálculo de racha semanal | ✅ Hecho |
| 4 | PIN o bloqueo de adulto para la tienda de recompensas y la edición de misiones | ⏳ Pendiente |
| 5 | Panel de edición de misiones y recompensas (actualmente fijas en el código) | ⏳ Pendiente |

Limitaciones conocidas: los canjes de la tienda no se pueden anular desde la interfaz, y cualquiera con acceso a la app puede completar misiones, canjear premios o restaurar copias (hasta que se implemente el punto 4).

## 📁 Estructura del proyecto

```
quest-kids.html   → aplicación completa (HTML + CSS + JS en un único archivo)
README.md         → este documento
```

## 📌 Notas técnicas

- Sin frameworks ni dependencias externas: HTML, CSS y JavaScript nativo.
- Tipografías vía Google Fonts (`Press Start 2P`, `Nunito`).
- Todo el contenido de misiones, recompensas y niveles está definido como datos dentro del propio script (`DAILY_MISSIONS`, `SPECIAL_MISSIONS`, `REWARDS`, `LEVELS`), por lo que cualquier cambio de contenido implica editar el archivo directamente hasta que se implemente el panel de edición (punto 5 de la tabla anterior).

## 📄 Licencia

Proyecto de uso personal/familiar. Sin licencia formal definida.