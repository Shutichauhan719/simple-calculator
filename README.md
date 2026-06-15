import tkinter as tk


window = tk.Tk()
window.title('calculator')
window.geometry('300x400')


# frame
frame1 = tk.Frame(window, bg='yellow', height=400, width=500)
frame1.place(anchor='w', relx=0.4, rely=0.3)


level1 = tk.Label(frame1, text='calculator', bg='darkred', fg='white')
level1.grid(pady=10, padx=10, row=0, columnspan=4)


level2 = tk.Label(frame1, text='Enter:', bg='blue', fg='red')
level2.grid(pady=10, row=1, padx=10, column=0)


entry = tk.Entry(frame1, bg='gray')
entry.grid(pady=10, row=1, padx=10, column=1)


# Clear all button
def but():
    entry.delete(0, tk.END)


button = tk.Button(frame1, text="DEL", command=but)
button.grid(pady=10, padx=10, row=2, column=0)


# Delete one by one button
def but1():
    v = len(entry.get())
    if v > 0:
        entry.delete(v - 1)


button1 = tk.Button(frame1, text="CL", command=but1)
button1.grid(pady=10, padx=10, row=2, column=1)


# Plus button
def but2():
    entry.insert(tk.END, '+')


button2 = tk.Button(frame1, text="+", command=but2)
button2.grid(pady=10, padx=10, row=2, column=2)


# Minus button
def but3():
    entry.insert(tk.END, '-')


button3 = tk.Button(frame1, text="-", command=but3)
button3.grid(pady=10, padx=10, row=2, column=3)


# Add 1
def add1():
    entry.insert(tk.END, '1')


ad1 = tk.Button(frame1, text="1", command=add1)
ad1.grid(pady=10, padx=10, row=3, column=0)


# Add 2
def add2():
    entry.insert(tk.END, '2')


ad2 = tk.Button(frame1, text="2", command=add2)
ad2.grid(pady=10, padx=10, row=3, column=1)


# Add 3
def add3():
    entry.insert(tk.END, '3')


ad3 = tk.Button(frame1, text="3", command=add3)
ad3.grid(pady=10, padx=10, row=3, column=2)


# Multiply
def but4():
    entry.insert(tk.END, '*')


button4 = tk.Button(frame1, text="*", command=but4)
button4.grid(pady=10, padx=10, row=3, column=3)


# Add 4
def add4():
    entry.insert(tk.END, '4')


ad4 = tk.Button(frame1, text="4", command=add4)
ad4.grid(pady=10, padx=10, row=4, column=0)


# Add 5
def add5():
    entry.insert(tk.END, '5')


ad5 = tk.Button(frame1, text="5", command=add5)
ad5.grid(pady=10, padx=10, row=4, column=1)


# Add 6
def add6():
    entry.insert(tk.END, '6')


ad6 = tk.Button(frame1, text="6", command=add6)
ad6.grid(pady=10, padx=10, row=4, column=2)


# Divide
def but5():
    entry.insert(tk.END, '/')


button5 = tk.Button(frame1, text="/", command=but5)
button5.grid(pady=10, padx=10, row=4, column=3)


# Add 7
def add7():
    entry.insert(tk.END, '7')


ad7 = tk.Button(frame1, text="7", command=add7)
ad7.grid(pady=10, padx=10, row=5, column=0)


# Add 8
def add8():
    entry.insert(tk.END, '8')


ad8 = tk.Button(frame1, text="8", command=add8)
ad8.grid(pady=10, padx=10, row=5, column=1)


# Add 9
def add9():
    entry.insert(tk.END, '9')


ad9 = tk.Button(frame1, text="9", command=add9)
ad9.grid(pady=10, padx=10, row=5, column=2)


# Modulo
def but6():
    entry.insert(tk.END, '%')


button6 = tk.Button(frame1, text="%", command=but6)
button6.grid(pady=10, padx=10, row=5, column=3)


# Final output
def final():
    z = entry.get()
    try:
        result = eval(z)
        entry.delete(0, tk.END)
        entry.insert(tk.END, str(result))
    except:
        entry.delete(0, tk.END)
        entry.insert(tk.END, 'Error')


button7 = tk.Button(frame1, text="=", command=final)
button7.grid(pady=10, padx=10, row=6, column=0, columnspan=4)


window.mainloop()
