# Modifiers

Modifiers are used in [attachment.md](attachment.md "mention") to modify the stats of the affected weapon. Arguments here take advantage of the DoubleModifier and the IntModifier. When using `Mechanics`, you can replace the config key with `Replace_Mechanics` to override all previous mechanics. The mechanics will be _added_ to the base list if you use `Mechanics`.

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
  Damage_Modifier:
    Damage: <DoubleModifier>
    Explosion_Damage: <DoubleModifier>
    Fire_Ticks: <IntModifier>
    Armor_Damage: <IntModifier>
    Damage_Dropoff:  
      - distance damage
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

  Shoot_Modifier:
    Projectile_Amount: <IntModifier>
    Projectile_Speed: <DoubleModifier>
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics

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
    Maximum_Through_Amount: <IntModifier>
    
    # Bouncy modifiers
    Override_Bouncy: <Bouncy>
    Maximum_Bounce_Amount: <IntModifier>

  Reload_Modifier:
    Magazine_Size: <IntModifier>
    Ammo_Per_Reload: <IntModifier>
    Reload_Duration: <IntModifier>
    Shoot_Delay_After_Reload: <IntModifier>
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics

  Scope_Modifier:
    Zoom_Amount: <DoubleModifier>
    Night_Vision: <true/false>
    Zoom_Stacking: 
      - <DoubleModifier>
      - <DoubleModifie>r
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics

  Explosion_Modifier:
    Override_Explosion: <Explosion>  # completely override explosion
    Add_Mechanics: <Mechanics>  # or use Replace_Mechanics
```
