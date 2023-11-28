# Attachment

Attachments are items you can addon or "attach" to your guns. These will modify the stats of your weapon to change the damage, ammo, recoil, etc.

```yaml
Attachment:
  Priority: <priority> 
  Maximum_Stack_Amount: <amount>
  Item: <ItemSerializer>
  Denying:
    Attachments:
      - REQUIRE <attachment>
      - DENY <attachment>
    Mechanics: <Mechanics>
  Attach_Mechanics: <Mechanics>
  Detach_Mechanics: <Mechanics>
  Modifiers: <Modifier>
  Per_Weapon_Modifiers:
    <WeaponTitle>: <Modifier>
    <etc>: <Modifier>
  Armor_Modifiers: <Armor Modifier>
  Per_Armor_Modifiers:
    <ArmorTitle>: <Armor Modifier>
    <etc>: <Armor Modifier>
```

#### Priority

Priority decides the "priority" or order of the attachment when the weapon has multiple attachments. Lower numbers mean the modifiers are applied earlier. Higher numbers mean the modifiers are applied later. This means that when using `Set_Mechanics` and `Set` modifiers, a higher `Priority` can overwrite the effects of other attachments. You can use negative numbers if you would like.

<details>

<summary><strong>More information if you are confused...</strong></summary>

Let's say you have two attachments:

```yaml
# This is the low-priority attachment since 5 < 10
My_First_Attachment:
  Priority: 5
  Item:
    Type: IRON_NUGGET
    Name: "<yellow>My First Attachment"
  Modifiers:
    Damage_Modifier: 
      Damage: ADD 2.5  # adds 2.5 damage to the base amount

# This is the high-priority attachment since 10 > 5
My_Second_Attachment:
  Priority: 10
  Item:
    Type: IRON_NUGGET
    Name: "<yellow>My First Attachment"
  Modifiers:
    Damage_Modifier: 
      Damage: SET 5.2  # replaces the existing damage with 5.2 damage
```

If your weapon has both `My_First_Attachment` _and_ `My_Second_Attachment`, the damage effects of `My_First_Attachment` are removed since `My_Second_Attachment` has a higher priority.

</details>

#### Maximum\_Stack\_Amount

This number decides how many copies of this attachment can be on the same weapon. Defaults to `1`.

#### Item

This is the item that the attachment appears as in the game. You will drag and drop this item onto your weapon to view the changes. Uses the [item serializer](https://github.com/WeaponMechanics/MechanicsMain/wiki/General#item-serializer).

#### Denying

This section allows you to prevent specific attachments from being used together. It also allows for having another attachment REQUIRED before using this attachment.

* `Attachments`
  * Use `REQUIRE` to require an attachment
  * Use `DENY` to prevent an attachment
* `Mechanics`
  * The [Mechanics](https://github.com/WeaponMechanics/MechanicsMain/wiki/Mechanics) to play when an attachment is denied.

#### Attach\_Mechanics

The [Mechanics](https://github.com/WeaponMechanics/MechanicsMain/wiki/Mechanics) to play when the attachment is added to a weapon.

**`Detach_Mechanics`**

The [Mechanics](https://github.com/WeaponMechanics/MechanicsMain/wiki/Mechanics) to play when the attachment is removed from a weapon.

#### Modifiers

The modifiers that change the weapon's damage, recoil, ammo, etc. If you want to have different modifiers per weapon, you can use `Per_Weapon_Modifiers`. Here is an example:

```yaml
My_Cool_Attachment:
  Item:
    Type: DIAMOND
    Name: "<#00ffff>My Cool Attachment"
  Modifiers:
    Damage_Modifier:
      Damage: ADD 0.5
  Per_Weapon_Modifiers:
    AK-47:
      Damage_Modifiers:
        Damage: ADD 1.5
```

In this example, the AK-47 weapon will deal 1.5 more damage instead of just 0.5 more.

#### Armor\_Modifiers

If you want this attachment to modify armor (It only works for \*armor attachments\*; weapon attachments cannot modify the armor). If you want different modifiers per piece of armor, you can use `Per_Armor_Modifiers` (See above for example using weapons instead of armors).&#x20;
