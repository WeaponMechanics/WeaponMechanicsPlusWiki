---
description: Modifies the damage config of a weapon
---

# Damage Modifier

```yaml
  Damage_Modifier:
    Base_Damage: <DoubleModifier>
    Base_Explosion_Damage: <DoubleModifier>
    Fire_Ticks: <IntModifier>
    Armor_Damage: <IntModifier>
    Damage_Dropoff:  
      - <distance> <damage>
    Add_Damage_Modifier: <DamageModifier>  # or use Replace_Damage_Modifier
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
    Add_Kill_Mechanics: <Mechanics>  # or use Replace_Kill_Mechanics
    Backstab:
      Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
    Critical_Hit:
      Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
    Head:
      Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
    Body:
      Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
    Arms:
      Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
    Legs:
      Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
    Feet:
      Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
```

### Base\_Damage

Modifies the [Base\_Damage](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/damage#base\_damage "mention") of the weapon, the damage before any damage modifiers are added.

### Base\_Explosion\_Damage

Modifies the [Base\_Explosion\_Damage](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/damage#base\_explosion\_damage "mention") of the weapon, the damage of the explosion before any exposure is taken into account.&#x20;

### Fire\_Ticks

Modifies the [Fire\_Ticks](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/damage#fire\_ticks "mention") of the weapon, the number of ticks that the victim should be on fire. Remember that the time is measured in ticks, and 20 ticks is 1 second.&#x20;

### Armor\_Damage

Modifies the [Armor\_Damage](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/damage#armor\_damage "mention") of the weapon, or the durability damage dealt to the piece of armor that is hit by the bullet. If you are making armor piercing bullets, you can use this damage to increase the damage specifically dealt to the armor.

### Add\_Damage\_Modifier

{% hint style="info" %}
This will add an additional damage modifier to the existing modifier(s). To replace all current modifiers, change the config key to `Replace_Damage_Modifier`.&#x20;
{% endhint %}

This adds a WeaponMechanics' [Damage Modifiers](https://app.gitbook.com/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/damage/damage-modifiers "mention"). This can be used to multiply the damage based on conditions, like the armor worn, entity type hit, entity speed/movement, etc. In practice, this can be used to make armor piercing rounds:

<details>

<summary>Armor Piercing Rounds Example</summary>

```yaml
  Damage_Modifier:
    Replace_Damage_Modifier:
      Min: 20%   
      Max: 300% 
      Per_Armor_Point: 0% # Makes armor make 0% difference in damage

      # Modifiers for where the bullet hits the body
      Head: +50%

      # Add your other options here!
```

</details>

### Add\_Mechanics

{% hint style="info" %}
This will add additional [Mechanics](https://app.gitbook.com/o/MgHAZkcfIhs3YcmBjk2r/s/hz7yMxlL81NxAT44nraH/ "mention") to the current mechanics. To replace all current mechanics, change the config key to `Replace_Mechanics`.&#x20;
{% endhint %}

Modifies the current mechanics applied whenever an entity is damaged by a weapon. In practice, this can be used to bleeding rounds, freezing rounds, levitating rounds, etc.

<details>

<summary>Bleeding Rounds Example</summary>

```yaml
  Damage_Modifier:
    # This adds a "bootlegged" bleeding effect by damaging the entity every
    # few seconds. You can add particles effects using the Particle{} mechanic
    Add_Mechanics:
     - "Damage{damage=1, repeatAmount=3, repeatInterval=40, delayBeforePlay=20} @Target{}"
```

</details>

### Add\_Kill\_Mechanics

{% hint style="info" %}
This add additional [Mechanics](https://app.gitbook.com/o/MgHAZkcfIhs3YcmBjk2r/s/hz7yMxlL81NxAT44nraH/ "mention") to the current mechanics. To replace all current mechanics, change the config key to `Replace_Kill_Mechanics`.
{% endhint %}

Modifies the current mechanics applied whenever an entity is killed by a weapon.&#x20;

### Backstab

* `Add_Mechanics` -> adds to the current backstab mechanics
* `Replace_Mechanics` -> replaces the current backstab mechanics

### Critical\_Hit

* `Add_Mechanics` -> adds to the current critical hit mechanics
* `Replace_Mechanics` -> replaces the current critical hit mechanics

### Head

* `Add_Mechanics` -> adds to the current head shot mechanics
* `Replace_Mechanics` -> replaces the current head shot mechanics

### Body

* `Add_Mechanics` -> adds to the current body shot mechanics
* `Replace_Mechanics` -> replaces the current body shot mechanics

### Arms

* `Add_Mechanics` -> adds to the current arm shot mechanics
* `Replace_Mechanics` -> replaces the current arm shot mechanics

### Legs

* `Add_Mechanics` -> adds to the current leg shot mechanics
* `Replace_Mechanics` -> replaces the current leg shot mechanics

### Feet

* `Add_Mechanics` -> adds to the current foot shot mechanics
* `Replace_Mechanics` -> replaces the current foot shot mechanics
