# Tool Learning Log

## Tool: **Godot/GDScript**

## Project: **Mystery/horror game with cryptography puzzles**

---

### 10/19/26: Intro to GDScript
Used the [GDScript documentation](https://gdscript.com/tutorials/)

* GDScript does not need curly braces, `{}`, or semi-colons, `;`, but indentations are helpful.
    * Different from Javascript or Java
* Numbers
    * Enums are used when you don't care about the value automatically assigned by the engine.
    * Each value is a bit, and every data-type is stored as a certain amount of bits. 
        * Ex. An integer is 64 bits.
    * Number wrapping allows you to prevent an error when trying to reach the maximum x-value.
* Variables
    * Names will be in ALL lower-case, and connect words with an underscore, `_`
    * Assign types to variables like so: `var my_greeting: String = "Hello!"`
    * Global scope variables are available everywhere 
    * Local scope variables are only available within the functions they are called in.
* Functions
    * Built-in functions always have an underscore prefix in the name.
    * Custom functions will be named similarly to how we name variables.
* Return values
    * You have to use `return` to return a value at any point.
    * Without using `return`, the code continues to the end of the function, and instead returns `null`.
        * However, you don't need to use a return value.
* A class-type can have its property altered without returning the node value due to its reference nature.

In addition to looking at a sneak peek of how basic GDScript is organized, I've downloaded Godot and plan to follow both a [GDScript guide](https://gdquest.github.io/learn-gdscript/) and [Godot guide](https://www.gdquest.com/library/gdtour_get_to_know_godot_editor/)

### X/X/XX:
* Text


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
