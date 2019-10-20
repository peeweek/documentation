# Play From Here

Play from Here (a.k.a Play from Scene View point of view) is a feature that enables defining custom behavior in order to start playing from a particular point of view.

![Play From Here](images/play-from-here.gif)

## Setup and How To Use

In order to use this feature, your code must implement a static method that will handle the startup. This is required so you can perform your own adjustments (for instance, disabling an intro cinematic, or customize your player controller).

When this callback is set-up correctly, a **> Here** button shall appear on the additional scene view toolbar.

## Play from Here Callback

Here's a sample code that demonstrates how to implement a play from here callback.

```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEditor;

static class SamplePlayFromHere
{
    [InitializeOnLoadMethod]
    static void SetPlayFromHere()
    {
        GameplayIngredients.Editor.PlayFromHere.OnPlayFromHere += PlayFromHere_OnPlayFromHere;
    }

    private static void PlayFromHere_OnPlayFromHere(Vector3 position, Vector3 forward)
    {
        var initialPosition = position + forward;
        var initialForward = forward;
        initialForward.Scale(new Vector3(1, 0, 1));
        initialForward.Normalize();
        var initialRotation = Quaternion.LookRotation(initialForward, Vector3.up);

        var prefab = (GameObject)Resources.Load("DefaultPlayer");
        var Player = Object.Instantiate(prefab, initialPosition, initialRotation);
        Player.name = "(Play From Here)" + prefab.name;
    }
}```
```