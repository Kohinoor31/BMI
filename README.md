# BMI
import tkinter as tk

def calculate_bmi():
    weight = float(weight_entry.get())
    height = float(height_entry.get())
    bmi = weight / (height ** 2)
    bmi_label.config(text=f"Your BMI is: {bmi:.2f}")
    category_label.config(text=f"Category: {classify_bmi(bmi)}")

def classify_bmi(bmi):
    if bmi < 18.5:
        return "Underweight"
    elif bmi >= 18.5 and bmi < 25:
        return "Normal weight"
    elif bmi >= 25 and bmi < 30:
        return "Overweight"
    else:
        return "Obese"

root = tk.Tk()
root.title("BMI Calculator")

weight_label = tk.Label(root, text="Enter your weight in kilograms:")
weight_label.grid(row=0, column=0, padx=10, pady=5, sticky="w")

weight_entry = tk.Entry(root)
weight_entry.grid(row=0, column=1, padx=10, pady=5)

height_label = tk.Label(root, text="Enter your height in meters:")
height_label.grid(row=1, column=0, padx=10, pady=5, sticky="w")

height_entry = tk.Entry(root)
height_entry.grid(row=1, column=1, padx=10, pady=5)

calculate_button = tk.Button(root, text="Calculate BMI", command=calculate_bmi)
calculate_button.grid(row=2, column=0, columnspan=2, pady=10)

bmi_label = tk.Label(root, text="")
bmi_label.grid(row=3, column=0, columnspan=2)

category_label = tk.Label(root, text="")
category_label.grid(row=4, column=0, columnspan=2)

root.mainloop()
