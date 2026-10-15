# ¿Quién es ese Pokémon?

Juego tipo "¿Quién es quién?" para 2 jugadores con los 1025 Pokémon de las 9 generaciones.
Cada jugador elige un Pokémon secreto de un tablero de 24 y, por turnos, hacen preguntas de sí o no
hasta adivinar el del otro.

## Modos de juego

- **En un solo dispositivo:** se pasan el celular o la compu. Una pantalla de pausa tapa el tablero entre turnos.
- **Online:** cada uno en su pantalla, con un código de partida de 4 letras. Necesita Firebase (ver abajo).

## Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | Todo el juego: diseño, lógica y datos de los Pokémon (nombre en español y tipos) |
| `g/g1.json` … `g/g9.json` | Las imágenes de cada generación; se descargan solo las que hacen falta |
| `database.rules.json` | Reglas de seguridad para Firebase Realtime Database |

## Probarlo en la PC

```bash
python -m http.server 8765
```

Y abrir http://localhost:8765. En `localhost` el modo online funciona entre pestañas del mismo navegador, para probar.

## Activar el modo online (Firebase, gratis)

1. Crear un proyecto en https://console.firebase.google.com
2. **Build → Authentication → Sign-in method:** activar **Anónimo**.
3. **Build → Realtime Database:** crear la base y, en la pestaña **Reglas**, pegar el contenido de `database.rules.json`.
4. **Configuración del proyecto → Tus apps → Web (`</>`):** registrar una app y copiar la configuración.
5. Pegar esos valores en `FIREBASE_CONFIG` dentro de `index.html` (incluido `databaseURL`) y subir el cambio.

Las imágenes de los Pokémon son de [PokeAPI](https://github.com/PokeAPI/sprites). Pokémon y sus nombres son marcas de Nintendo, Creatures Inc. y GAME FREAK inc. Proyecto de fans, sin fines comerciales.
