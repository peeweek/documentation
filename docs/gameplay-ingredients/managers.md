# Managers

Managers are Game-Wide utility Scripts that are meant to exist only once, such as Singletons. These are spawned automatically upon game startup, and lie into the **DontDestroyOnLoad** scene.

Many components of Gameplay Ingredients rely on these managers to perform general game tasks, such as loading levels, fading to black, accessing game saves,....

## Built-in Managers

Gameplay Ingredients come with the following built-in managers:

* **FullScreenFadeManager** : Manages Fading screen From/To Black
* **GameManager** : Manages Loading Game Levels, Main Menu, and Game Progression
* **[GameSaveManager](game-save-manager.md)** : Manages storing save data to disk
* **LevelStreamingManager**: Manages loading scenes and display Loading UI
* **ScreenshotManager**: Manages taking screenshots
* **UIEventManager**: Manages Focusing on UI
* **VirtualCameraManager** : Manages a single camera for your game.

## Manager Creation Logic

Whenever the game performs it `[RuntimeInitializeOnLoad]` (after the first frame's `OnEnable()` and before the first frame's `Start()`, the runtime code will try to load all managers (except those defined in the Excluded manager list of the [Gameplay Ingredients Settings Asset](settings.md)). In order to spawn an instance, the runtime will try to load a prefab in the **Resources** folder with the following priority (first found).

* Prefab that matches the name defined in the `[ManagerDefaultPrefab]` Attribute of the Manager C# Class.
* Prefab that matches the name defined in the `[ManagerDefaultPrefab]` Attribute of the Manager C# Class, prefixed by `Default_`.
  * If no prefab is found while the `[ManagerDefaultPrefab]` is defined, the creation will fail.
* If no `[ManagerDefaultPrefab]` is set : the system will create one game object with a default instance of the Manager Script.

> Managers should not reference each other during their `OnEnable()` methods, as the code that loads them is performed during the `[RuntimeInitializeOnLoad]`, it is advised to reference them during the `Start()` method instead.

## Exclude Managers

If you do not need a manager to be spawned, you can exclude it in the [Gameplay Ingredients Settings Asset](settings.md) . Please be aware that some managers rely on other managers and thus can start behaving incorrectly.

## Accessing Managers (C#)

Managers can be accessed using the following API:

* `bool Manager.Has<MyManager>()`: returns whether a manager of give type (`MyManager` in our example) is present
* `MyManager Manager.Get<MyManager>()`: returns an instance of the manager of the Given type (`MyManager` in our example). You can always check beforehand using the `Has<T>()` method. 

## Writing a Manager (C#)

If you need to create your own Managers, you can implement a class that derives from `GameplayIngredients.Manager`. A manager does not implement any abstract functions so it's rather straightforward to write.

You can implement the `[ManagerDefaultPrefab("MyManager")]` attribute if you want your manager to rely on a prefab for its configuration. This can be useful if your manager is bound to other game objects such as UI, AudioSources, etc.

#### Example

Here's an example of a simple Manager, that draws framerate to a UI Text in the Canvas.  As it relies on a UI.Text, it will need a Prefab to be completed.

```C#
using UnityEngine.UI;
using GameplayIngredients;

[ManagerDefaultPrefab("DrawFrameTimeManager")]
public class DrawFrameTimeManager : Manager
{
	public Text text;
	
	void Update()
	{
		if(text != null)
		{
			text.text = Time.deltaTime.ToString();
		}
	}
}
```