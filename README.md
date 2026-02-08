# OSC Avatar Manager for CVR

This is a fork of the OSC Avatar Manager so that it can more easily be used for CVR as well as fixing a few things.

This will match the defaults OSC parameters used to be the ones ChilloutVR needs. It does mean that if your avatar does not support the parameters, you are sending useless data, but I never had any issues with that.

Supported:

-  Quest Pro (eye + face)
-  Pico 4 Pro, HTC (eye only)
-  Project Babble
-  EyeTrackVR

## Setting up to use with ChilloutVR

A helper software is **NOT RECOMMENDED**, in order to handle OscQuery for us: [galister/VrcAdvert](https://github.com/galister/VrcAdvert).

If you use VRCAdvert with ChilloutVR, it might not work and no support will be provided regarding issues while using VRCAdvert.

Recommended start script:

```bash
#!/usr/bin/env bash
# If using WiVRn
./oscavmgr openxr

## If using ALVR
#./oscavmgr alvr

## If using Project Babble and/or EyeTrackVR
#./oscavmgr babble
```

Once OscAvMgr is started, it will print further instructions to the terminal.

## Using with Resonite (does not seem to work. Might fix one day)

Enable this mod: [galister/EyeTrackVRResonite](https://github.com/galister/EyeTrackVRResonite) (This is a fork that supports both Eye + Face)

With the mod enabled, simply start OscAvMgr.

A set of DynamicValueVariables will be created for you. Use them to drive your choice of blendshapes. (Network syncing is already handled for you).

If you are starting up Resonite after using VRC, you will need to restart OscAvMgr, or it will keep sending the set of parameters from your last VRC avatar!

**Pico 4 Pro Users**: Your eyes will be always closed. To fix this, remove the eyelid blendshapes from your EyeManager, and create a second EyeManager (not driven by OscAvMgr) to drive the eyelids.

## Building from Source

We recommend using `rustup`. If your compile is failing, try updating your toolchain using `rustup update stable`.

```bash
cargo build --release
```

Notes for ALVR: By default, OscAvMgr build for ALVR branch `v20`, which has the latest 20.x release.

If you need to use OscAvMgr with a different ALVR version, change the `branch` in `cargo.toml` and then run `cargo update` before building.

## Join the Linux VR Adventures community

-  [Discord](https://discord.gg/gHwJ2vwSWV)
-  [Matrix](https://matrix.to/#/#linux-vr-adventures:matrix.org)
-  [Wiki](https://lvra.gitlab.io/)
