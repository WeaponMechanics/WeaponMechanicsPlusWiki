---
description: Modifies the projectile config of a weapon
---

# Projectile Modifier

```yaml
  Projectile_Modifier:

    # ProjectileSettings modifiers
    Override_Projectile_Settings: <ProjectileSettings>
    Gravity: <DoubleModifier>
    Minimum_Speed: <DoubleModifier>
    Maximum_Speed: <DoubleModifier>
    Max_Alive_Ticks: <IntModifier>
    Drag:
      Base: <DoubleModifier>
      In_Water: <DoubleModifier>
      When_Raining_Or_Snowing: <DoubleModifier>
    
    # Sticky modifiers
    Override_Sticky: <Sticky>

    # Through modifiers
    Override_Through: <Through>
    Maximum_Through_Amount: <DoubleModifier>
    
    # Bouncy modifiers
    Override_Bouncy: <Bouncy>
    Maximum_Bounce_Amount: <IntModifier>
```

### Override\_Projectile\_Settings

{% hint style="warning" %}
In general, this feature should not be used as it is not very compatible with other attachments. Use with caution, or set this priority to be the first attachment.&#x20;
{% endhint %}

Completely overrides the projectile settings (See [Projectile](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile "mention")) of the shot projectile.&#x20;

### Gravity

Modifies the [Gravity](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile#gravity "mention") of the projectile, how fast it accelerates downwards over time.&#x20;

### Minimum\_Speed

Modifies the [Minimum](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile#minimum "mention") Speed of the projectile.

### Maximum\_Speed

Modifies the [Maximum](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile#maximum "mention") Speed of the projectile.

### Maximum\_Alive\_Ticks

Modifies the [Maximum\_Alive\_Ticks](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile#maximum\_alive\_ticks "mention") of the projectile. This can be used to make the projectile last for a shorter or longer amount of time. This can be used to create longer range laser weapon attachments, or similar.

### Drag

Modifies the [Drag](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile#drag "mention") constants of the projectile. Remember that a drag of `1.0` is actually no drag at all. A number like `0.98` will slow the projectile down a little bit over time.&#x20;

* `Base` -> When not in water, and not in the rain.
* `In_Water` -> When the projectile is traveling through water.
* `When_Raining_Or_Snowing` -> When it is raining.

<details>

<summary>Subtly Increase Drag Example</summary>

This example increases the drag of the projectile. This should be used for suppressors or other muzzle attachments.&#x20;

```yaml
    Projectile_Modifier:
      Drag:
        Base: MULTIPLY 0.98        
```

</details>

### Override\_Sticky

Completely overrides the current [Sticky](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile/sticky "mention") settings. This should probably only be used on explosive weapons.

### Override\_Through

Completely overrides the current [Through](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile/through "mention") settings.

### Maximum\_Through\_Amount

{% hint style="warning" %}
In order for this modifier to work, the weapon **must** already have a `Through` section configured, or an attachment with a lower [#priority](../attachment.md#priority "mention") must be attached to the weapon and use the [#override\_through](projectile-modifier.md#override\_through "mention") feature. Otherwise, this modifier will have no effect.&#x20;
{% endhint %}

Modifies the [Maximum\_Through\_Amount](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile/through#maximum\_through\_amount "mention") of the through settings. This can be used to create ammunition that pierces through more walls/entities.

### Override\_Bouncy

Completely overrides the current [Bouncy](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile/bouncy "mention") settings.&#x20;

### Maximum\_Bounce\_Amount

{% hint style="warning" %}
In order for this modifier to work, the weapon **must** already have a `Bouncy` section configured, or an attachment with a lower [#priority](../attachment.md#priority "mention") must be attached to the weapon and use the [#override\_bouncy](projectile-modifier.md#override\_bouncy "mention") feature. Otherwise, this modifier will have no effect.
{% endhint %}

Modifies the [Maximum\_Bounce\_Amount](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/projectile/bouncy#maximum\_bounce\_amount "mention") of the bouncy settings.
