# Data structures

## Bigfile contents

Each **Streets of Rage 4** (SOR4) *bigfile* is a massive concatenation of *data chunks*. Bigfiles for different versions of the game are structurally different. This is the reason why *bigfiles* from one version of the game will crash when you attempt to use it with another.

## Data chunk

Each of these represents a huge collection of configurations for various **data types**. They are read by *SOR4* and *Absolum* on load, and control a lot of aspects of the game.

Interesting ones that are mostly in the supported games include:

|Data type|Description|
|---|---|
|MetaGameConfig|General configurations for the game|
|Localization|All language configurations|
|Character|Used to configure character behaviors, such as moves|
|AnimatedSprite|Used to configure animations for character moves|
|Sprite|References to textures to be displayed in game|
|Projectile|Configurations for projectiles in game|
|Pickup|Configurations for various types of pickups|
|BtNode|Behavior tree, controller for AI behaviors (SOR4 only)|
|Level|Orchestrates events that happen in stages|
|Decor|Controls the decorative layout of stages|
|SurvivalConfig|Settings to manipulate survival mode (SOR4 only)|

Interesting *Absolum* only data types include:

|Data type|Description|
|---|---|
|AdventureKey|List of keys that are used to track permanent and per-run meta-progression|
|AdventureRun|Configurations for many of the random events in the game|
|AllShop|Configurations for various shops in the game|
|StatsConfig|Defines custom stats that can be applied to any character in the game|
|Story|Configurations for all the story events and dialogues in the game|

See [here](#data-type-structures) for links to the currently available data type pages.

### Terminology

The *data structures* within each *data type* is extremely complex. The following terminology will be used to describe them.

* **Group**: each *data type* will unpack into many **field groups**. *Groups* can contain other nested *groups*. They will often also contain *fields*.
* **Fields** are configurable variables that may be owned by *data types* or *groups*.
* **Collection**: these are a special *group* that contains only *fields* with duplicate *identifiers* (ID). For example, stage sections (has an ID of `*.1`).
  ![Collection section](../assets/images/technical/collection-section.png)
* **Identifiers**: are *Pandora's box's* means of differentiating the meanings of the absolute mess of variables within each *data set*. They can have definitions configured to give them meaning.
* **Group list**: an array of *groups*. When you see a *group*, you can expect it's always going to be within a *group list*. In the image above, the folder `Sections (1)` is a *group list*, while the folder `1 (3)` is a section group/collection. Unfortunately, this is necessary complexity to visualize the data within the bigfile, to ensure similar *groups* don't get muddled with one another.

## Field types

Every *field* has a **type**. These are the various *field types* you can expect to work with in the *bigfile*. They can be found directly within data and field groups. Unused types are intentionally ommitted.

| Name      | Description |
|-----------|-------------|
| Varint    | Undefined Protobuf varint. May be `Boolean` or `Int` |
| Boolean   | True or False  |
| Int       | Signed integer |
| ScaledInt | Signed scaled integer = (Int / 65536) to get a floating point number |
| Enum      | Preset control options |
| Float32   | Floating point number |
| String    | Mostly descriptions or `WWise` audio/music references |
| Text      | Multi-line strings, used only for `Localization` data |
| Data      | Reference to other data in the `bigfile` |
| Texture   | Reference to a texture loaded by the [texture manager](../functional/project-information.md#texture-management-related) |

## Data type structures

This section contains links to overviews of the *data structures* of various *data types* (with focus on the more interesting ones). The overviews are intended to make it clearer how various *data types* and *groups* relate to one another.

![Under construction](../assets/images/under_construction_wip.png)

## Authors note

This section is very technical in nature, and will be gradually expanded at my leisure when I have time to do so.