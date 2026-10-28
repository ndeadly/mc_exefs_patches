# MC ExeFS Patches

A collection of [Mission Control](https://github.com/ndeadly/MissionControl) adjacent ExeFS patches for Nintendo Switch (inspired by https://github.com/misson20000/exefs_patches). These are essentially opt-in features that don't make sense to distribute as part of the [releases](https://github.com/ndeadly/MissionControl/releases) on the main Mission Control repository.


## Installation

You have two options for installing patches:

1) Clone the repository and copy the directories for the patches you want to `sdmc:/atmosphere/exefs_patches`
2) Download one or more of the zip files containing the patches you want from the Releases section, extract them to a location on your device, and copy the extracted `atmosphere` directory to the root of your SD card.

Patches are loaded on boot by atmosphere's loader reimplementation and will only take effect after the console has been rebooted.

> [!Note]
Patches are specific to title build ID and must be updated every time a new firmware update changes their affected titles


## Patch List

### Disable Remap Dialog

**Affected Titles:** qlaunch [10.0.0+]

Disables the warning dialog that pops up every time the console wakes to remind that button remapping is active.


### Force Docked Handheld

**Affected Titles:** am [1.0.0-13.1.0], omm [14.0.0+]

Forces handheld controls to remain active while the console is docked.


### Disable Set Player Led Zero

**Affected Titles:** hid [22.0.0+]

Firmware 22.0.0+ started sending an additional SetPlayerIndicator command to attached controllers upon initialisation with the argument set to 0. Some third party controllers don't handle this value correctly and will no longer connect to the console as a result. This patch skips the problematic command and allows the use of such controllers on firmware 22.0.0+ when a controller firmware update to resolve the issue is not available/possible.
