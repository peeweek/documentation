# Callables

Callables is an abstraction of visual scripting that defines the core of Gameplay Ingredients Runtime. A Callable is a script that can be Called, to perform a certain task. There are two main types of callable used in gameplay ingredients : [Logic and Actions](events-logic-actions.md). In order to call them out of gameplay events, [Events](events-logic-actions.md) are not Callables per se but use callables to start scritping chains of calls.

Through Gameplay Ingredients, there are many more scripts that makes use of callables : [State Machines](state-machines.md),  [Factories](factories.md),  [Counters](counters.md), [Timers](timers.md), [Interactive](interactive.md), some [Rigs](rigs.md), and also some [Managers](managers.md) 

## Instigators

Callables can be called, passing an **Instigator** argument: a source object that was involved in the script execution, and that can be processed by any Callable in the chain of calls.

> For Example : A **OnTriggerEnter** Event, can call a **DelayLogic**, then a **DestroyObjectAction** defined on destroying the instigator. In this case, the Instigator will be first set by the OnTriggerEvent to be the object that entered the trigger (for example, the player). Then it will be passed to the Delay Logic, then to the Destroy Object. This final action will use its instigator argument which is the player game object that entered the trigger, and will be able to destroy it.

## Difference with UnityEvents

While UnityEvents are convenient as they can call most of the C# API, the Callable can only call callables. However, the need for automatic instigator propagation, call reordering and debug handling of all these calls makes the use of Callables more suited. Regardles of that, the **UnityEventAction** is provided to be able to perform UnityEvent calls at anytime. However, the instigator still can't be passed on as argument to these UnityEvent calls at the moment. 

## Editing Callable Lists

Events, Logic and Actions (but also other components such as [States](state-machines.md), [Managers](managers.md), [Factories](factories.md), ... ) can call scripts from other callable components. Editing in inspector of these lists can be achieved through a reorderable list where calls can be added in chronological order.

![](images/callable-list.png)

* Click the + button to add a new entry, then drag onto the Object field the game object or the component you want to add.

* You can use the popup drop-down to select any callable component on the target game object.

## Previewing the hierarchy of calls

You can preview the hierarchy of calls in editor by using the [Callable Tree Explorer](callable-tree-explorer.md) Window. This window allows you to get an overview of what's being called.

You can also enable Verbose Call Logging in the Gameplay Ingredients Settings asset.

## Calling Callables (C#)

Callables can be Called using the Static Method `GameplayIngredients.Callable.Call(call, instigator)` where call can be of the following:

* single `Callable` object
* `Callable[]` array

instigator parameter is of type `GameObject` and defaults to `null` so it's mandatory.

## Performance and Update Calls

Because calling an update message object has performance implications in unity, most of the callable system is designed to be run at non-update time. In order to perform runtime update calls, prefer using **Rigs** (still under development)

An option is still available in [settings](settings.md) to enable some of the update calls.  **Use at your own risk !** 

## Writing Callables

You can write your own callables my making them derive from the `ICallable` interface, or derive from `GameplayIngredients.Actions.ActionBase` or `GameplayIngredients.Logic.LogicBase` if you prefer to be consistent to the  [events-logic-actions](events-logic-actions.md) philosophy.

The `ICallable` interface is pretty straightforward:

```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

namespace GameplayIngredients
{
    public interface ICallable
    {
        void Execute(GameObject instigator = null);
    }

}
```

Implementing Callables enable you to reference them in the Callable Lists, and view them in the [Callable Tree Explorer](callable-tree-explorer.md) 