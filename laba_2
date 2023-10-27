from tkinter import *

def is_prime(num):
    if num <= 1:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True

def find_primes_in_range(min_value, max_value):
    primes = [num for num in range(min_value, max_value + 1) if is_prime(num)]
    return primes

def clicked():
    try:
        user_min = int(user_min_entry.get())
    except ValueError:
        result_text.insert("end", "Проверьте правильность переменных\n")

    try:
        user_max = int(user_max_entry.get())
    except ValueError:
        result_text.insert("end", "Проверьте правильность переменных\n")

    if user_min > user_max:
        result_text.insert("end", "Минимальное число больше максимального\n")

    prime_numbers = find_primes_in_range(user_min, user_max)

    result_text.delete(1.0, "end")  # Очистка текущего текста в виджете Text

    if prime_numbers:
        result_text.insert("end", f"Простые числа в диапазоне от {user_min} до {user_max}:\n")
        for prime in prime_numbers:
            result_text.insert("end", f"{prime} ")
        result_text.insert("end", "\n")
    else:
        result_text.insert("end", f"В заданном диапазоне от {user_min} до {user_max} нет простых чисел.")



window = Tk()
window.title("Вариант №1")
window.geometry('640x480')


mess1 = Label(window, text="От", font=("Calibri", 20)) #Сообщение для поля минимум
mess2 = Label(window, text="До", font=("Calibri", 20)) #Сообщение для поля максимум
mess3 = Label(window, text="Результат: ", font=("Calibri", 20))
user_min_entry = Entry(window, width=15) #Окно ввода минимума
user_max_entry = Entry(window, width=15) #Окно ввода максимума
btn = Button(window, text="Найти результат", command=clicked) #кнопка, по нажатию которой будет выведен ответ

result_text = Text(window, height=10, width=40)
result_text.grid(row=3, column=0, columnspan=2, sticky="nsew", padx=20, pady=20)  # Изменено columnspan и добавлены отступы

for i in range(4):  # Цикл для всех строк
    window.grid_rowconfigure(i, weight=1)
for i in range(2):  # Цикл для всех столбцов
    window.grid_columnconfigure(i, weight=1)

mess1.grid(row=0, column=0, padx=20, pady=10)
mess2.grid(row=1, column=0, padx=20, pady=10)
user_min_entry.grid(row=0, column=1, padx=20, pady=10)
user_max_entry.grid(row=1, column=1, padx=20, pady=10)
btn.grid(row=2, column=0, columnspan=2, pady=10)

window.mainloop()
