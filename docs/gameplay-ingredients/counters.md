# Counters

Counters are special scripts that hold per-instance values so they can be used as logic counters in your game levels.

## Counter

The Counter component is the main holder of the value of a counter. It initializes at a given value and can be altered during the gameplay.

It possesses the following properties:

* **ValueSource** (enum) : determines the source of the value stored into the counter.
  * Property : A property set on the component
  * GlobalVariable : A [Global Variable](globals.md)  
  * GameSave : A data stored into the [game save manager](game-save-manager.md) 

* **Value** : (if Value Source is Property) the initial value of the counter.
* **Game Save Variable Name** : (if Value Source is Game Save) the name of the Game Save Manager int Variable that holds the value
* **Game Save Location** : (if Value Source is Game Save) the location of the Game Save where to look for the name
* **Global Variable Name** : (if Value Source is Global Variable) the name of the Game Save Manager int Variable that holds the value
* **Global Scope** : (if Value Source is Global Variable) the location of the Game Save where to look for the name
* **OnValueChanged** : Called when the value of the counter changes

## CounterAction

Counter action performs a modification of one or many Counter's value(s).

* **Counters** : the list of Counter Components to alter
* **Operation** (enum) : the operation to apply on the counters
  * Set
  * Add
  * Subtract
  * Multiply
  * Divide
  * Modulo
* **ValueSource** (enum) : determines the source of the value to use for the operation
  - Property : A property set on this CounterAction
  - GlobalVariable : A [Global Variable](globals.md)  
  - GameSave : A data stored into the [game save manager](game-save-manager.md) 

- **Value** : (if Value Source is Property) the value to apply to the counter(s).
- **Game Save Variable Name** : (if Value Source is Game Save) the name of the Game Save Manager int Variable that holds the value
- **Game Save Location** : (if Value Source is Game Save) the location of the Game Save where to look for the name
- **Global Variable Name** : (if Value Source is Global Variable) the name of the Global int Variable that holds the value
- **Global Scope** : (if Value Source is Global Variable) the location of the Global Variable Scope where to look for the variable name

## Counter Logic

Counter Logic performs checks on counters and calls according to evaluations.

* **Counter**: the counter component to perform the evaluation on.
* **Evaluation** the test to perform
  * Equal
  * Not Equal
  * Greater
  * Greater Or Equal
  * Less
  * Less Or Equal
* **ValueSource** (enum) : determines the source of the value to use for the evaluation
  - Property : A property set on this CounterLogic
  - GlobalVariable : A [Global Variable](globals.md)  
  - GameSave : A data stored into the [game save manager](game-save-manager.md) 

- **Value** : (if Value Source is Property) the value to compare to the counter.
- **Game Save Variable Name** : (if Value Source is Game Save) the name of the Game Save Manager int Variable that holds the value to compare
- **Game Save Location** : (if Value Source is Game Save) the location of the Game Save where to look for the name to compare
- **Global Variable Name** : (if Value Source is Global Variable) the name of the Global int Variable that holds the value to compare
- **Global Scope** : (if Value Source is Global Variable) the location of the Global Variable Scope where to look for the variable name to compare