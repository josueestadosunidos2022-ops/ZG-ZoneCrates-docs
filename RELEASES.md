# ZG ZoneCrates — releases / entregas

## 2.0.6 protected candidate / candidato protegido

- Minecraft 1.20.1, Forge 47.x, Java 17; **one universal JAR installed on client and server**.
- Required server dependency: ZoneCore `[2.0.0,)`. ZoneGuardian integration is optional. ZoneClans 1.1.4 requires ZoneCrates `[2.0.1,3)`.
- `zonecrates-2.0.6-protected.jar` SHA-256: `8E31E9B39D260628CF317C60F072AF2A459D9EB1301DC1200978C36C286CE79E`.
- New release metadata: author Elgochogms, All Rights Reserved. Original ZONE key texture replaces the earlier vanilla gold base texture. This does not revoke the license of older MIT copies.
- Gradle clean build and ProGuard completed. The protected JAR started on an isolated Forge 47.4.10 / Java 17 server with protected ZoneCore 2.1.3; `/zonecrates config lista` returned seven tiers, `/zonecrates reload` responded, and shutdown was clean. A second startup with protected ZoneClans server 1.1.4 passed command registration and clean shutdown.
- Client rendering, player wallet transactions, complete modpack, multiplayer, and production hosting have **not** been tested with this exact protected JAR. The three generated common TOML keys are currently inactive; see [configuration](CONFIGURATION.md).
- CurseForge upload and moderation remain pending. This candidate is not yet a publicly downloadable release.

## Español

La versión 2.0.6 usa **un único JAR universal** en cliente y servidor. Requiere ZoneCore en el servidor. La compilación, ofuscación y dos pruebas de arranque/apagado aisladas terminaron bien; no equivalen a una prueba gráfica, de transacciones, modpack completo ni hosting. La carga en CurseForge sigue pendiente. Verifica el SHA-256 y respalda el mundo antes de instalarla.

