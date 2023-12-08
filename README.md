# GBHW12.12

def copy_line(source_file, destination_file, line_number):
    try:
        with open(source_file, 'r', encoding='utf-8') as file:
            lines = file.readlines()
            if line_number <= len(lines):
                with open(destination_file, 'a', encoding='utf-8') as dest_file:
                    dest_file.write(lines[line_number - 1])
                print(f"Строка {line_number} была скопирована из {source_file} в {destination_file}")
            else:
                print(f"Строки с номером {line_number} нет в файле {source_file}")
    except FileNotFoundError:
        print("Ошибка: Один из файлов не найден")

source_file = "source.txt"  # название исходного файла
destination_file = "destination.txt"  # название файла, в который будет производиться копирование
line_number = int(input("Введите номер строки для копирования: "))
copy_line(source_file, destination_file, line_number)
