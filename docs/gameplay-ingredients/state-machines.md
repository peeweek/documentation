# State Machines

Gameplay Ingredients implements a simple way to declare state machines and control them through Actions.

## State Machine Component

The State Machine Component defines a state machine and its states. Each State machine start at a given state and can change its state along time.  You can use a **SetStateAction** to change a State Machine to another state.

## States

States define a State of a state Machine. A state is defined by a Game Object holding a **State** behaviour.

State Behaviour are composed of a **OnStateEnter** and **OnStateExit** callable lists. Upon Entering the state, the OnStateEnter will be called, and the OnStateExit is called before exiting the state.

## Life Cycle Example

The State Machines enable their state objects based on the current active state, and perform the state enter calls just after enabling, and on state exit just before disabling.

Let's take an example with a state machine that defines State A and State B, Setting  State A as Default.

**At Startup**

* State A becomes Enabled
* State A > **OnStateEnter** is called

**A SetStateAction** changes the state to **State B**

* State A > **OnStateExit** is called
* State A becomes Disabled
* State B becomes Enabled
* State B > **OnStateEnter** is called