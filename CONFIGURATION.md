# ZoneCrates — Configuration / Configuración (2026-11-06)

| Side / Lado | Version / Versión |
|---|---|
| Universal / Ambos lados | 2.1.0-beta4 |

## Server files / Archivos del servidor

`config/ZONEMODS/zonecrates/ajustes.toml` controls rules and effects. `cajas.toml` holds the seven tier tables. On first creation, existing world rewards are imported; keep your real files. / `ajustes.toml` controla reglas y efectos; `cajas.toml`, las siete tablas. La primera generación importa premios del mundo; conserva los archivos reales.

Use `/crates editar` → Herramientas → Recargar TOML after external edits. Invalid reloads retain the last valid configuration. External changes invalidate stale editor actions. / Recarga desde Herramientas tras editar fuera del juego. Una recarga inválida conserva la configuración válida y una revisión nueva invalida acciones antiguas.

| Key / Clave | Default / Valor inicial | Meaning / Uso |
|---|---|---|
| `general.enabled` | `true` | Enable purchases/openings / Habilitar compras y aperturas |
| `general.requireNearbyCrate` | `false` | Require matching nearby coffer for menu opening / Exigir cofre cercano al abrir por menú |
| `general.interactionRadius` | `6` | 1–8 blocks / bloques |
| `opening.durationTicks` | `100` | 20–200 ticks; 20 ticks = 1 s |
| `opening.minimumIntervalTicks` | `20` | 0–1200 ticks; additional shared interval / intervalo común adicional |
| `opening.allowSkip` | `true` | Early reveal does not bypass cooldown / Revelar antes no evita la espera |
| `opening.fullInventoryMode` | `"DROP_REMAINDER"` | Insert what fits, drop remainder / Insertar lo posible y soltar sobrante |
| `effects.particlesEnabled` | `true` | Controls coffer particles and aura / Controla partículas y aura |
| `effects.soundEnabled` | `true` | Sounds / Sonidos |
| `effects.soundVolume` | `0.5` | 0–1 |
| `death.keepWallet`, `death.keepKeys` | `true` | Preserve wallet and virtual keys on death / Conservar cartera y llaves virtuales al morir |
| `physical.adminOnlyPlacement`, `physical.adminOnlyBreaking` | `true` | Administrative placement/removal / Colocación y retirada administrativa |
| `physical.explosionProof` | `true` | Explosion protection / Protección frente a explosiones |

`REQUIRE_SPACE` requires room for any possible reward before rolling. The shared opening lock uses the larger of duration and minimum interval, plus the tier cooldown. / `REQUIRE_SPACE` exige espacio para cualquiera de los premios antes del sorteo. El bloqueo usa el mayor de duración e intervalo, además de la espera del nivel.

Each `tiers.easy`, `medium`, `hard`, `escarlata`, `iluminaria`, `critical`, `infinity` table supports `enabled`, exact-decimal text `key_price` (up to two decimal places), `cooldown_seconds` (0–86400), `default_weight` (1–1000000), and at most ten rewards. Reward probability is weight divided by total weight: 100 and 300 mean 25% and 75%. / Cada nivel admite esas claves y hasta diez premios; la probabilidad es peso dividido por suma de pesos.

Rewards preserve item NBT and optional ForgeCaps. Use the hand-item editor for modded items. Do not replace real tables with examples. Historical `zonecrates-common.toml` and `crates/tiers_y_premios.toml` remain preserved but do not control beta4. / Los premios conservan NBT y ForgeCaps opcional. Usa el editor desde la mano; no sustituyas tablas reales por ejemplos. Los archivos históricos se conservan pero no controlan beta4.

[Current release / Entrega actual](RELEASE-2026-11-06.md) · [README](README.md).
