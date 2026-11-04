# ZoneCrates

## Current builds / Versiones actuales — 2026-11-04

| Side / Lado | Version / Versión | File / Archivo |
|---|---|---|
| universal | 2.1.0-beta2 | [zonecrates-2.1.0-beta2-protected.jar](https://www.curseforge.com/projects/1738036/files/9438417) |

Minecraft 1.20.1 / Forge 47.4.x / Java 17. Protected public Beta builds; availability depends on each file approval. / Betas públicas protegidas; disponibilidad según aprobación de cada archivo.

## English — What is new

Seven original physical coffer tiers with animated lids, custom models, matching physical/virtual keys and blue/purple/cyan UI. Commands are now /crates and /crates editar; the old /zonecreate, /zonascreate and /zonecrates aliases were removed. Active editable configuration is config/ZONEMODS/zonecrates/ajustes.toml and cajas.toml, with validated reload, external-edit conflict detection and GUI rollback. Preserves the shared GodieCoin wallet/API, imports existing SavedData on first creation and retains historical configuration files without reading them. Same universal beta2 JAR on BOTH sides; protocol 4, incompatible with beta1/3 or 2.0.6/2. Core is required only on SERVER.

## Español — Novedades

Siete cofres físicos originales con tapas animadas, modelos propios, llaves físicas/virtuales y GUI azul/morada/celeste. Comandos actuales /crates y /crates editar; retirados /zonecreate, /zonascreate y /zonecrates. Configuración editable activa en config/ZONEMODS/zonecrates/ajustes.toml y cajas.toml, con recarga validada, detección de ediciones externas y rollback del editor. Conserva cartera/API GodieCoin e importa SavedData al crear TOML por primera vez; conserva los archivos históricos sin leerlos. Mismo JAR universal beta2 en AMBOS lados: protocolo 4, incompatible con beta1/3 y 2.0.6/2. Core obligatorio solo en SERVIDOR.

## Installation / Instalación

The universal Crates beta2 JAR is identical on both sides; Core is required on server only. / El universal Crates beta2 es el mismo en ambos lados; Core solo es obligatorio en servidor.

Stop the affected instance, back up the world/config, remove only the previous same-mod/same-side JAR, and install the table version. Preserve character data, wallets and TOML. Do not put server-only dependencies on clients. / Detén la instancia, respalda mundo/config, sustituye solo el JAR anterior del mismo mod y lado, y conserva personajes, cartera y TOML. No instales dependencias exclusivas de servidor en el cliente.

## Dependencies / Dependencias

**universal**: `zonecore` [2.0.0,) (required/obligatorio; SERVER).

[Full changes and usage / Novedades y uso](RELEASE-2026-11-04.md) · [Configuration / Configuración](CONFIGURATION.md) · [Historical releases / Entregas históricas](RELEASES.md).

## Validation / Verificación

Original release checks and isolated startup/command registration of the protected set were reviewed. Shared schemas: Essentials 35, Guardian 13 and Misions 4 classes, with no mapping differences. This does not certify a new graphical client session, two-player gameplay, full third-party modpack, hosting deployment or FPS/TPS. / Revisadas las verificaciones de entrega y el arranque/registro de comandos del conjunto protegido. Esquemas compartidos sin diferencias de mapeo: Essentials 35, Guardian 13 y Misions 4 clases. No certifica una nueva sesión gráfica, dos jugadores, modpack completo, hosting ni FPS/TPS.

## Ownership / Titularidad

Original ZONE code and visual assets © Elgochogms. Public documentation only: no mod sources, private obfuscation maps, credentials or production player data. Existing rights of earlier distributions are preserved.
