from random import choice
choice_list = ['win','lose','draw']
rating_dict = {}
count = 0
check = ['rock', 'paper', 'scissors']
win = {'rock':'scissors', 'paper':'rock', 'scissors':'paper'}
lose = {'rock':'paper', 'paper':'scissors', 'scissors':'rock'}
name = input('Enter your name : ')
print('Hello,',name)
score_file = open("rating.txt", "r")
for line in score_file:
    fname, score = line.split()
    rating_dict[fname] = int(score)
score_file.close()
user_score = rating_dict[fname] if name in rating_dict else 0
choice_l = input().split(',')
print("Okay, let's start")
if choice_l == ['']:
    while count == 0:
        user_choice = input()
        system_choice = choice(choice_list)
        if user_choice == '!exit':
            print('Bye!')
            break
        if user_choice == '!rating':
            print("Your rating:", user_score)
            continue
        if user_choice not in check:
            print("Invalid input")
            continue
        if system_choice == 'win':
            print(f'Well done. Computer chose {win[user_choice]} and failed')
            user_score += 100
        elif system_choice == 'lose':
            print(f'Sorry, but computer chose {lose[user_choice]}')
        elif system_choice == 'draw':
            print(f'There is a draw ({user_choice})')
            user_score += 50
else:
    half = ((len(choice_l)) + 1) // 2
    while count == 0:
        user_choice = input()
        system_choice = choice(choice_l)

        if user_choice == '!exit':
            print('Bye!')
            break
        if user_choice == '!rating':
            print("Your rating:", user_score)
            continue
        if user_choice not in choice_l:
            print("Invalid input")
            continue
        indx = choice_l.index(user_choice)
        temp = choice_l[indx:]
        temp1 = choice_l[:indx]
        #temp1.reverse()
        for item in temp1:
            temp.append(item)

        if user_choice == system_choice:
            print(f'There is a draw ({user_choice})')
            user_score += 50
        elif temp.index(user_choice) < temp.index(system_choice) < half:
            print(f'Sorry, but computer chose {system_choice}')
        else:
            print(f'Well done. Computer chose {system_choice} and failed')
            user_score += 100
