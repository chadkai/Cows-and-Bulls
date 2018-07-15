# Cows-and-Bulls

Simple simulation of a cows and bulls game

import random
randNum = str(random.randint(1000, 9999))
randList = list(randNum)
print(randList)
while True:
    playerInput = input("Input your guess: ")
    
    try:
        playerInput = int(playerInput)
    except ValueError:
        print("That's not an integer!")
    if len(str(playerInput)) > 4:
        print("Please enter a valid 4 digit guess.")
    playerList = list(str(playerInput))
    
    c = 0
    b = 0
    
    if playerList != randList:
        for i in playerList:
            if i in randList:
                if playerList.index(i) == randList.index(i):
                    c += 1
                else:
                    b += 1
        print("Cows: {}, Bulls: {}".format(c,b))
        continue
    else:
        print("You got the correct answer!")
        break

