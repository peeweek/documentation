# Game Save Manager

The Game Save Manager is a [Manager](managers.md)  that enables saving and loading data to disk for your game. It relies on a **System Save** and **One or many User Saves** to store data.

You can perform **Logic** or **Actions** related to the Game Save Manager, for instance for [counters](counters.md) or [globals](globals.md).

## Locations

The Game Save manager can save to different kind of files:

* An unique System Save
* Many User Saves (up to 256)

The Save Files are stored into the `Application.persistantDataPath` folder. 

The data stored into these save files consists into JSON Arrays.

## Accessing the Manager

The manager can be get after the game `Start()` message using the `Manager.Get<GameSaveManager>()`

