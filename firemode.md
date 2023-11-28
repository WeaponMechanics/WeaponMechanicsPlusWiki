# Firemode

Firemodes are similar to the selective fire feature from WeaponMechanics, but instead of switching between semi/full auto/burst, this allows you to **COMPLETELY SWITCH** the held weapon on a trigger. Unfortunately, this means you have to set up 2 (or more) completely separate weapons. Possible use cases:

1. Switching between spells on a magic wand
2. Using multiple grenade types in 1 ammo (Gas grenade, highexplosive, etc.)
3. Customizing recoil/damage/whatever per full-auto, burst, and semi-auto

> **Note**: You will have to create a "list" of weapons, where each weapon "points" towards to the next weapon in the fire\_mode. for programmers, this is a [circularly linked list](https://www.geeksforgeeks.org/circular-linked-list/). For non-developers, please refer to the example below before asking for support in discord.

```yaml
    Fire_Mode:
      Trigger: <Trigger>
      Mechanics: <Mechanics>
      Order:
        - "<weapon-title> <uses different ammo> <attachment>" 
```

## Trigger

The [Trigger](http://127.0.0.1:5000/s/nwFaVZ2SN7YPdxsP5G6f/trigger "mention") to cause the firemode switch. I recommend using `SWAP_HANDS`, as it is usually intuitive for players.

## Mechanics

The [#mechanics](firemode.md#mechanics "mention") to play when switching to the next fire mode.

## Order

This defines the:

1. Order of firemodes (If you are using more then 2)
2. Required attachment to use a specific firemode
3. A unique string defining which ammo that firemode uses

The format is `<weapon-title> <ammo> <attachment>`.&#x20;

{% hint style="warning" %}
`<ammo>`, in this case, does not refer to an [Ammo](http://127.0.0.1:5000/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/reload/ammo "mention"), this is _completely separate_. Instead, this is simply a unique id. This unique id decides which firemodes can share ammo. For example, for an `m4a1`, `m4a1_burst`, and `m4a1_grenade`, you will want the `m4a1` and `m4a1_burst` to share the default ammo, and the `m4a1_grenade` to use its own unique ammo. See [#example-1](firemode.md#example-1 "mention")&#x20;
{% endhint %}

### Example 1

Let's look at an example for the `m4a1`. We will have the `m4a1` and `m4a1_burst` share the same ammo, but the `m4a1_grenade` will require an attachment and use its own ammo. For simplicity, these weapons will be missing the required [Info](http://127.0.0.1:5000/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/info "mention") and [Shoot](http://127.0.0.1:5000/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/shoot "mention") sections.&#x20;

When somebody is holding an `m4a1_burst` weapon, and they switch to the next weapon, WeaponMechanicsPlus will check to see if the weapon item has a `grenade_launcher` attached to it. If it does, **great;** we'll switch to `m4a1_grenade`. Otherwise, that fire mode gets skipped and we reset back to `m4a1`.&#x20;

```yaml
m4a1:
  # Make sure to add missing Info and Shoot sections
  Fire_Mode:
    Trigger:
      Main_Hand: SWAP_HANDS
      Off_Hand: SWAP_HANDS
    Order:
      - "m4a1"  # This always has to come first!!
      - "m4a1_burst"  
      - "m4a1_grenade any_unique_name grenade_launcher" # Uses a different ammo then the rest, and requires the grenade launcher attachment

m4a1_burst:
  # Make sure to add missing Info and Shoot sections
  # Do _NOT_ add another Fire_Mode section here. Each weapon can only be a part of 1.

m4a1_grenade:
  # Make sure to add missing Info and Shoot (and Explosion) sections 
```

### Example 2

Let's look at some example config for a magic spell. We will have 3 spells, `fireball`, `heal`, and `laser`. Again, for simplicity, these configs will be missing the required [Info](http://127.0.0.1:5000/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/info "mention") and [Shoot](http://127.0.0.1:5000/s/nwFaVZ2SN7YPdxsP5G6f/weapon-modules/shoot "mention") sections.&#x20;

```yaml
fireball:
  Fire_Mode:
    Trigger:
      Main_Hand: SWAP_HANDS
      Off_Hand: SWAP_HANDS
    Order:
      - "fireball"  # This always has to come first!!
      - "heal"
      - "laser"

heal:
 Info: # Add an info section
 Shoot: # Add a shoot section
 

laser:
  Info: # Add an info section
  Shoot: # Add a shoot section
```
