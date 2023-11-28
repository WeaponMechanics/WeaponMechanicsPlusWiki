# Placeholders

Placeholders are variables in strings in config. When you spawn an armor or weapon, all placeholders will be replaced with the correct value. For example, adding `<item_generic_armor>` into the lore of your armor will display a number showing how many armor bars it has.&#x20;

{% hint style="success" %}
WeaponMechanicsPlus is optional for placeholders. However, formatting options (`percentage`, `bar`, `emoji`) won't function without it. It also updates item display names and lore when players equip the weapon/armor, which is unavailable in the free plugin WeaponMechanics.&#x20;
{% endhint %}

> So if you can use placeholders without WeaponMechanicsPlus, why should we use WeaponMechanicsPlus?

1. Placeholders are updated automatically by WeaponMechanicsPlus. Without it, older guns will become outdated and use old values.
   1. For ArmorMechanics, this occurs whenever you equip armor.
   2. For WeaponMechanics, this occurs whenever you stop shooting, or equip the gun.
2. **Formats.** WeaponMechanicsPlus adds placeholders formats (You can modify them in the `your server -> plugins -> WeaponMechanics -> placeholders` folder).&#x20;

## Numeric Format

This is the most commonly used format, because most config values are numbers (Like damage, armor, reloading times, zoom amount, etc). Let's take a look at the `item_generic_max_health.yml` placeholder.

```yaml
Default_Mode: EMOJI
Prefix: "<gray>"
Suffix: "</gray>"
Null_Format: "0"

Colors:
  - "0.0 <green>"
  - "6.0 <gold>"

Min: 0.0
Max: 20.0

Bar:
  Left_Color: "" # blank since Colors handles this
  Right_Color: "<gray>"
  Left_Symbol: "|"
  Right_Symbol: "|"
  Symbol_Amount: 10

Emojis:
  - "2 ♥"
  - "1 +½"
```



## Enum Format

## List Format

## All Items

These placeholders are available for all items.

| Placeholder                     | Description                                               |
| ------------------------------- | --------------------------------------------------------- |
| `<item_generic_armor>`          | The amount of armor added by the armor attribute          |
| `<item_generic_max_health>`     | The amount of health added by the health attribute        |
| `<item_generic_movement_speed>` | The amount of speed added by the movement speed attribute |

## ArmorMechanics

These placeholders are exclusively available for Armor items from ArmorMechanics.&#x20;

| Placeholder | Description |
| ----------- | ----------- |
|             |             |
|             |             |
|             |             |

## WeaponMechanics

These placeholders are exclusively available for Weapon items from WeaponMechanics

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

