# Tic Tac Toe Game

board = [' ' for _ in range(9)]

def display_board():
    print()
    print(board[0] + " | " + board[1] + " | " + board[2])
    print("--+---+--")
    print(board[3] + " | " + board[4] + " | " + board[5])
    print("--+---+--")
    print(board[6] + " | " + board[7] + " | " + board[8])
    print()

def check_winner(player):
    winning_positions = [
        (0, 1, 2),
        (3, 4, 5),
        (6, 7, 8),
        (0, 3, 6),
        (1, 4, 7),
        (2, 5, 8),
        (0, 4, 8),
        (2, 4, 6)
    ]

    for a, b, c in winning_positions:
        if board[a] == board[b] == board[c] == player:
            return True

    return False

def check_draw():
    return ' ' not in board

# Main game
print("TIC TAC TOE")
print("Player 1 = X")
print("Player 2 = O")

current_player = 'X'

while True:
    display_board()

    try:
        position = int(input("Player " + current_player +
                             ", enter position (1-9): ")) - 1

        if position < 0 or position > 8:
            print("Please enter a number from 1 to 9.")
            continue

        if board[position] != ' ':
            print("Position already occupied. Try again.")
            continue

        board[position] = current_player

        if check_winner(current_player):
            display_board()
            print("Player " + current_player + " wins!")
            break

        if check_draw():
            display_board()
            print("The game is a draw!")
            break

        # Change player
        if current_player == 'X':
            current_player = 'O'
        else:
            current_player = 'X'

    except ValueError:
        print("Please enter a valid number.")
