from tkinter import *
import random

root = Tk()
root.title('Фигуры')
root.resizable(0,0)
root.geometry('500x500')

def triangle():
    canvas.create_line(80, 370, 310, 370)
    canvas.create_line(80, 370, 230, 250)
    canvas.create_line(230, 250, 310, 370)

def rectangle():
    canvas.create_rectangle(80, 180, 310, 370)

def oval():
    canvas.create_oval(80, 180, 310, 370)

def change():
    canvas.delete('all')
    functions = (triangle, rectangle, oval)
    choice = random.choice(functions)
    choice()

button = Button(root, text = 'Создать фигуру', command = change)
button.pack()

canvas = Canvas(root, height = 500, width = 500)
canvas.pack()

root.mainloop()
