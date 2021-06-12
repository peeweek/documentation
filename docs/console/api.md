# Console API

The Console Package can be easily extended by creating Console Commands or Views to extend the visibility of the package.

In order to access the Console API, you need to access the `ConsoleUtility` namespace either by adding a `using ConsoleUtility` or placing your classes in the namespace directly.

## Console Commands

Console Commands can be easily defined by creating a class:

* Implementing the `IConsoleCommand` interface
  * This interface requires you implement the following:
    * `public string name` : the actual name of the command. Names are case insensitive.
    * `public string summary` : a string that describes briefly the purpose of the command
    * `public string help`: a multiline string that describes precisely the syntax of the command.
    * `public IEnumerable<Console.Alias> aliases` : a list of aliases (shortcuts) for your command.
* **Optionally** : using the `[AutoRegisterConsoleCommand]` class attribute
  * Not implementing this attribute will require a manual registration of your class using the `public static void AddCommand(IConsoleCommand command)` method.

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

namespace ConsoleUtility
{
    [AutoRegisterConsoleCommand]
    public class MyConsoleCommand : IConsoleCommand
    {
        public void Execute(string[] args)
        {
	     //use args array to parse command. args[] do not include the base command so in
             // command 'mycommand foo bar' args[0] is foo and args[1] is bar
        }

        public string name => "mycommand"; 		// the actual command key
        public string summary => "Does soemthing";	// summary displayed when typing 'help'
        public string help => "usage: mycommand"; 	// help displayed when typing 'help mycommand'

        public IEnumerable<Console.Alias> aliases
        {
            get
            {
                    yield return Console.Alias.Get("myalias", "mycommand foo bar");
                    // yield return any console alias you need, for ease of use purposes
            }
        }
    }
}

```

## Views

Views can be created by deriving from the `ConsoleUtility.View` class. These can be registered 

* Manually using the `Console.RegisterView(Type t)`,

* using the `[RegisterStatView("view_name")]` attribute, this way your view will be available through the `stat view_name` command

```c#
using System.Text;
using UnityEngine;
using UnityEngine.SceneManagement;

namespace ConsoleUtility
{
    [RegisterStatView("foo")]
    class FooStatView : View
    {  
        // Refreshes 15 times/s
        public FooStatView() : base(15f) { } 

        public override string GetDebugViewString()
        {
            return $@"Some text to draw";
        }
    }
}

```



