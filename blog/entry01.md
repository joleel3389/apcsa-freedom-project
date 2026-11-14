# Entry 1: Deciding on my freedom project tool
##### 11/9/26

### What tool did I decide on, and why?

---

For my project, I decided to use Godot/GDScript. Godot is a 2D/3D game engine. The reason why I chose Godot was because I wanted to make a game that users could learn some basic cybersecurity awareness through cryptography puzzles. This game would teach users the importance of concealing private information online, how to maintain/protect confidentiality, and the usefulness of authentication. 

For how I tinkered with my tool, I first decided I should set up Godot on my computer so that down the line, I wouldn't have to worry about setting it up. My installation is shown below:

<img width="1675" height="1008" alt="2026-11-08 12_06_22-testing-godot" src="https://github.com/user-attachments/assets/9badcd0d-77d2-4734-812f-bf5c7937aff3" />

Following my installation of Godot, I began to learn about its main scripting language: GDscript. To learn about GDscript, I used both its [documentation](https://gdscript.com/tutorials/) and a website called [gdquest](https://gdquest.github.io/learn-gdscript/), which provided lessons that help you get adapted to GDscript. It has coding activities that allow me to test out the concepts myself as I tried to code for myself. 

One memorable concept I've learned so far are functions in GDscript. For GDscript, functions are done differently than if we were to compare it to JavaScript or Java. It's identifier/name uses underscores, `_`, to indicate separation, or camelCase, but underscores are more commonly used. Some built-in functions even use underscore prefixes in their name. Other than that, these identifiers/names can't use spaces or numbers (at the start) likewise to Java or JavaScript. For example, take this function below:

```godot
    func _ready():
	print("Welcome!")
```

This is a built-in function that starts with an underscore prefix. Other than the naming, a function in Godot starts with `func` and ends with a pair of parentheses, followed by a colon like `():`. This contrasts with Java or Javascript's usage of semi-colons, `;`, or curly braces, `{}`. 

For non-built-in Godot functions, we follow normal Godot naming conventions. For example, I made a function that would draw a rectangle, using other functions like `move_forward()` & `turn_right()` below. 

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

The function `draw_rectangle()` is tasked to make a rectangle with the dimensions of a width of 200 pixels and a height of 120 pixels. As you can see with this function, you're allowed to use functions within functions. There's also not a formal way to show the closing of your functions.

Another example of using a function within a function can be seen within this code:

```godot
func draw_square():
	move_forward(200)
	turn_right(90)
	move_forward(200)
	turn_right(90)
	move_forward(200)
	turn_right(90)
	move_forward(200)
	turn_right(90)
	
func draw_three_squares():
	jump(300,300)
	draw_square()
	jump(300,300)
	draw_square()
	jump(300,300)
	draw_square()
```

As seen, the first function actually draws a square with a side length of 200 pixels, but when we actually call it three times in the `draw_three_squares()` function, we can see three squares actually being drawn. 



### Engineering Design Process

---

I'm currently on the first step of the engineering design process: define the problem. In my case, my problem is "How can I use Godot to help make my cryptography game?" To address this problem, I'm going to continue utilizing my tool and improving my usage with my tool to make a 2D game with mysterious cryptography puzzles, in order to allow users to learn the significance of cybersecurity. For my next steps, I plan to research more into the problem (step 2). To do this, I'll progress in learning my tool, Godot, so I can solve the problem more effectively. I'd also like to look into the most appropriate ways I can add my cryptography puzzles.

### Skills

---

Below are the skills I've learned while working on my blog:
* How to learn
    * When first learning my tool, I used websites like the [Godot guide](https://www.gdquest.com/library/gdtour_get_to_know_godot_editor/) and [GDScript guide](https://gdquest.github.io/learn-gdscript/) to help gain exposure to the tool. The guides like the GDScript guide were easy to follow, with their own lessons I could code myself. 
* How to read
    * When first figuring out how to connect my Github repo to my tool, Godot, I had to read a few documentations that would allow me to do so on Debian Linux. With my brother's help, we both read many documentations to help set up Godot on my computer. Doing so not only helped increase my familiarity with Linux but successfully allowed Godot to work on my home computer. 

### Next steps

---

For my next steps, I plan to research/learn more about my tool in depth to use it more effectively, but to also see how I can incorporate my cryptography puzzle ideas appropriately into my project.

[Next](entry02.md)

[Home](../README.md)