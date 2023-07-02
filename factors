#!/usr/bin/python3
import sys

def factorize_number(number):
    for divisor in range(2, int(number**0.5) + 1):
        if number % divisor == 0:
            return divisor, int(number/divisor)
    return None, None

def factorize_file(file_path):
    with open(file_path, 'r') as file:
        for line in file:
            number = int(line.strip())
            factor1, factor2 = factorize_number(number)
            if factor1 and factor2:
                print(f"{number} = {factor1} * {factor2}")

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: factors <file>")
        sys.exit(1)

    file_path = sys.argv[1]
    factorize_file(file_path)
    sys.exit(1)

