# ZoneCrates 2.1.0-beta2 — Configuration / Configuración

## English

Active inputs: `config/ZONEMODS/zonecrates/ajustes.toml` and `cajas.toml`. First creation imports existing world rewards; do not overwrite a live catalog with an example. Reload from `/crates editar` > Tools > Reload TOML. Validation is all-or-nothing; GUI saves reject stale external edits. The old common TOML and tiers_y_premios export remain historical and are not active inputs. Global tier rewards are shared by all physical coffers of that tier. See the complete [release guide](RELEASE-2026-11-04.md) for keys, bounds, NBT/capability handling, inventory modes, death persistence and administrative controls.

## Español

Entradas activas: `config/ZONEMODS/zonecrates/ajustes.toml` y `cajas.toml`. La primera creación importa premios del mundo; no sobrescribas un catálogo real con un ejemplo. Recarga desde `/crates editar` > Herramientas > Recargar TOML. Una validación errónea conserva el estado activo; el editor rechaza cambios externos sin recargar. Los TOML common y tiers_y_premios anteriores son históricos y no se leen. Todos los cofres físicos de un nivel comparten sus premios. [Guía completa y límites](RELEASE-2026-11-04.md).

## Default settings / Ajustes predeterminados

```toml
# ZoneCrates 2.1.0-beta2. Configuración REAL del servidor.
# Recarga desde /crates editar > Herramientas > Recargar TOML.
# Un error rechaza la recarga completa y conserva la configuración activa.
[general]
enabled = true
keyShopEnabled = true
menuOpeningEnabled = true
# Si es true, abrir desde /crates requiere un cofre del nivel cerca.
requireNearbyCrate = false
interactionRadius = 6
# Limita nuevas altas; nunca borra premios existentes al reducirlo. Máximo técnico: 10.
maxRewardsPerTier = 10
maxAddedStackCount = 64

[keys]
physicalKeysEnabled = true
# false permite que los jugadores utilicen sus llaves físicas del nivel correcto.
physicalKeysAdminOnly = false

[death]
keepWallet = true
keepKeys = true

[physical]
adminOnlyPlacement = true
adminOnlyBreaking = true
explosionProof = true

[opening]
# 20 ticks = 1 segundo. La protección entre aperturas usa el mayor de ambos valores.
durationTicks = 100
minimumIntervalTicks = 20
allowSkip = true
# DROP_REMAINDER suelta solo el sobrante. REQUIRE_SPACE rechaza sin gastar llave.
fullInventoryMode = "DROP_REMAINDER"

[effects]
soundEnabled = true
soundVolume = 0.5
particlesEnabled = true
particleInterval = 8
idleMotion = true
floatingLabels = true
labelDistance = 16

[logging]
# Registra aperturas, compras y herramientas administrativas en el log del servidor.
auditActions = true

```

`cajas.toml`: seven `tiers.<tier>` sections with enabled, key_price (decimal string), cooldown_seconds, default_weight and up to ten rewards with item/count/weight/nbt/forge_caps. / Siete niveles con precio decimal exacto y premios ponderados; no sustituir los premios reales con datos de prueba.
