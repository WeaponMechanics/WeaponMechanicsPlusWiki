---
description: Modifies the Reload section of the weapon config
---

# Reload Modifier

```yaml
  Reload_Modifier:
    Magazine_Size: <IntModifier>
    Ammo_Per_Reload: <IntModifier>
    Reload_Duration: <IntModifier>
    Shoot_Delay_After_Reload: <IntModifier>
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
```

### Magazine\_Size

{% hint style="danger" %}
This section should **always** be used alongside `Ammo_Per_Reload`.
{% endhint %}

Modifies the [Magazine\_Size](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/reload#magazine\_size "mention") of the weapon. This does not actually make it reload **more** ammunition into the gun. Instead, it just sets how much ammo **can** be loaded. This is important for deciding if the player can reload their currently held weapon.

### Ammo\_Per\_Reload

{% hint style="danger" %}
This section should **always** be used alongside `Magazine_Size`.
{% endhint %}

Modifies the [Ammo\_Per\_Reload](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/reload#ammo\_per\_reload "mention"), how much ammunition is loaded into the weapon.

### Reload\_Duration

Modifies the [Reload\_Duration](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/reload#reload\_duration "mention"), how much time, in ticks, it takes for the reload to complete.&#x20;

### Shoot\_Delay\_After\_Reload

Modifies the [Shoot\_Delay\_After\_Reload](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/reload#shoot\_delay\_after\_reload "mention"), the delay after reloading before you can shoot.&#x20;

### Add\_Mechanics

{% hint style="info" %}
This will add additional [Mechanics](https://app.gitbook.com/o/MgHAZkcfIhs3YcmBjk2r/s/hz7yMxlL81NxAT44nraH/ "mention") to the current mechanics. To replace all current mechanics, change the config key to `Replace_Mechanics`.&#x20;
{% endhint %}

Modifies the current mechanics applied whenever an entity reloads.
