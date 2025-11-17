import random
import time
import os

def clear():
    os.system("cls" if os.name == "nt" else "clear")

def make_galaxy(size=25, density=0.08):
    galaxy = []
    for _ in range(size):
        row = []
        for _ in range(size):
            if random.random() < density:
                row.append(random.choice(["*", ".", "o", "+"]))
            else:
                row.append(" ")
        galaxy.append(row)
    return galaxy

def show_galaxy(galaxy):
    for row in galaxy:
        print("".join(row))

# animated galaxy
for _ in range(60):
    clear()
    g = make_galaxy()
    show_galaxy(g)
    time.sleep(0.05)
