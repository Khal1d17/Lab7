import random
n = int(input("Massivin element sayını daxil edin: "))
lower_bound = int(input("Minimum dəyəri daxil edin: ")) 
upper_bound = int(input("Maksimum dəyəri daxil edin: ")) 
numbers = [random.randint(lower_bound, upper_bound) for _ in range(n)]
with open("numbers.txt", "w") as file:
    for num in numbers:
        file.write(str(num) + "\n")
odd_sum = 0
new_numbers = []
with open("numbers.txt", "r") as file:
    for line in file:
        number = int(line.strip())
        if number % 2 != 0:
            odd_sum += number
            new_numbers.append(number * 2) 
        else:
            new_numbers.append(number)
with open("new_numbers.txt", "w") as new_file:
    for num in new_numbers:
        new_file.write(str(num) + "\n")
print("Tək nömrələrin cəmi:", odd_sum)
