# Window Setup

import turtle
import time

# Asking to waitt for 3 seconds
wait = turtle.Turtle()
wait.goto(0,0)
wait.penup()
wait.hideturtle()
wait.write("3...",align="center", font=("courier",100,"normal"))
time.sleep(1)
wait.clear()
wait.write("2...",align="center", font=("courier",100,"normal"))
time.sleep(1)
wait.clear()
wait.write("1...",align="center", font=("courier",100,"normal"))
time.sleep(1)
wait.clear()

def closegame() :
    quit()

win = turtle.Screen()
win.tracer(0)
win.bgcolor("black")
win.setup(width = 800, height = 600)
win.title("PING PONG by Lalit")


# paddle1
paddle1 = turtle.Turtle()
paddle1.up()
paddle1.goto(-350, 0)
paddle1.shape("square")
paddle1.shapesize(stretch_len=1, stretch_wid=5)
paddle1.color("white")
paddle1.speed(0)

# paddle2
paddle2 = turtle.Turtle()
paddle2.up()
paddle2.goto(350,0)
paddle2.shape("square")
paddle2.shapesize(stretch_len=1, stretch_wid=5)
paddle2.color("white")
paddle2.speed(0)

# ball
ball = turtle.Turtle()
ball.penup()
ball.goto(0, 0)
ball.shape("circle")
ball.color("white")
ball.speed(0)
ball.dx = 2.5
ball.dy = 2.5

# Announcer
ann = turtle.Turtle()
ann.goto(0,0)
ann.penup()
ann.pencolor("black")
ann.hideturtle()

# Scores
score1 = 0
score2 = 0

# Player Scores
pen = turtle.Turtle()
pen.penup()
pen.color("White")
pen.goto(0, 260)
pen.hideturtle()
pen.write(f"Player 1 : {score1}   Player 2 : {score2}",align="center", font=("courier",24,"normal"))

# Movement functions for paddle1
def paddle1_up() :
    y1 = paddle1.ycor()
    y1 = y1 + 20
    paddle1.sety(y1)

def paddle1_down():
    y1 = paddle1.ycor()
    y1 = y1 - 20
    paddle1.sety(y1)

# Movement functions of paddle2
def paddle2_up() :
    y2 = paddle2.ycor()
    y2 = y2 + 20 
    paddle2.sety(y2)

def paddle2_down() :
    y2 = paddle2.ycor()
    y2 = y2 - 20
    paddle2.sety(y2)


# Keyboard bindings

win.listen()
win.onkey(paddle1_up,"a")
win.onkey(paddle1_down,"z")
win.onkey(paddle2_up,"o")
win.onkey(paddle2_down,"l")

# Main game loop
while True :
    win.update()

    # Move the ball
    ball.setx( ball.xcor() + ball.dx)
    ball.sety( ball.ycor() + ball.dy)

    # Border checking
    if ball.ycor() > 280 :
        ball.sety(280.00)
        ball.dy = ball.dy * -1
 
    if ball.ycor() < -280 :
        ball.sety(-280)
        ball.dy = ball.dy * -1

    if ball.xcor() > 380 :
        ball.goto(0, 0)
        ball.dx = ball.dx * -1
        score1 += 1
        pen.clear()
        pen.write(f"Player 1 : {score1}   Player 2 : {score2}",align="center", font=("courier",24,"normal"))

    if ball.xcor() < -380 :
        ball.goto(0, 0)
        ball.dx = ball.dx * -1 
        score2 += 1
        pen.clear()
        pen.write(f"Player 1 : {score1}   Player 2 : {score2}",align="center", font=("courier",24,"normal"))

    # Ball and Paddle Collisions 
    if ball.xcor() > 340 and ball.xcor() < 360 and ball.ycor() < paddle2.ycor() + 50 and ball.ycor() > paddle2.ycor() - 50 : 
        ball.setx(330)
        ball.dx = ball.dx * -1 

    if ball.xcor() < -340 and ball.xcor() > -360 and ball.ycor() < paddle1.ycor() + 50 and ball.ycor() > paddle1.ycor() - 50 : 
        ball.setx(-330)
        ball.dx = ball.dx * -1 

    # Announcement
    if score1 == 3:
        win.clearscreen()
        win.clearscreen()
        ann.write("Player 1 Wins!!",align="center", font=("courier",80,"normal"))
        time.sleep(2)
        quit()
    elif score2 == 3 :
        win.clearscreen()
        win.clearscreen()
        ann.write("Player 2 Wins!!",align="center", font=("courier",80,"normal"))
        time.sleep(2)
        quit()
