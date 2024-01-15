---
description: All modifiers for your weapons
---

# Modifiers

Modifiers are used in [attachment.md](../attachment.md "mention") to modify the stats of the affected weapon. Arguments here take advantage of the DoubleModifier and the IntModifier. When using `Mechanics`, you can replace the config key with `Replace_Mechanics` to override all previous mechanics. The mechanics will be _added_ to the base list if you use `Mechanics`.

## DoubleModifier

We use the double modifier to modify the existing value _without_ replacing it. Uses the format `<Operation> <decimal>`. This is different than the `IntModifier` because it allows decimals.

Here are valid operations:

* `ADD` -> Adds the decimal to the **existing value**
* `MULTIPLY` -> Multiplies the **existing value** by the decimal
* `SET` -> Replaces the **existing value** with the decimal

## IntModifier

We use the double modifier to modify the existing value _without_ replacing it. Uses the format `<Operation> <integer>`. This differs from the `DoubleModifier` because it does not allow decimals.

Here are valid operations:

* `ADD` -> Adds the integer to the **existing value**
* `MULTIPLY` -> Multiplies the **existing value** by the integer
* `SET` -> Replaces the **existing value** with the integer

### Modifier

```yaml
  Modifier:
    Damage_Modifier: # See the Damage Modifier wiki
    Shoot_Modifier: # See the Shoot Modifier wiki
    Projectile_Modifier: # See the Projectile Modifier wiki
    Reload_Modifier: # See the Reload Modifier wiki
    Scope_Modifier: # See the Scope Modifier wiki
    Explosion_Modifier: # See the Explosion Modifier wiki
```
