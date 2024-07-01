import turtle
import random

# Setup the screen
screen = turtle.Screen()
screen.bgcolor("dark blue")
screen.title("Starlit Ocean")

# Create a turtle for the stars
star_turtle = turtle.Turtle()
star_turtle.hideturtle()
star_turtle.speed(0)
star_turtle.color("white")

# Create a turtle for the ocean waves
wave_turtle = turtle.Turtle()
wave_turtle.hideturtle()
wave_turtle.speed(0)
wave_turtle.color("light blue")

# Function to draw a star at a given position
def draw_star(x, y, size):
    star_turtle.penup()
    star_turtle.goto(x, y)
    star_turtle.pendown()
    for _ in range(5):
        star_turtle.forward(size)
        star_turtle.right(144)

# Function to draw a wave at a given position
def draw_wave(x, y, length):
    wave_turtle.penup()
    wave_turtle.goto(x, y)
    wave_turtle.pendown()
    wave_turtle.setheading(0)
    for _ in range(length // 10):
        wave_turtle.circle(10, 180)
        wave_turtle.circle(-10, 180)

# Randomly place stars
for _ in range(50):
    x = random.randint(-300, 300)
    y = random.randint(0, 300)
    size = random.randint(5, 15)
    draw_star(x, y, size)

# Draw waves on the ocean
for i in range(-300, 301, 50):
    draw_wave(i, -200, 100)

# Hide the turtle and display the screen
star_turtle.hideturtle()
wave_turtle.hideturtle()
screen.mainloop()
