# ZoneCrates 2.0.6 — configuración / configuration

## Español

### TOML y datos

| Ruta o dato | Función comprobada en el código |
|---|---|
| `config/zonecrates-common.toml` | Forge genera `[general]` con `maxRewardsPerTier=10`, `maxWallet=1000000` y `keepWalletOnDeath=true`. **En 2.0.6 ninguno de estos tres valores es consultado por el código activo.** Cambiarlos no modifica el límite de premios, el saldo máximo ni la conservación de billetera al morir. |
| `config/ZONEMODS/zonecrates/crates/tiers_y_premios.toml` | Exportación legible que el mod **reescribe** al modificar niveles o premios. No es entrada de configuración; editarla no cambia las cajas y el siguiente guardado puede reemplazar los cambios. |
| Datos guardados del mundo (`zonecrates`) | Fuente efectiva de niveles, esperas, pesos y premios. Se cambia con comandos o editor del juego y se debe respaldar antes de actualizar. |
| Datos persistentes del jugador (`zonecrates_wallet`) | Saldo y llaves. El límite efectivo del saldo proviene del código `CrateWallet.MAX_CENTS`, no de `maxWallet`. La billetera completa se copia al morir en 2.0.6, independientemente de `keepWalletOnDeath`. |

El límite efectivo es **10 premios por nivel**. Los nombres de nivel son `EASY`, `MEDIUM`, `HARD`, `ESCARLATA`, `ILUMINARIA`, `CRITICAL`, `INFINITY`. Los comandos administrativos son:

```text
/zonecrates config lista
/zonecrates config tier <nivel> info
/zonecrates config tier <nivel> espera <segundos: 0..86400>
/zonecrates config tier <nivel> peso <valor: 1..1000000>
/zonecrates config tier <nivel> vaciar
/zonecrates config tier <nivel> agregar <mod:item> <cantidad: 1..64> <peso: 1..1000000>
/zonecrates reload
/zonascreate editar
/zonascreate coins dar <jugadores> <cantidad: 1..1000000>
/zonecreate
```

`/zonecrates reload` obtiene los datos guardados y sincroniza billeteras conectadas; **no importa el TOML de exportación**. `zonecrates.open` permite `/zonecreate` por defecto; `zonecrates.admin` controla comandos de administración. Los operadores de nivel 2 tienen acceso administrativo. ZoneRanks puede conceder ambos nodos si está instalado.

### Compatibilidad

Instala el JAR universal 2.0.6 en ambos lados, con ZoneCore `[2.0.0,)` en el servidor. ZoneClans 1.1.4 declara ZoneCrates `[2.0.1,3)` como dependencia obligatoria en servidor. Otros mods ZONE pueden llamar la API pública `CrateWallet`; prueba sus versiones exactas antes de actualizar un mundo persistente.

## English

Forge creates `config/zonecrates-common.toml` with `maxRewardsPerTier`, `maxWallet`, and `keepWalletOnDeath`. **None of these three values is read by active 2.0.6 code.** The actual reward limit is 10 per tier, the wallet ceiling is enforced by `CrateWallet.MAX_CENTS`, and the wallet is copied on death regardless of the TOML value. Do not rely on these keys for server policy.

`config/ZONEMODS/zonecrates/crates/tiers_y_premios.toml` is a readable **output** rewritten after tier changes, not an editable input. Saved world data is the authoritative reward and cooldown store; player persistent data contains balances and keys. Use the admin commands shown above to change tiers. `/zonecrates reload` syncs connected wallets but does not import the output TOML. Back up world and player data before updates.

The universal 2.0.6 JAR belongs on both client and server. ZoneCore `[2.0.0,)` is required on the server. ZoneClans 1.1.4 requires ZoneCrates `[2.0.1,3)` on the server. `zonecrates.open` is allowed by default, `zonecrates.admin` needs operator level 2 or an assigned permission, and ZoneRanks can supply permission nodes when installed.

