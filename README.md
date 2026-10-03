# Dragonfly Room Reverb for MPC OS

An unofficial port of the [Dragonfly Reverb](https://github.com/michaelwillis/dragonfly-reverb) Room plugin (3.2.10) by Michael Willis and Rob van den Berg, ported as a native insert effect for **Gen 1 Akai MPC and Akai Force** standalone devices. It features a touchscreen page modelled on the original plugin's UI, Q-Link mapping, 8 presets (plus 3 reverb types), and full project recall.

This plugin recreates the intimate, natural sound of small to medium-sized acoustic spaces—ideal for vocals, acoustic instruments, and recording sessions that need realistic room ambience without sounding artificial.

![Dragonfly Room on MPC](https://raw.githubusercontent.com/gmorb/mpc-vst-dragonfly/main/docs/screenshots/room.png)

## What Is Room Reverb?

Room reverb simulates the acoustics of small to medium-sized enclosed spaces like recording studios, small halls, and residential rooms. Unlike plate reverb (which emulates metal resonance) or hall reverb (which simulates large concert spaces), room reverb produces short, natural-sounding reflections with distinct early echoes and a quick, smooth decay. The result is realistic spatial depth that enhances your mix without overwhelming the source.

Room reverb is one of the most commonly used reverb types in music production, especially suited for:

- **Acoustic instruments**: Guitars, piano, strings, and folk instruments
- **Vocals**: Adds natural room ambience for intimate vocal tracks
- **Drums**: Fills in room sound around the kit without masking transients
- **Electronic music**: Authenticates synthetic sources with organic acoustic character
- **Post-production**: Matches dialogue and sound effects to recorded room ambience

## Controls and Parameters

The Dragonfly Room interface mirrors the original desktop plugin with a fully functional touchscreen layout and Q-Link assignable parameters:

### Main Pages

- **Decay**: Controls the reverb tail length from short (0.5s) to medium (3s). Adjust for tight studio rooms to larger live spaces.
- **Pre-Delay**: Sets the time between the direct signal and the onset of reverb (0–100ms). Shorter pre-delay values create more intimate, glued-together sounds.
- **Damping**: Low-pass filters the reverb tail, simulating sound absorption by furniture and walls. Higher damping creates warmer, dead-room characteristics.
- **Diffusion**: Determines reflection density. Lower values create distinct, early echoes; higher values produce smoother, more uniform room ambience.
- **Size**: Adjusts the simulated room dimensions from intimate booths to medium halls.
- **Mix**: Blends wet/dry signal from 0% (fully dry) to 100% (fully wet).

### Q-Link Assignments

All parameters can be mapped to the MPC's Q-Link knobs for real-time performance control. Default assignments include Decay, Damping, Pre-Delay, Size, and Mix—adjustable per preset via the Q-Link menu.

### Reverb Types

Three distinct room tonal profiles are available, selectable from the preset menu:

1. **Type A (Small)**: Tight, intimate room with fast decay—ideal for vocals and acoustic instruments
2. **Type B (Medium)**: Balanced room with moderate decay and diffusion—versatile for general use
3. **Type C (Large)**: Extended room with slower decay and higher diffusion—suited for drums and ambient recordings

### Preset System

Eight user presets are provided, spanning:

- **Studio rooms**: Tight, dry, and controlled—perfect for vocal tracking
- **Live rooms**: Warm, spacious, with natural decay—ideal for band recordings
- **Acoustic rooms**: Bright, present, with moderate diffusion—suited for guitar and piano
- **Ambient rooms**: Larger decay, smoother tails—great for atmospheric textures

Custom presets can be saved and recalled across sessions. Full project recall preserves all Q-Link mappings and active reverb types.

## Install

Two ways, from the same [Releases](../../releases). Use one per device (see [docs/CATALOG.md](docs/CATALOG.md)).

**From the [MPC OS Plugin Catalog](https://sd88me.github.io/mpc-vst-plugins/)**: download `<Name>-<version>-mpc-armv7.zip` with an `install.sh`; the zip's `INSTALL.md` has the steps.

**Force VST plugins distribution**: download `Dragonfly-Reverb-for-MPC-OS-<version>.zip`. It follows the Force VST plugins distribution layout ([docs/DISTRIBUTION.md](docs/DISTRIBUTION.md)): one self-contained folder per plugin.

Requires a Gen 1 Akai Force or MPC with SSH access (modded firmware such as MockbaMod) and the distribution's `Synths` folder with `vstscanner.sh`. The steps are written for the **Akai Force with MockbaMod**, which mounts its memory card at `/media/662522`:

1. Copy the `Dragonfly - VST - Room` folder into `/media/662522/Synths` (next to `vstscanner.sh`).
2. On the device: `sh /media/662522/Synths/vstscanner.sh` (afterwards just `vstscanner`). MPC restarts; the plugin is under VST, manufacturer "Dragonfly".

Other custom firmware (for example Hakai), or no `662522` card: put the folder in a `Synths` folder on any drive under `/media` (e.g. `/media/az01-internal/Synths`), find MPC's settings file (`find / -name MPC.settings`), and run `sh <that Synths folder>/vstscanner.sh <settings path>`. The release's README has the full steps, updating from 1.1.x, and troubleshooting.

## Screenshots

| Room |

![Dragonfly Room on MPC](https://raw.githubusercontent.com/gmorb/mpc-vst-dragonfly/main/docs/screenshots/room.png)

## Notes

This is an independent port maintained for the MPC OS community. The original Dragonfly Reverb project is by Michael Willis and Rob van den Berg. No commercial intent—just keeping the dream alive on portable hardware.
