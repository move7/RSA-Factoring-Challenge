#!/usr/bin/python3
import sys
from math import gcd

def pollards_rho_factorize(n):
    if n % 2 == 0:
        return 2, n / 2
    if n % 3 == 0:
        return 3
    if n % 5 == 0:
        return 5
    x = 2
    y = 2
    d = 1

    f = lambda x: (x**2 + 1) % n

    while d == 1:
        x = f(x)
        y = f(f(y))
        d = gcd(abs(x - y), n)

    if d == n:
        return 1, n

    return d, n // d

def factorize_file(file_path):
    with open(file_path, 'r') as file:
        for line in file:
            number = int(line)
            factor1, factor2 = pollards_rho_factorize(number)
            print(f"{number}={factor1}*{factor2}")

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: factors <file>")
        sys.exit(1)

    file_path = sys.argv[1]
    factorize_file(file_path)

