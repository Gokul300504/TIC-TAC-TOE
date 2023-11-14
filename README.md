# TIC-TAC-TOE
In this repository i will be providing the code for a multiplayer one on one tic tact toe based on python

SOURCE CODE:

def show():
    for i in range(3):
        for j in range(3):
            print(tic[i][j],end='|')
        print()



tic = [
    [' ',' ',' '],
    [' ',' ',' '],
    [' ',' ',' ']
]

ct=1
p = 'x'
hasnotwon=True

while hasnotwon:
    show()
    x=int(input("Player {}:".format(p)))

    if not 0<= x <= 9:
        print("enter value within 0 and 9")
        continue
    
    r=(x-1)//3
    c=(x-1) % 3

    print("Value entered is ",x,"In row",r,"In column",c)

    if tic[r][c]=='x' or tic[r][c] == '0':
        print("try again")
        continue

    tic[r][c]=p
    
    for i in range(3):
        if tic[i][0]==tic[i][1]==tic[i][2] and tic[i][0] in ('x','O'):#row
            print("{} has won".format(tic[0][0]))
            hasnotwon=False
        if tic[0][i]==tic[1][i]==tic[2][i] and tic[i][0] in ('x','O'):#column
            print("{} has won".format(tic[0][0]))
            hasnotwon=False
    if tic[1][1]==tic[0][0]==tic[2][2] and tic[1][1] in ('x','O'):#diagonal1
            print("{} has won".format(tic[0][0]))
            hasnotwon=False
    if tic[1][1]==tic[0][2]==tic[2][0] and tic[1][1] in ('x','O'):#diagonal2
            print("{} has won".format(tic[0][0]))
            hasnotwon=False
    if ct==9:
         print("THE MATCH IS A DRAW")
         break
    print()
    ct+=1
    if p=='x':
        p='o'
    else:
        p='x'
if hasnotwon==False:
     show()
     print("")


OUTPUT :

 | | |
 | | |
 | | |
Player x:1
Value entered is  1 In row 0 In column 0

x| | |
 | | |
 | | |
Player o:4
Value entered is  4 In row 1 In column 0

x| | |
o| | |
 | | |
Player x:2
Value entered is  2 In row 0 In column 1

x|x| |
o| | |
 | | |
Player o:7
Value entered is  7 In row 2 In column 0

x|x| |
o| | |
o| | |
Player x:3
Value entered is  3 In row 0 In column 2
x has won

x|x|x|
o| | |
o| | |
