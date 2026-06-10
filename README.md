
# Задание task_03_03_08.
#
# Выполнил: Павлова Е.А.
# Группа: ЦИБ-251



"""
Ошибки (номера строк через пробел, данная строка - №2): !!!
"""


# Дан список ФИО. Найти наиболее часто встречаемое отчество.
# Если отчества нет, человек не учитывается в подсчете.

n = int(input("Введите кол-во человек: "))

middle_names = {}
for i in range(n):
    fio = input("Введите ФИО через пробел: ").split()
    try:
        middle_name = fio[2]
        middle_names[middle_name] = middle_names.get(middle_name, 0) + 1
    except IndexError:
        continue
try:
    print(sorted(middle_names.items(), key=lambda item: item[1])[-1][0])
except IndexError:
    print("Нет отчеств для подсчёта")
print("В расчете участвовало человек:", n)


# Другой код, с определёнными нюансами

# Дан список ФИО. Найти наиболее часто встречаемое отчество.
# Если отчества нет, человек не учитывается в подсчете.

n = int(input("Введите кол-во человек: "))

middle_names = {}
for i in range(n):
    fio = input("Введите ФИО через пробел: ").split()
    try:
        middle_name = fio[2]
        middle_names[middle_name] = middle_names.get(middle_name, 0) + 1
    except IndexError:
        continue
if not middle_names:
    print("Нет отчеств для подсчёта")
else:
    if max(middle_names.values()) == 1:
        print("Все отчества разные")
    else:
        print(sorted(middle_names.items(), key=lambda item: item[1])[-1][0])
print("В расчете участвовало человек:", n)
count = sum(middle_names.values())
print("В расчете участвовало человек(имеющих отчество):", count)
