import turtle as t
import random as r

#기본 설정
t.speed(-1)
t.screensize(10,10 ,'black')

def move(x, y):
    t.penup()
    t.goto(x,y)
    t.pendown()

def star(a):
    for i in range(5):
        t.forward(a)
        t.right(144)

def r_star(a):
    q= r.randint(0,1)
    if q==0:
        t.begin_fill()
        star(a)
        t.end_fill()
    else:
        star(a)
        
def square(a):
    for i in range(4):
            t.forward(a)
            t.right(90)

def r_square(a):
    q= r.randint(0,1)
    if 1== 0:
        t.begin_fill()
        square(a)
        t.end_fill()
    else:
        square(a)
        
def circle(a):
    t.circle(a/2)

def r_circle(a):
    q=r.randint(0,1)
    if q==0:
        t.begin_fill()
        circle(a)
        t.end_fill()
    else:
        circle(a)

def triangle(a):
    for i in range(3):
        t.forward(a)
        t.right(120)

def r_triangle(a):
    q= r.randint(0,1)
    if 1==0:
        t.begin_fill()
        triangle(a)
        t.end_fill()
    else:
        triangle(a)
    
def heart(a):
    t.forward(a/2)
    t.circle(a/4, 180)
    t.right(90)
    t.circle(a/4, 180)
    t.forward(a/2)

def r_heart(a):

    q= r.randint(0,1)
    if q==0:
        t.begin_fill()
        heart(a)
        t.end_fill()
    else:
        heart(a)

#지피티한테 물어보면 색 뽑아준다
red_color_list = [
    "red",
    "darkred",
    "indianred",
    "firebrick",
    "crimson",
    "maroon",
    "tomato",
    "salmon",
    "orangered",
    "coral"
]
blue_color_list = [
    "blue",
    "royalblue",
    "mediumblue",
    "navy",
    "dodgerblue",
    "deepskyblue",
    "skyblue",
    "lightskyblue",
    "lightblue",
    "powderblue"
]
purple_color_list = [
    "purple",
    "indigo",
    "darkviolet",
    "mediumorchid",
    "blueviolet",
    "darkorchid",
    "plum",
    "violet",
    "orchid",
    "lavender"
]

for i in range(500):
    a = r.randint(5, 40)
    x = r.randint(-600, 600)
    y = r.randint(-300, 300)
    move(x,y)
    t.right(r.randint(1,180))
    
#그라데이션으로 색 지정, 중간은 확률 반반
    if x<-360:
        t.color(r.choice(red_color_list))
    elif x<-120:
        a= r.randint(0,1)
        if a== 0:
            t.color(r.choice(red_color_list))
        else:
            t.color(r.choice(purple_color_list))
    elif x<120:
        t.color(r.choice(purple_color_list))
    elif x<360:
        a = r.randint(0, 1)
        if a == 0:
            t.color(r.choice(blue_color_list))
        else:
            t.color(r.choice(purple_color_list))
    else:
        t.color(r.choice(blue_color_list))

    t.width(r.randint(2,4))
    a = r.randint(5, 40)
    draw_list= [r_star, r_square, r_circle, r_triangle, r_heart] ###
    draw_list[r.randint(0,len(draw_list)-1)](a)

t.done()
