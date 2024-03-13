# Workshop 1

In this workshop, we'll be giving you the tools to create a full illustration with Turtle graphics. Below are basic steps that you could follow to draw with Turtle and a cheat sheet of different commands you can use to create the picture you want.

## Direction/Movement Commands
One of the most important things in using Turtle is figuring out how it moves. Once you've figured out how it moves you can easily draw anything you want with it.

| Command               | Description                                                                        |
|-----------------------|------------------------------------------------------------------------------------|
| `goto(x , y)`         | Goes to the specific coordinates that were given                                 |
| `forward(distance)`     | Moves the turtle forward by a specified distance.                                   |
| `backward(distance)`    | Moves the turtle backward by a specified distance.                                  |
| `setheading(angle)`     | Sets the direction of the turtle to a specific angle. (has an absolute angle regardless of its current orientation)                              |
| `right(angle)`          | Turns the turtle clockwise by a specified angle. (will depend on its current orientation )                                   |
| `left(angle)`           | Turns the turtle counterclockwise by a specified angle. (will depend on its current orientation )                             |
| `penup()`               | Lifts the pen off the drawing surface so the turtle can move without drawing.       |
| `pendown()`             | Puts the pen back down on the drawing surface so the turtle can draw as it moves.   |
| `speed(speed)`          | Sets the speed of the turtle (0 = fastest, 1 = slowest).                             |

## Properties Commands

[turtle colors](https://trinket.io/docs/colors){ .md-button .md-button--primary style="font-size: 14px;" }

| Command                 | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `color(colorstring)`    | Sets pen color.                                                              |
| `pencolor(colorstring)` | Sets pen color.                                                              |
| `fillcolor(colorstring)`| Sets fill color.                                                            |
| `bgcolor(colorstring)`  | Sets background color.                                                      |
| `width(width)`          | Sets pen width.                                                              |
| `begin_fill()`          | Begins filling area bounded by subsequent drawing commands.                 |
| `end_fill()`            | Ends filling area started by `begin_fill()`.                                 |
| `clear()`               | Clears drawing canvas.                                                      |

## Steps in Drawing with Turtle

Here are simplified steps for drawing in Turtle:
Sure, here's the Markdown code segment with the numbered list formatted as an ordered list:

Step 1: Establish a starting point by setting coordinates.

```Python
penup()
goto(-100, 100)  # Example starting position
```

Step 2:  Define drawing properties such as color and the width of the pen.

```Python
pendown()  # Put the pen down to start drawing
pensize(2)  # Set the thickness of the lines
color("blue")  # Set the color of the lines
```

Step 3: Utilize Turtle to create shapes and lines for your image. If you are going to draw something particular, the easiest way to do this is by looking at how to do it in shapes. You can make your own functions that already draw the shapes as well, you can decide the parameters it takes.

```Python
def draw_circle(x, y, radius, color):
    penup()
    goto(x, y)
    pendown()
    color(color)
    begin_fill()
    circle(radius)
    end_fill()

def draw_triangle(points, color):
    penup()
    goto(points[0])
    pendown()
    color(color)
    begin_fill()
    for point in points[1:]:
        goto(point)
    goto(points[0])
    end_fill()

# Draw the body
draw_circle(0, -150, 150, "black")

# Draw the head
draw_circle(0, 0, 100, "black")

# Draw the ears
draw_triangle([(-30, 80), (-100, 180), (-50, 240)], "black")
draw_triangle([(30, 80), (100, 180), (50, 240)], "black")

# Draw the eyes
draw_circle(-40, 40, 20, "white")
draw_circle(40, 40, 20, "white")

# Draw the pupils
draw_circle(-40, 60, 10, "black")
draw_circle(40, 60, 10, "black")

# Draw the nose
draw_circle(0, 20, 15, "pink")


# Draw the mouth
penup()
goto(-20, 0)
pendown()
color("black")
right(90)
circle(20, 180)

```
