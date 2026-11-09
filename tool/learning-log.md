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
    * For example,
    ```godot
    func _ready():
	print("Welcome!")
    ```
* Return values
    * You have to use `return` to return a value at any point.
    * Without using `return`, the code continues to the end of the function, and instead returns `null`.
        * However, you don't need to use a return value.
* A class-type can have its property altered without returning the node value due to its reference nature.

In addition to looking at a sneak peek of how basic GDScript is organized, I've downloaded Godot and plan to follow both a [GDScript guide](https://gdquest.github.io/learn-gdscript/) and [Godot guide](https://www.gdquest.com/library/gdtour_get_to_know_godot_editor/)

### 11/2/26: Godot from scratch L3-5
I installed and connecting Godot to my Github repo with the help of my brother on Debian Linux, testing out a new script file (uses GdScript).

<img width="1675" height="1008" alt="2026-11-08 12_06_22-testing-godot" src="https://github.com/user-attachments/assets/9badcd0d-77d2-4734-812f-bf5c7937aff3" />


**Using [Godot guide](https://www.gdquest.com/library/gdtour_get_to_know_godot_editor/):**
* Godot bundles a lot of libraries together

* Functions
    * To call a function, you use the exact function name followed by a pair of parentheses, (). 
        * Inside the parenthese, you can pass an **argument** inside of these parentheses while calling it. This argument may be option or required depending on the function. 
    * `show()` is a void Godot function that makes something visible (ex. character or item).
        * If an entity is already visible, calling `show()` again has *no* effect.
    * `hide()` is a void Godot function that hides your entity. 
        * Like the show function, an already hidden entity cannot be hidden again with `hide()`. 
    * `rotate(radians: float)` is a void Godot function that can rotate your entity.
        * The part inside the parentheses means that the function takes in radians as a `float` data type. 
For example, define a function using `func` followed by your function name. 
```godot
func run():
    show()
    rotate(0.5)
```
The tab is needed to the computer can properly compute it. Unlike Java or JavaScript, no semi-colons, `;`, or curly braces, `{}` are needed.

**Practice with non-built-in Godot functions:**
In the following code, the template functions NEED an argument passed in.
```godot
func draw_rectangle():
	move_forward(200)
	turn_right(90)
	move_forward(120)
	turn_right(90)
	move_forward(200)
	turn_right(90)
	move_forward(120)
```
This code makes a rectangle with a width of 200 pixels and a height of 120 pixels.

* Writing functions
    * The name of a function is an **indentifier**, as the name you give one function CAN'T be reused for another function. 
        * Ex. `func identity():`
        * Function names/indentifiers CAN'T use spaces or numbers (at the start). They use underscores, `_`, to indicate separation.
            * Ex. `func hi_hello():`
        * OR instead of underscores, you can use camelCase. 
            * Ex. `func hiHello():`
    * The instructions inside a function can be any code you want to repeat. Any time you call the function, the same exact instructions you put will be ran everytime. 

### x/x/xx: 


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
