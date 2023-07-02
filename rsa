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
    if n % 2 == 0:
        return 2, n / 2
    if n % 3 == 0:
        return 3, n / 3
    if n % 5 == 0:
        return 5, n / 5
    x = y = 2
    d = 1
    f = lambda x: (x**2 + 1) % n
    while d == 1:
        x = f(x)
        y = f(f(y))
        d = math.gcd(abs(x - y), n)
    return d

def factorize_file(file_path):
    with open(file_path, 'r') as file:
        for line in file:
            number = int(line)
            p = factorize(number)
            if p != number:
                while not is_prime(p) and p != number:
                    p = pollard_rho(p)
            if p == number:
                print(f"{number}")
            else:
                print(f"{number}={p}*{number // p}")

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: rsa <file>")
        sys.exit(1)

    file_path = sys.argv[1]
    factorize_file(file_path)
