---
description: Modifies the Scope section of the config
---

# Scope Modifier

```yaml
  Scope_Modifier:
    Zoom_Amount: <DoubleModifier>
    Night_Vision: <true/false>
    Pumpkin_Overlay: <true/false>
    Zoom_Stacking: 
      - <DoubleModifier>
      - <DoubleModifier>
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
```

### Zoom\_Amount

Modifies the [Zoom\_Amount](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/scope#zoom\_amount "mention"), how far you zoom in when you scope. This can be used to zoom in further.&#x20;

### Night\_Vision

Modifies the [Night\_Vision](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/scope#night\_vision "mention") of the scope. Use `true` to force enable night vision. Use `false` to force disable night vision. This can be used to create night vision scopes.&#x20;

### Pumpkin\_Overlay

{% hint style="warning" %}
This requires [WeaponMechanicsCosmetics](https://www.spigotmc.org/resources/weaponmechanicscosmetics-guns-in-minecraft-1-12-2-1-20-4.104539/) to be installed in order to work.
{% endhint %}

Modifies the [Pumpkin\_Overlay](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/scope#pumpkin\_overlay "mention") of the scope. Use `true` to force enable pumpkin scope overlay. Use `false` to force disable pumpkin scope overlay.

### Zoom\_Stacking

Modifies the existing scope stacks. See [Zoom\_Stacking](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/scope#zoom\_stacking "mention") for more information.

### Add\_Mechanics

{% hint style="info" %}
This will add additional [Mechanics](https://app.gitbook.com/o/MgHAZkcfIhs3YcmBjk2r/s/hz7yMxlL81NxAT44nraH/ "mention") to the current mechanics. To replace all current mechanics, change the config key to `Replace_Mechanics`.&#x20;
{% endhint %}

Modifies the current mechanics applied whenever a player scopes.&#x20;
