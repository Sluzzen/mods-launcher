# mods-launcher 🚀

Repositorio centralizado de paquetes de mods, configuraciones y recursos para launchers de Minecraft desarrollados por **SLuzzen**.

---

## 🌳 Estructura de Ramas por Servidor

Cada servidor dispone de una rama dedicada que contiene sus respectivos mods, configuraciones y manifiesto:

| Servidor | Rama | Loader / Versión | Descripción |
| :--- | :--- | :--- | :--- |
| **Doraland** | `main` | NeoForge 21.1.250 (MC 1.21.1) | Paquete oficial de Doraland con 149 mods, emotes, shaders y menús customizados |

---

## 📁 Estructura de Archivos en cada Rama

```text
├── mods/                  # Archivos .jar de los mods del servidor
├── overrides/             # Configuraciones (config/), shaders, defaultconfigs y emotes
└── mods-manifest.json     # Manifiesto JSON con checksums (SHA1), tamaños y rutas oficiales
```

---

## 🛠️ Cómo agregar un Nuevo Servidor

1. Crea una nueva rama con el nombre del servidor:
   ```bash
   git checkout -b <nombre-del-servidor>
   ```
2. Coloca los mods en la carpeta `mods/` y las configuraciones en `overrides/`.
3. Genera el manifiesto oficial con `npm run manifest` en el launcher.
4. Sube la rama a GitHub:
   ```bash
   git push -u origin <nombre-del-servidor>
   ```
5. En el `launcher-config.json` de ese launcher, define:
   ```json
   "mods": {
     "githubOwner": "Sluzzen",
     "githubRepo": "mods-launcher",
     "branch": "<nombre-del-servidor>"
   }
   ```
