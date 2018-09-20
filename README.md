import tkinter as tk
from tkinter import *
import random

def cb():
    if var1.get()==0:
        randd()
def randd():
    v=StringVar()
    if var1.get()==1:
        c=random.randint(0,pow(10,15))
        v.set(str(c))
    else:
        a=(e1.get())
        b=(e2.get())
        c=random.randint(int(a),int(b))
        v.set(str(c))
    Entry(master,  text = "%s" %(v) ).grid(row=4, column=2)
master=Tk(screenName="Random Number Generator")
tex = tk.Text(master)
var1 = IntVar()
C1=Checkbutton(master, text='No range', variable=var1,onvalue = 1, offvalue = 0, command=cb).grid(row=0,column=0,sticky=W)
Label(master, text='Lower Bound').grid(row=1,column=0,padx=30)
Label(master, text='Upper Bound').grid(row=1,column=3,padx=30)
Label(master,text="RNG:").grid(row=4,column=2)
e1 = Entry(master)
e2 = Entry(master)
button=tk.Button(master,text="Generate",width=10,command=randd)

e3=Entry(master)
e1.grid(row=2, column=0)
e2.grid(row=2, column=3)
e3.grid(row=4,column=2)
button.grid(row=8,column=2)
master.geometry("400x150")
master.mainloop()

