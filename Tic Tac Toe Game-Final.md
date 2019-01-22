
# Design the Game Board


```python
#Borad Frame
game=[[0,0,0],
     [0,0,0],
     [0,0,0]]

def display():
    print("|%i|%i|%i|"%(game[0][0], game[0][1],game[0][2]))
    print("-"*7)
    print("|%i|%i|%i|"%(game[1][0], game[1][1],game[1][2]))
    print("-"*7)
    print("|%i|%i|%i|"%(game[2][0], game[2][1],game[2][2]))

#Board Update
def board_update(game, player, row, col):
    game[row][col]=player
    display()
    return game
    
 #Define winners
def win():
    #Horizontal winn
    def hor():
        for row in game:
            if row[0]==row[1]==row[2] and row[0]!=0:
                print("player %i won"%row[0])
                print("Game over!")
                
    hor()
    
    #Vertical winner
    def ver():
        for i in range(len(game)):
            col=[]
            for row in game:
                col.append(row[i])
            if col[0]==col[1]==col[2] and col[0]!=0:
                print("player %i won"%row[0])
                print("Game over!")
    ver()

    
    #Diagonal winner \ orientation
    def diag1():
        diag=[]
        for i in range(len(game)):
            diag.append(game[i][i])
        if diag[0]==diag[1]==diag[2] and diag[0]!=0:
            print("player %i won"%game[0][0])
            print("Game over!")
       
           
    diag1()
    
    #Diagonal winner / orientation
    def diag2():
        diag=[]
        for i in range(len(game)):
            diag.append(game[i][len(game)-i-1])
        if diag[0]==diag[1]==diag[2] and diag[0]!=0:
            print("player %i won"%diag[0])
            print("Game over!")
           
    diag2()
    
    
#board_update(game, player=1, row=1, col=1)
```


```python
  i=1
while True:
    if i<=9:
        print("Please Player 1, play!")
        player=1
        while True:
            while True:
                row=int(input("enter the row you want to play. Choose in (0,1,2): "))
                if row in [0,1,2]:
                    break
                else:
                    print("The number you entered is out of range")

            while True:
                col=int(input("enter the col you want to play. Choose in (0,1,2): "))
                if col in [0,1,2]:
                    break
                else:
                    print("The number you entered is out of range")

            if game[row][col]==0:
                board_update(game, player, row, col)
                win()
                break
            else:
                print("The position is alredy taken. Please choose a different position")
                


        print("Please Player 2, play!")
        player=2
        while True:
            while True:
                row=int(input("enter the row you want to play. Choose in (0,1,2): "))
                if row in [0,1,2]:
                    break
                else:
                    print("The number you entered is out of range")

            while True:
                col=int(input("enter the col you want to play. Choose in (0,1,2): "))
                if col in [0,1,2]:
                    break
                else:
                    print("The number you entered is out of range")

            if game[row][col]==0:
                board_update(game, player, row, col)
                print(win())
                break
            else:
                print("The position is alredy taken. Please choose a different position")
               
        
        i+=1
    else:
        print("Game over!")
        break
    

```

    Please Player 1, play!
    
