from tkinter import *
from tkinter import messagebox

# restarting the entrys
def reset_entry():
    age_tf.delete(0, 'end')
    height_tf.delete(0, 'end')
    weight_tf.delete(0, 'end')

# calculator of the bmi
def calculate_bmi():
    try:
        kg = int(weight_tf.get())
        m = int(height_tf.get()) / 100
        bmi = kg / (m * m)
        bmi = round(bmi, 1)
        bmi_index(bmi)
    except:
        messagebox.showinfo('Error', 'Please make sure you have filled everything')

# bmi indexes
def bmi_index(bmi):
    if bmi < 18.5:
        messagebox.showinfo('bmi status', f'BMI = {bmi} is Underweight')
    elif (bmi > 18.5) and (bmi < 24.9):
        messagebox.showinfo('bmi status', f'BMI = {bmi} is Normal')
    elif (bmi > 24.9) and (bmi < 29.9):
        messagebox.showinfo('bmi status', f'BMI = {bmi} is Overweight')
    elif (bmi > 29.9):
        messagebox.showinfo('bmi status', f'BMI = {bmi} is Obesity')
    else:
        messagebox.showerror('bmi status', 'something went wrong!')

# creating the tkinter
root = Tk()
root.title('BMI Calculator')
root.geometry('400x300')
root.config(bg='#686e70')

var = IntVar()

frame = Frame(root,padx=10,pady=10)
frame.pack(expand=True)

# age text label
age_lb = Label(frame,text="Enter Age (2 - 120)")
age_lb.grid(row=1, column=1)

# age entry label
age_tf = Entry(frame)
age_tf.grid(row=1, column=2, pady=5)

# gender text label
gen_lb = Label(frame,text='Select Gender')
gen_lb.grid(row=2, column=1)

# gender options label
frame2 = Frame(frame)
frame2.grid(row=2, column=2, pady=5)
male_rb = Radiobutton(frame2,text='Male',variable=var,value=1)
male_rb.pack(side=LEFT)
female_rb = Radiobutton(frame2,text='Female',variable=var,value=2)
female_rb.pack(side=RIGHT)

# height text label
height_lb = Label(frame,text="Enter Height (cm)  ")
height_lb.grid(row=3, column=1)
# weight text label
weight_lb = Label(frame,text="Enter Weight (kg)  ")
weight_lb.grid(row=4, column=1)

# height entry label
height_tf = Entry(frame)
height_tf.grid(row=3, column=2, pady=5)

# weight entry label
weight_tf = Entry(frame)
weight_tf.grid(row=4, column=2, pady=5)

frame3 = Frame(frame)
frame3.grid(row=5, columnspan=3, pady=10)

# calculate button
cal_btn = Button(frame3, text='Calculate',command=calculate_bmi)
cal_btn.pack(side=LEFT)

# reset button
reset_btn = Button(frame3,text='Reset',command=reset_entry)
reset_btn.pack(side=LEFT)

# exit button
exit_btn = Button(frame3,text='Exit',command=lambda: root.destroy())
exit_btn.pack(side=RIGHT)

root.mainloop()
