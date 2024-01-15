---
description: Modifies the explosion of a weapon
---

# Explosion Modifier

```yaml
  Explosion_Modifier:  
    Override_Explosion: <Explosion>  # completely override explosion
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
```

### Override\_Explosion

Completely overrides the [Explosion](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/explosion "mention") of the weapon.&#x20;

### Add\_Mechanics

{% hint style="info" %}
This will add additional [Mechanics](https://app.gitbook.com/o/MgHAZkcfIhs3YcmBjk2r/s/hz7yMxlL81NxAT44nraH/ "mention") to the current mechanics. To replace all current mechanics, change the config key to `Replace_Mechanics`.&#x20;
{% endhint %}

Modifies the current mechanics applied when the explosion triggers.
