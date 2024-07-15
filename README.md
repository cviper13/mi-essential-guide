# Mi Essential Scooter Modding Guide

<p align="center">
  Join the community!
  <br>
  <br>
  <a href="https://discord.gg/https://discord.gg/scooterhacking" target="_blank" title="Join our community!">
    <img src="https://dcbadge.limes.pink/api/server/https://discord.gg/scooterhacking"/>
  </a>
</p>

## Table of Contents

- [General Information](#general-information)
  - [Firmware](#firmware)
  - [Battery](#battery)
  - [Motor](#motor)
  - [Tires](#tires)
- [Modding](#modding)
  - [Firmware](#firmware-1)
    - [Configuration](#configuration)
  - [Battery](#battery-1)
  - [Motor](#motor-1)
  - [Tires](#tires-1)

## General Information

The Xiaomi Mi Scooter Essential was released in 2020 alongside the 1S and PRO2 models. Despite being the most affordable option, it offers the lowest range and speed compared to other models, including the older Xiaomi M365.

### Firmware

The Essential's firmware restricts speeds as follows:

- 5 km/h in ECO/WALKING mode
- 15 km/h in DRIVE mode
- 20 km/h in SPORT mode

### Battery

The Essential features a 10S2P battery running at 36V with 250W nominal power (peak 500W). With the original firmware, it provides approximately 8 to 12 km of range, although Xiaomi claims up to 20 km under ideal conditions.

### Motor

> Work in Progress (WIP).

### Tires

The stock tires included with the Essential are 8.5-inch Air Pneumatic tires.

Recommended tire pressure settings based on load:

| Load      | Pressure (psi) |
|-----------|----------------|
| 50-70 kg  | 45-50          |
| 70-90 kg  | 45-55          |
| 90-100 kg | 50-60          |
| 100 kg+   | 55-65          |

> ##### WARNING
>
> Please ensure to monitor tire pressure regularly if you use tubed tires. Operating with insufficient pressure may lead to damage of the inner tube.

> ##### WARNING
>
> Caution is advised for riders above 100 kg due to increased risk of puncture.

> ##### NOTE
> 
> Tires should be inflated to 50 psi when used under default conditions.

## Modding

### Firmware

Currently, the Essential supports SHFW (developed by the same team behind CFW), which can be installed using the ScooterHacking Utility (SHUT) available for Android devices. For scooters with DRV versions above 173, a DRV downgrade via SHUT or using an ST-LINK/V2 device for reprogramming with SHFW (see [Reflasher](https://www.scooterhacking.org/forum/viewtopic.php?t=676)) may be necessary.

#### Configuration

To optimize performance with SHFW:

1. Set DPC to 15A with full quadratic (1.0) settings.
   - Acceleration boost: 100%
   - Brake boost: 0-100% (adjust as needed)
   - Brake: 30A flat (0.0)

2. In the field weakening tab:
   - Enable "expert view."
   - Activate field weakening for SPORT mode.
   - Configuration: 15 km/h start speed, 0A, 1500mAh.

3. Under Motor Settings, select 20 or 24 kHz.

> ##### NOTE
> 
> These settings are recommended by [@lekrsu](https://github.com/lekrsu). Refer to the [SHFW Walkthrough](https://github.com/lekrsu/shfw-walkthrough) for detailed usage instructions.

> ##### Danger
> 
> Drawing current at or near the rated limits may increase the temperature of the battery pack. It is advisable to monitor the temperature.

### Battery

Despite its compact size, the Essential can accommodate up to a 10S4P battery with relocation of the ESC using power tools, or a 10S3P battery without chassis modification.

### Motor

> Work in Progress (WIP).

### Tires

Each type of tire offers distinct advantages and disadvantages:

#### Tubeless

```diff
+ Fewer flat tires
+ Economical
+ Enhanced performance and grip
- Difficult installation
```

#### Tubed

```diff
+ Included with purchase
+ Suitable for speeds up to 50 km/h
- Not suitable for off-road use
- Slippery at high speeds
- Expensive
```

#### Solid

```diff
+ No risk of flat tyres
+ Available in various colors
- Difficult installation
- Not ideal for high speeds
- Causes damage to bearings and the folding mechanism
- Causes discomfort to the rider from shaking and vibrations
```
