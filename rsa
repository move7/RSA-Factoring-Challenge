#!/usr/bin/python3
import sys
import math

def is_prime(num):
    if num < 2:
        return False
    if num == 2 or num == 3:
        return True
    if num % 2 == 0 or num % 3 == 0:
        return False
    for i in range(5, int(math.sqrt(num)) + 1, 6):
        if num % i == 0 or num % (i + 2) == 0:
            return False
    return True

def factorize(n):
    if n < 2:
        return None, None
    if n % 2 == 0:
        return 2, n // 2
    if n % 3 == 0:
        return 3, n // 3
    sqrt_n = int(math.sqrt(n)) + 1
    for i in range(5, sqrt_n, 6):
        if n % i == 0:
            if is_prime(i) and is_prime(n // i):
                return i, n // i
        if n % (i + 2) == 0:
            if is_prime(i + 2) and is_prime(n // (i + 2)):
                return i + 2, n // (i + 2)
    return None, None

def factorize_file(file_path):
    with open(file_path, 'r') as file:
        for line in file:
            number = int(line)
            factor1, factor2 = factorize(number)
            if factor1 and factor2:
                print(f"{number}={factor1}*{factor2}")
            else:
                print(f"{number}")

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: rsa <file>")
        sys.exit(1)

    file_path = sys.argv[1]
    factorize_file(file_path)
