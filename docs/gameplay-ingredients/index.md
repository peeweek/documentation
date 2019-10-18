# Welcome to Gameplay Ingredients

Gameplay Ingredients is a set of **Runtime** and **Editor** tools for Unity Games : A collection of scripts that ease simple tasks while making games and prototypes.

GItHub repository is here : [https://github.com/peeweek/net.peeweek.gameplay-ingredients](https://github.com/peeweek/net.peeweek.gameplay-ingredients)

#### Runtime Tools

* [Events, Logic and Actions](events-logic-actions.md) : Atomic Components to perform Actions based on logic and events.
* [Managers](managers.md) : Game Singletons that take care of low level game logic.
* [Rigs](rigs.md) : Components that animate, bind and connect objects together 
* [State Machines](state-machines.md) Abstraction that perform simple state behaviors.
* [Factories](factories.md) : Components that create objects based on blueprint and manage their life. 
* [Timers](timers.md) : Time-based component that keep track of time.
* [Global Variables](globals.md) : A Blackboard of values to read, write and get logic from.
* [interactive](interactive.md) : Interaction system for your characters
* [Gameplay Ingredients Settings](settings.md) : Configuration asset of the project.

#### Editor Tools

* [Welcome Screen](welcome-screen.md) : Window that provides tips, and initial setup for your project.
* [Play From Here](play-from-here.md)  : Play from your current Scene View location
* [Hierarchy Hints](hierarchy-hints.md) : Advanced Hierarchy View with more info.
* [Link Game View](link-game-view.md) : Sets the Game view to the same point of view as Scene View
* [Scene Point of Views](scene-pov.md) : Navigate Pre-recorded point of views in your levels.
* [Scene Setups](scene-setups.md) : Open Multiple Scenes at once in editor.
* [New Scene from Template](new-scene-from-template.md) : Create new scenes based on existing ones.
* [Find and Replace](find-and-replace.md) : A Tool to search game objects and replace them by prefabs.
* [Callable Tree Explorer](callable-tree-explorer.md) : Keep track of all your Events, Logic and Actions
* [Discover](discover.md) : Navigate and Document your project using a Browser.
* [Other Tools](editor-other.md)  

## Requirements

* Unity 2018.3 / 2019.1 / 2019.2
* Package Manager UI

## How to install

You can use a manual, local package installation if you need to alter the code locally or automate the fetch of the repository by using a git address directly. The latter option shall download and manage automatically the repository, with the drawback of being read-only.

### Manual Version

- Clone repository somewhere of your liking
- In your project, open the `Window/Package Manager` window and use the + button to select the `Add Package from Disk...` option.
- Navigate to your repository folder and select the `package.json` file
- The repository shall be added

### Git reference version

- With unity closed, edit the `Packages/manifest.json` with a text editor
- append the line `    "net.peeweek.gameplay-ingredients": "https://github.com/peeweek/net.peeweek.gameplay-ingredients.git#2018.3.0",` under `dependencies`

You can check that the package was imported by looking at the project window, under Packages/ Hierarchy, there should be a `Gameplay Ingredients` hierarchy

### Version / Tag Compatibility

Gameplay Ingredients comes with the following compatibility:

* **Unity 2018.3 / 2018.4 :** choose the tag `2018.3.0`
* **Unity 2019.1 / 2019.2 :** choose the tag `2019.1.2` 

* **Unity 2019.3** : Not officially supported ATM