# Logic

Here's a list of all Logic currently in latest version of Gameplay Ingredients.

| Name                          | Description                                                  |
| ----------------------------- | ------------------------------------------------------------ |
| DelayedLogic                  | Perform the Calls after a delay. Can perform other calls if delay is interrupted |
| EditorOnlyLogic               | Performs the Calls based on conditions of being a Standalone Player, Editor and/or Play From Here |
| FlipFlopLogic                 | Two Way Latch Logic, calls one list of Callable or the Other every time it is called. |
| Logic                         | Basic Logic forwarding, Calls a list of Callable scripts.    |
| NextFrameLogic                | Waits until the next frame to perform the Calls              |
| NTimesLogic                   | Perform the calls depending on a maximum counter value. Every time it is called, it increments the counter value. |
| PlatformLogic                 | Perform the calls based on current game platform. (PC,Mac,Console,Mobile, etc.) |
| RandomLogic                   | Perform one call at random from a list of Callable           |
| SaveDataLogic                 | Perform the calls based on testing a value from the Game Save Manager. |
| SaveDataSwitchOnIntLogic      | Calls the Nth item of a Callable List from an integer value stored by the Game Save Manager |
| SetInstigatorFromFactoryLogic | Changes the Instigator and forward the calls. The instigator is picked from a Factory based on an index. |
| SetInstigatorLogic            | Changes the Instigator and forward the calls                 |
| StateLogic                    | Forwards the calls based on a State Machine Current State    |

