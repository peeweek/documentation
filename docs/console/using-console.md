# Using Console

By default, a default console is spawned from the prefab when playing.

Press the Backslash `\` key at runtime to toggle the Console (Can be customized if you use the package as local package)

Use the input field to input commands and execute button or return key to execute.

Upon entering a command, syntax completion panel displays information below the text field.

* Commands that look like the entered text
* Aliases of the command
* Help of the command

### Navigation (Defaults)

* Backslash to Open/Close console
* Up/Down arrows to access type command history
* PageUp/PageDown to scroll console log history

### Navigation (Views)

* Tab / Shift Tab to cycle views (when views are active)
* Ctrl + Tab to Close current view (when views are active)

### Built-in Commands

* `help` : displays a list of all registered commands with summary
* `help [command]` displays the `GetHelp()` string of given command.
* `clear` clears the console output.
* `exit` closes the application or stops playing in editor
* `screenshot` takes screenshots
* `stat` displays stat screens (Views)
* `time` performs time scale manipulation

### Peek

The Peek Feature will display temporary log messages at the top of the screen, when the console is not visible.

The Peek feature can be customized in the [Prefab's Console Component](getting-started.md).

