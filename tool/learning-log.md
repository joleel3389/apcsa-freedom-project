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


**Using [GDScript guide](https://gdquest.github.io/learn-gdscript/):**
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

### 11/16/26: Godot from scratch L6-8
**Using [GDScript guide](https://gdquest.github.io/learn-gdscript/):**

* Functions can have arguments and parameters
    * Parameters are optional placeholders in a function's code, which are filled every time when the function is called.
        * They can be numbers, text, etc.
        * They go inside your parentheses with any name you want, as long as it follows normal naming conventions
    * Ex. `func draw_square(size):
        * Parameter goes in the parentheses before the colon
    * Functions can have multiple parameters/placeholders, separated by commas

For example, we can use a "length" parameter with out `draw_corner()` function
```godot
func draw_corner(length):
    move_forward(length)
    turn_right(90)
    move_forward(length)
```
Once we draw the local parameter "length", we can use it within our inner functions within `draw_corner()`.

If we wanted multiple parameters, we could do the following with the `draw_rectangle()` function:
```godot
func draw_rectangle(length, height):
	move_forward(length)
	turn_right(90)
	move_forward(height)
	turn_right(90)
	move_forward(length)
	turn_right(90)
	move_forward(height)
	turn_right(90)
```

* Variables are labels used to keep track of values that vary over time
    * Function parameters are considered variables.
    * Member variables are variables built into Godot, being values atatched to a game entity.
        * Member variables can have sub-values/variables, accessed using dot operators `.`
            * Ex. `position` and `scale` have `x` and `y` subvariables, being accessed like so: `position.x = value`
    * The value of a variable is changed using the equal sign, `=`
        * The `=` indicates variable assignment, not equality.
* Regarding the X-axis and Y-axis, the Y-axis is different in code
    * As the y-axis goes down, it is more positive. Thus, it points downwards.
    * The origin starts from (0,0)--there are no negative numbers, the axises follow the display pixels for a screen.

For example, we can set the x and y subvalues of `position` to determine where our shape starts:
```godot
func run():
	position.x = 120
	position.y = 100
	draw_rectangle(200, 120)
```

In this case, this code starts to draw a rectangle at position (120,100), with a length of 200 pixels and height of 120 pixels.

The following example will make 3 squares with proportions of 100x100 pixels, all 100 pixels apart and starting at (100,100).
```godot
func run():
	position.x = 100
	position.y = 100
	draw_rectangle(100,100)
	position.x += 200
	draw_rectangle(100,100)
	position.x += 200
	draw_rectangle(100,100)
```

* The `print()` function is made to output an argument to your output window
    * Used to access variable values/messages.
    * Essentially sends information to display on your device screen.
* To define your own variable, you must use the `var` keyword followed by your desired variable name. To assign it a value, follow up with `=` and your desired value.
    * Note that `var` stands for variable, like `func` stands for function. This keyword, `var`, only needs to be used *once* per variable after a variable is defined. 
    * Variables are case-sentitive, so `health` and `Health` would be different variables.
        * However, you CAN'T create two variables with the same name.
    * After defining a variable, you can change its value whenever using the same `=` sign for assignment. 

### 11/23/26: Godot from scratch L9-12
**Using [GDScript guide](https://gdquest.github.io/learn-gdscript/):**

* The `-=` syntax is a shortchut to subtracting a value from a variable.
* The `+=` syntax is a shortcut to adding a value to a variable.

* Godot has special functions we can customize or add to, such as the `_process()` function which does calculations or continuous actons.
* When Godot draws on the screen, that's called a frame.

For example, the `_process()` function runs multiple times, for every frame.
```godot
func _process(delta):
	rotate(0.05)
```

To create a circular motion, we can add the `move_local_x()` function
```godot
func _process(delta):
	rotate(0.05)
	move_local_x(5)
```

* Almost everything in your game will have a `_process()` function that runs every frame.
* A **frame** is an image of the game world on the screen
    * As frames move, you get the illusion of movement. 
    * Frames take varying amounts of time to calculate.
* The `delta` parameter represents a time difference that varies each frame (in seconds), which helps to ensure the game is consistent for everyone.
    * Multiplying a time-sensitive value by delta makes your function time-dependent over frame-dependent for more relevant movement.

For example, the following code helps to manage the rotation of our character:
```godot
func _process(delta):
	rotate(2*delta)
	move_local_x(100*delta)
```
Our character would smoothly rotate 2 radians per second and in a circle clockwise

* In godot, we comment by using the `#` symbol infront of our comment
* A variable is a label for a value we can save, change, and read later.
    * Makes code easier to read
    * If we define a variable inside of a function, only that function can use it.
        * Trying to use it outside of its function leads to an error.
    * Variables defined outside of a function are script-wide functions--they can be accessed anywhere

For example, within the following code there is a scope error: the `set_angular_speed()` function is trying to use a local variable declared in `_process()`...
```godot
func _process(delta):
	var angular_speed = 4
	rotate(angular_speed * delta)

func set_angular_speed(new_angular_speed):
	angular_speed = new_angular_speed
```

To fix it, we can change the code to the following so the variable becomes script-wide:
```godot
var angular_speed = 4

func _process(delta):
	rotate(angular_speed * delta)

func set_angular_speed(new_angular_speed):
	angular_speed = new_angular_speed
```

### xx/xx/xx: Godot from scratch L
**Using [GDScript guide](https://gdquest.github.io/learn-gdscript/):**

<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
