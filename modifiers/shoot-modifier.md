---
description: Modifies the shoot config of a weapon
---

# Shoot Modifier

```yaml
  Shoot_Modifier:
    Projectile_Amount: <IntModifier>
    Projectile_Speed: <DoubleModifier>
    Base_Spread: <DoubleModifier>
    Override_Spread: <Spread>
    Fully_Automatic_Shots_Per_Second: <IntModifier>
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
```

### Projectile\_Amount

Modifies the [Projectiles\_Per\_Shot](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/shoot#projectiles\_per\_shot "mention"), the number of projectiles launched for each shot. This is typically used for shotguns, to increase the amount of pellets/shrapnel.&#x20;

### Projectile\_Speed

Modifies the [Projectile\_Speed](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/shoot#projectile\_speed "mention"), the speed, in $$\frac{m}{s}$$, that the projectile should be launched at. You can use this on suppressor attachments to decrease the muzzle velocity of the launched projectile(s).

### Base\_Spread

Modifies the [Base\_Spread](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/shoot/spread#base\_spread "mention"), the random variations in bullet path. Increasing the spread will make the gun harder to use because bullets will fly more randomly.&#x20;

### Override\_Spread

{% hint style="warning" %}
In general, you should try to use the [#base\_spread](shoot-modifier.md#base\_spread "mention") feature instead of `Override_Spread`. This is to make it easier to configure multiple attachments that modify spread at the same time.&#x20;
{% endhint %}

Completely overrides the [Spread](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/shoot/spread "mention") of the weapon.

### Fully\_Automatic\_Shots\_Per\_Second

Modifies the [Fully\_Automatic\_Shots\_Per\_Second](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/shoot#fully\_automatic\_shots\_per\_second "mention") of the weapon. For non-automatic weapons (semi/burst weapons), the starting value will be 0.&#x20;

<details>

<summary>Allow Selective Fire Example</summary>

In this example, selective fire still works with burst and semi-auto weapons. This is because we use the `MULTIPLY` option, and $$0\times x=0$$, where $$x$$ can be any number. In this example, the full auto rate will be 50% higher then before.&#x20;

```yaml
    Shoot_Modifier:
      Fully_Automatic_Shots_Per_Second: MULTIPLY 1.50
```

</details>

<details>

<summary>Convert to Full Auto Example</summary>

In this example, selective fire will no longer work. This example will convert all weapons to fully automatic weapons.

```yaml
    Shoot_Modifier:
      Fully_Automatic_Shots_Per_Second: SET 6
```

</details>

### Add\_Mechanics

{% hint style="info" %}
This will add additional [Mechanics](https://app.gitbook.com/o/MgHAZkcfIhs3YcmBjk2r/s/hz7yMxlL81NxAT44nraH/ "mention") to the current mechanics. To replace all current mechanics, change the config key to `Replace_Mechanics`.&#x20;
{% endhint %}

Modifies the current mechanics applied whenever an entity shoots the weapon. In practice, this can be used to create suppressors, VALORANT styled skins (skins that modify sounds shoot sounds), make sounds louder, etc.

<details>

<summary>Suppressor Example</summary>

In this example, we replace the original mechanics (and thus, the original sound) with a suppressed sound with less volume.&#x20;

```yaml
    Shoot_Modifier:
      Replace_Mechanics:
        - "CustomSound{sound=shoot.m4a1.silenced.loud, volume=2, noise=0.1}"
```

</details>
