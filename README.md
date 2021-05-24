# python calculus , tkinter programming
# A simple calculus calculator

from tkinter import *
from sympy import *

new_root = Tk()

new_root.title("Math calculus")
new_root.iconbitmap('ico1.ico')
new_root.configure(bg="CadetBlue1")

e = Entry(new_root, bg='cyan', fg='black')
e.grid(row=0, column=0, columnspan=8, ipady=20, ipadx=130)
x = symbols("𝑥")


def on_click(number):
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + str(number))


def clear():
    e.delete(0, END)


def ac():
    current = e.get()
    z = len(current)
    y = z - 1
    e.delete(y, END)


def add():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "+")


def div():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "/")


def mul():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "*")


def sub():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "-")


def sin():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "sin(")


def cos():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "cos(")


def tan():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "tan(")


def bk_l():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + ")")


def bk_f():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "(")


def exp():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "exp(")


def power():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "**")


def log():
    current = e.get()
    e.delete(0, END)
    e.insert(0, str(current) + "log(")


def integ():
    p = integrate(e.get())
    e.delete(0, END)
    e.insert(0, p)


def derivative():
    p = diff(e.get())
    e.delete(0, END)
    e.insert(0, p)


button_1 = Button(new_root, text="1", padx=20, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(1))
button_2 = Button(new_root, text="2", padx=20, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(2))
button_3 = Button(new_root, text="3", padx=21, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(3))
button_4 = Button(new_root, text="4", padx=20, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(4))
button_5 = Button(new_root, text="5", padx=20, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(5))
button_6 = Button(new_root, text="6", padx=21, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(6))
button_7 = Button(new_root, text="7", padx=20, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(7))
button_8 = Button(new_root, text="8", padx=20, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(8))
button_9 = Button(new_root, text="9", padx=21, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(9))
button_0 = Button(new_root, text="0 ", padx=49, pady=10, bg="black", fg="white", bd=5, command=lambda: on_click(0))
button_p = Button(new_root, text=". ", padx=21, pady=10, bg="cadetblue", fg="white", bd=5,
                  command=lambda: on_click("."))
button_x = Button(new_root, text="x", font="italic", padx=35, bg="green4", fg="white", bd=5, pady=2,
                  command=lambda: on_click(x))
button_bk_f = Button(new_root, text="(", bg="cadetblue", fg="white", bd=5, padx=42, pady=10, command=bk_f)
button_bk_l = Button(new_root, text=")", bg="cadetblue", fg="white", bd=5, padx=42, pady=10, command=bk_l)

button_sin = Button(new_root, text="sin ", bg="cadetblue", fg="white", bd=5, padx=35, pady=10, command=sin)
button_cos = Button(new_root, text="cos", bg="cadetblue", fg="white", bd=5, padx=35, pady=10, command=cos)
button_tan = Button(new_root, text="tan", bg="cadetblue", fg="white", bd=5, padx=35, pady=10, command=cos)
button_exp = Button(new_root, text=" e/exp ", bg="cadetblue", fg="white", bd=5, padx=6, pady=10, command=exp)
button_pow = Button(new_root, text="^/** ", bg="cadetblue", fg="white", bd=5, padx=10, pady=10, command=power)
button_log = Button(new_root, text="log ", bg="cadetblue", fg="white", bd=5, padx=13, pady=10, command=log)

b_ac = Button(new_root, text="AC ", bg="Orange red", fg="white", bd=5, padx=45, pady=10, command=ac)
b_clear = Button(new_root, text="C", bg="Red", fg="white", bd=5, padx=19, pady=10, command=clear)
b_add = Button(new_root, text="  + ", bg="coral3", fg="white", bd=5, padx=35, pady=10, command=add)
b_mul = Button(new_root, text="x ", bg="coral3", fg="white", bd=5, padx=39, pady=10, command=mul)
b_div = Button(new_root, text="/", bg="coral3", fg="white", bd=5, padx=41, pady=10, command=div)
b_sub = Button(new_root, text="-", bg="coral3", fg="white", bd=5, padx=41, pady=10, command=sub)

b_integrate = Button(new_root, bg="medium blue", fg="white", bd=5, text="Integrate", padx=20, pady=10, command=integ)
b_differ = Button(new_root, bg="medium blue", fg="white", bd=5, text="Differentiate ", padx=10, pady=10,
                  command=derivative)

button_1.grid(row=3, column=0)
button_2.grid(row=3, column=1)
button_3.grid(row=3, column=2)

button_4.grid(row=2, column=0)
button_5.grid(row=2, column=1)
button_6.grid(row=2, column=2)

button_7.grid(row=1, column=0)
button_8.grid(row=1, column=1)
button_9.grid(row=1, column=2)
button_0.grid(row=4, column=0, columnspan=2)
button_p.grid(row=4, column=2)

b_add.grid(row=1, column=3, columnspan=2)
b_mul.grid(row=2, column=3, columnspan=2)
b_div.grid(row=3, column=3, columnspan=2)
b_sub.grid(row=4, column=3, columnspan=2)
button_x.grid(row=1, column=5, columnspan=2)
button_bk_f.grid(row=2, column=5, columnspan=2)
button_bk_l.grid(row=3, column=5, columnspan=2)

button_sin.grid(row=4, column=5)
button_cos.grid(row=5, column=5)
button_tan.grid(row=5, column=4)
button_exp.grid(row=5, column=2)
button_pow.grid(row=5, column=1)
button_log.grid(row=5, column=0)

b_ac.grid(row=6, column=1, columnspan=2)
b_clear.grid(row=6, column=0)
b_integrate.grid(row=6, column=3, columnspan=2)
b_differ.grid(row=6, column=5, columnspan=2)

new_root.mainloop()
