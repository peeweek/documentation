# Messager

The Messager is a Game-Wide static class that enables broadcasting messages. Scripts can register as listeners of a particular message and receive them when another object broadcasts them. 

Gameplay Ingredients comes built-in with Events, Actions and a Timeline Track that works with the Messager.

## Receiving Messages with OnMessageEvent

OnMessageEvent is an [Event](events-logic-actions.md) that can execute [callables](callable.md) when a message is sent. Its behaviour will be enabled when the component or its game object is active.

## Broadcasting Messages with SendEventAction

You can broadcast messages via the messager using a SendEventAction.

## C# API

How to Register/Unregister a listener:

```C#
// Register a message
GameplayIngredients.Messager.RegisterMessage("My_Message", MyMessageHandler);

// Unregister a message
GameplayIngredients.Messager.RemoveMessage("My_Message", MyMessageHandler);


void MyMessageHandler()
{
    // Do Something.
}

```

How to Send Events:

```C#
GameplayIngredients.Messager.Send("My_Message");
```




