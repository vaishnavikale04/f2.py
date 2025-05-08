from tkinter import *

def click(event):
    global expression
    expression += str(event.widget["text"])
    input_text.set(expression)

def clear():
    global expression
    expression = ""
    input_text.set("")

def evaluate():
    global expression
    try:
        result = str(eval(expression))
        input_text.set(result)
        expression = result
    except:
        input_text.set("Error")
        expression = ""

expression = ""
root = Tk()
root.title("Calculator")
input_text = StringVar()

input_frame = Frame(root)
input_frame.pack()

input_field = Entry(input_frame, textvariable=input_text, width=25, font=('arial', 18, 'bold'), bd=5, insertwidth=4, bg="powder blue", justify='right')
input_field.grid(row=0, column=0, columnspan=4)

buttons = [
    ['7', '8', '9', '/'],
    ['4', '5', '6', '*'],
    ['1', '2', '3', '-'],
    ['0', '.', '=', '+']
]

for i, row in enumerate(buttons):
    for j, char in enumerate(row):
        button = Button(root, text=char, padx=20, pady=20, bd=8, fg="black", font=('arial', 18, 'bold'))
        button.grid(row=i+1, column=j)
        if char == '=':
            button.bind("<Button-1>", lambda e: evaluate())
        elif char == 'C':
            button.bind("<Button-1>", lambda e: clear())
        else:
            button.bind("<Button-1>", click)

root.mainloop()
