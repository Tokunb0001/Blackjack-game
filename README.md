# Blackjack-game
import random
logo = """
.------.            _     _            _    _            _    
|A_  _ |.          | |   | |          | |  (_)          | |   
|( \/ ).-----.     | |__ | | __ _  ___| | ___  __ _  ___| | __
| \  /|K /\  |     | '_ \| |/ _` |/ __| |/ / |/ _` |/ __| |/ /
|  \/ | /  \ |     | |_) | | (_| | (__|   <| | (_| | (__|   < 
`-----| \  / |     |_.__/|_|\__,_|\___|_|\_\ |\__,_|\___|_|\_\\
      |  \/ K|                            _/ |                
      `------'                           |__/           
"""

print(logo)

cards = [11,2,3,4,5,6,7,8,9,10,10,10,10]
user_card= [(random.randint(2,11)),(random.randint(2,11))]
computer_card = [(random.randint(2,11)),(random.randint(2,11))]
add_card = (random.randint(2,11))
print(user_card)
print(computer_card[0])
sum_user = sum(user_card)
print(sum_user)
sum_computer = sum(computer_card)
print(sum_computer)



""" To calculate the card og the blackjack we do run the below code"""
def calculating_cards():
    # if sum or card is 21 and have ace = 11, 
    if user_card == [10, 11] or user_card == [11,10] and sum_user == 21:
        print('You have a Blackjack')
        print('You Won')

    elif computer_card == [10, 11] or computer_card == [11,10] and sum_computer == 21:
        print('Computer has Blackjack')
        print('Computer won')

    """After checking the first condition we now check if the user score is over 21 or not """
    if sum_user>21:
        """we check if the user card contain ace or not"""
        if user_card == 11:
            for card in user_card:
                user_card.remove(11)
                return user_card.append(1)

    """so after checking if the sum of the card dor user is >21 then we have to check if aftyer replacing the ace with 1 are the still greater than 21"""
    if sum_user > 21:
        print('you loose computer wins try your luck next time ')

    else:
        """we ask the user if they want draw abother card"""
        user_question = input('Do you want to draw another card?  y or n')
        if user_question == 'y':
            user_card.append(add_card)

        if user_question == 'n':
            while sum_computer < 17:
                computer_card.append(add_card)

    if sum_computer>21:
        print('computer won')


def comparing_computer_and_user_score():
    if sum_user>sum_computer:
        print('computer win')
    elif sum_computer==sum_computer:
        print('you both draw')
    elif sum_user<sum_computer:
        print('computer looses so you are the winner')




calculating_cards()
comparing_computer_and_user_score()
