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

- [Table of Contents](#table-of-contents)
- [General Information](#general-information)
  * [Firmware](#firmware)
  * [Battery](#battery)
  * [Motor](#motor)
  * [Tires](#tires)
- [Modding](#modding)
  * [Firmware](#firmware-1)
    + [Configuration](#configuration)
  * [Battery](#battery-1)
  * [Motor](#motor-1)
    + [Motor Frequency](#motor-frequency)
  * [Tires](#tires-1)
    + [Tubeless](#tubeless)
    + [Tubed](#tubed)
    + [Solid](#solid)
- [Accessories](#accessories)
- [How to Contribute](#how-to-contribute)
  * [TL;DR](#tldr)

## General Information

The Xiaomi Mi Scooter Essential was released in 2020 alongside the 1S and PRO2 models. Despite being the most affordable option, it offers the lowest range and speed compared to other models, including the older Xiaomi M365.

### Firmware

The Essential's stock firmware restricts speeds as follows:

- 5 km/h in ECO/WALKING mode
- 15 km/h in DRIVE mode
- 20 km/h in SPORT mode

### Battery

The Essential features a 10S2P battery running at 36V. With the original firmware, it provides approximately 8 to 12 km of range, although Xiaomi claims up to 20 km under ideal conditions.

### Motor

> Work in Progress (WIP).

### Tires

The stock tires included with the Essential are 8.5-inch Air Pneumatic tires.

Recommended tire pressure settings based on load:

| Load      | Pressure (psi) |
|-----------|----------------|
| 50-70 kg  | 40-50          |
| 70-90 kg  | 45-50          |
| 90+ kg    | 50             |

> [!WARNING]
> Please ensure to monitor tire pressure regularly if you use tubed tires. Operating with insufficient pressure may lead to damage of the inner tube.

> [!WARNING]
> Caution is advised for riders above 100 kg due to increased risk of puncture.

> [!NOTE]
> Tires should be inflated to 50 psi when used under default conditions.

## Modding

### Firmware

The Essential currently supports SHFW, developed by the team behind CFW. Installation of SHFW is facilitated through the ScooterHacking Utility (SHUT), available for Android devices. For scooters equipped with BLE versions 1.5.5 and above, reprogramming with SHFW may necessitate the use of an ST-LINK/V2 device (refer to the [Reflasher](https://www.scooterhacking.org/forum/viewtopic.php?t=676) for detailed instructions). In cases where the firmware version of the DRV is incompatible with flashing, users are advised to attempt a DRV downgrade using the Scooter Hacking Utility (SHUT).

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

> [!NOTE] 
> These settings are recommended by [@lekrsu](https://github.com/lekrsu). Refer to the [SHFW Walkthrough](https://github.com/lekrsu/shfw-walkthrough) for detailed usage instructions.

> [!CAUTION] 
> Drawing current at or near the rated limits may increase the temperature of the battery pack. It is advisable to monitor the temperature.



### Battery

Despite its compact size, the Essential can accommodate up to a 10S4P battery with relocation of the ESC using power tools, or a 10S3P battery without chassis modification.

### Motor

> Work in Progress (WIP).

#### Motor Frequency

When you **increase** the PWM frequency:

- **Noise**: The motor's operation becomes quieter as the frequency moves out of the audible range, reducing or eliminating the high-pitched whine.
  
- **Motor Efficiency and Heat**: At a higher frequency, the current ripple in the motor windings is reduced, leading to smoother current flow and potentially lower motor heating. However, this comes at the cost of increased switching losses in the motor controller due to more frequent switching, which can generate additional heat in the controller.

- **Smoothness of Control**: Increasing the PWM frequency generally improves the smoothness of the motor's response to throttle input, particularly noticeable at lower speeds, where the motor operates more smoothly without the "cogging" effect that can occur with lower frequencies.

When you **decrease** the PWM frequency:

- **Noise**: The motor may produce a noticeable high-pitched whine, as the frequency remains within the range of human hearing, particularly at lower speeds.

- **Motor Efficiency and Heat**: A lower frequency can lead to better efficiency in the motor controller, as the transistors switch less frequently, reducing switching losses. However, the longer duration of each pulse can cause more heat buildup in the motor windings due to less smooth current flow.

- **Smoothness of Control**: With a lower PWM frequency, throttle response might feel less smooth, with a greater chance of motor "cogging," especially when starting or running at low RPMs.

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

## Accessories

Given the extensive list of accessories available, they have been detailed on a separate page. Please refer to [this link](https://github.com/cviper13/mi-essential-guide/blob/main/ACCESSORIES.md) to view the full list.

## How to Contribute

We welcome contributions from the community! To contribute to this project, follow these steps:

1. **Fork the Repository**
   - Click on the "Fork" button on the top right corner of the repository page. This creates a copy of the repository under your GitHub account.

2. **Clone Your Fork**
   - Clone the repository to your local machine using Git. Replace `<your-username>` with your GitHub username:
     ```bash
     git clone https://github.com/<your-username>/mi-essential-guide.git
     cd mi-essential-guide
     ```

3. **Create a New Branch**
   - Create a new branch for your contribution. Replace `<branch-name>` with a descriptive name for your branch:
     ```bash
     git checkout -b <branch-name>
     ```

4. **Make Changes**
   - Make your desired changes to the project code or documentation on your local machine.

5. **Commit Your Changes**
   - Commit the changes to your branch:
     ```bash
     git add .
     git commit -m "Clear and descriptive commit message explaining your changes"
     ```

6. **Push Changes**
   - Push your changes to your forked repository on GitHub:
     ```bash
     git push origin <branch-name>
     ```

7. **Open a Pull Request**
   - Go to the original repository on GitHub and you should see a "Compare & pull request" button for your new branch.
   - Click on the button to open a pull request (PR) against the 'main' branch.
   - Provide a clear title and description for your PR outlining what you have done.

8. **Discuss and Iterate**
   - Participate in the discussion on your PR if any feedback or changes are requested.
   - Make changes to your branch as necessary by adding new commits. Repeat steps 5-7 until your PR is merged.

### TL;DR

- Fork the repository, clone it locally, and create a new branch.
- Make your changes, commit them, and push to your fork.
- Open a pull request (PR) against the `main` branch in the original repository.
