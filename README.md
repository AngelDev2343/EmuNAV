# 🎮 EmuNav

![Platform](https://img.shields.io/badge/platform-browser--only-blue)
![DS](https://img.shields.io/badge/consola-Nintendo%20DS-red)
![License](https://img.shields.io/badge/license-all%20rights%20reserved-lightgrey)

**EmuNav** es una interfaz web para jugar ROMs de **Nintendo DS** directamente en el navegador, sin instalaciones ni configuraciones. Está construida sobre el emulador **Desmond DS** y ofrece una experiencia limpia y minimalista.

---

## 📜 Licencia

**Todos los derechos reservados**

Este proyecto no es Open-Source y es creado con fines personales/demostrativos.

---

## 🎯 Objetivo

Ofrecer una forma sencilla de correr juegos de Nintendo DS en el navegador, con una interfaz ligera que no requiere conocimientos técnicos.

---

<div align="center">

[🎮 Probar ahora](https://angeldev2343.github.io/EmuNAV/)

Si quieres probarlo y no tienes ROMS, puedes descargar las que se encuentran en este repositorio son 100% legales.
</div>

---

## 🖥️ Estructura del proyecto

```
EmuNav/
├── index.html        # Interfaz principal (controles, iframe del emulador)
├── emulator.html     # Wrapper del emulador Desmond DS
├── style.css         # Estilos de la interfaz
└── desmond.min.js    # Motor del emulador (Desmond DS, externo)
```

---

## ⚙️ Cómo funciona

1. `index.html` carga la interfaz y embebe `emulator.html` dentro de un `<iframe>` escalado
2. `emulator.html` inicializa el componente `<desmond-player>` y espera a que el usuario cargue una ROM
3. Al seleccionar un archivo `.nds`, se crea un `Object URL` y se pasa al método `loadURL()` del emulador
4. Una vez cargada la ROM, la pantalla de controles se oculta y el emulador ocupa toda el área

---

## 🕹️ Controles de teclado

| Acción | Tecla |
|--------|-------|
| D-Pad Arriba | `W` |
| D-Pad Abajo | `S` |
| D-Pad Izquierda | `A` |
| D-Pad Derecha | `D` |
| Botón A | `J` |
| Botón B | `K` |
| Botón X | `U` |
| Botón Y | `I` |
| L (hombro) | `Q` |
| R (hombro) | `E` |
| Start | `Enter` |
| Select | `Shift` |

---

## 🖼️ Interfaz

- **Header** con nombre y descripción
- **Sección de controles** colapsable (`<details>`)
- **Área del emulador** escalada con `transform: scale()` para mayor visibilidad, con recorte del margen interno del emulador mediante offset negativo
- **Botón de pantalla completa** integrado sobre el área de juego

---

## 📋 Requisitos

- Navegador moderno con soporte para **WebAssembly** y **Custom Elements** (Web Components)
- Una ROM de Nintendo DS en formato `.nds` (no incluida)
- El archivo `desmond.min.js` debe estar presente en la misma carpeta

> ⚠️ EmuNav no incluye ROMs ni el binario del emulador. Debes obtenerlos por tu cuenta.

---

## 🌍 Compatibilidad

| Navegador | Estado |
|-----------|--------|
| Google Chrome | ✅ Recomendado |
| Microsoft Edge | ✅ Compatible |
| Safari | ✅ Compatible |
| Firefox | ⚠️ No probado |

---

## 🛠️ Estado del proyecto

- **Estado:** Estable
- **Naturaleza:** Experimental / Personal

### Limitaciones conocidas

- Requiere que el archivo `desmond.min.js` esté disponible localmente
- El emulador inicializa con un retraso de ~1 segundo para dar tiempo al motor de cargarse
- La pantalla táctil (segunda pantalla DS) puede aparecer en negro dependiendo del juego

---

## 🙏 Créditos

- **Desmond DS** — motor de emulación de Nintendo DS que corre en el navegador vía WebAssembly
- **Press Start 2P** / **Nunito** — tipografías vía Google Fonts
- **EmuNav UI** — Interfaz y estilos por Angel
