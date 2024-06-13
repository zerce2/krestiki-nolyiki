board = list(range(1,10))
def draw_board(board):
    print("-"*13)
    for i in range(3):
        print("|", board[i*3], "|",board[1+i*3], "|", board[2+i*3])
        print("-"*13)

def take_input(token):
    while True:
        answer = input(f"Куда поставим: {token}?\n")
        try:
            answer = int(answer)
        except:
            print("Некорректный ввод. Вы уверены, что ввели число?")
            continue
        if answer >= 1 and answer <= 9:
            if (str(board[answer-1]) not in 'XO'):
                board[answer-1] = token
                break
            else:
                print("Эта клеточка уже занята")
        else:
            print('Некорректный ввод. Введите число от 1-9')

            
def check_win(board):
    win_code = ((0,1,2),
               (3,4,5),
               (6,7,8),
               (0,4,8),
               (2,4,6),
               (0,3,6),
               (1,4,7),
               (2,5,8))
    for w in win_code:
        if board[w[0]] == board[w[1]] == board[w[2]]:
            return board[w[0]]
    return False

out = False
count = 0
while not out:
    draw_board(board)
    if count % 2 == 0:
        take_input("X")
    else:
        take_input("O")
    count+=1
    if count> 4:
        examination = check_win(board)
        if examination:
            print(f"{examination} выиграл!")
            out = True
    if count == 9:
        print("Ничья")
        out = True
