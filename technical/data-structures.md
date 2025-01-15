# Data structures

## Bigfile contents

Each **Streets of Rage 4** (SOR4) *bigfile* is a massive concatenation of *data chunks*. Bigfiles for different versions of the game are structurally different. This is the reason why *bigfiles* from one version of the game will crash when you attempt to use it with another.

## Data chunk

Each of these represents a huge collection of configurations for various **data types**. They are read by SOR4 on load, and control a lot of aspects of the game.

Interesting ones include

* MetaGameConfig
* Localization
* Character
* AnimatedSprite
* Sprite
* Pickup
* Level
* Decor
* SurvivalConfig

See [here](#data-type-structures) for details.

### Terminology

The data structures within each data chunk is extremely complex. Here are some leyman terminologies to attempt to mask it.

* **Group**: each *data chunk* will unpack into many configuration **groups** (that can be nested very deep), and also *fields*
* **Fields** are configurable elements that may be at data level, or within a *group*.
* **Collection**: these are a special group that contains only fields with duplicate *identifiers* (ID). For example, stage sections (has an ID of `*.1`).
  ![Collection section](../assets/images/technical/collection-section.png)
* **Identifiers**: are *Pandora's box's* means of differentiating the meanings of the absolute mess of configurations within each data chunk.
* **Group list**: an array of *groups*. When you see a group, you can expect it's always going to be within a group list. In the image above, the folder `Sections (1)` is a *group list*, while the folder `1 (3)` is a section group/collection. Unfortunately, this is necessary complexity to visualize the data within the bigfile, to ensure similar configuration groups don't get muddled with one another.

## Data type structures

This section is intended to provide more detailed breakdowns on the data structures of various data types, with focus on the more interesting ones.

![Under construction](../assets/images/under_construction_wip.png)

## Authors note

This section is very technical in nature, and will be gradually expanded at my leisure when I have time to do so.