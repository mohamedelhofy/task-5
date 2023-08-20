# task-5
table={
    1:' ',2:' ',3:' ',4:' ',
    5:' ',6:' ',7:' ',8:' ',
    9:' ',10:' ',11:' ',12:' ',
    13:' ',14:' ',15:' ',16:' '
    }
player1='o'
player2='x'
def printtable(table):
    print(table[1] + '|' + table[2] + '|' + table[3]+'|' + table[4])
    print('-+-+-+-')   
    print(table[5] + '|' + table[6] + '|' + table[7]+'|' + table[8])
    print('-+-+-+-')  
    print(table[9] + '|' + table[10] + '|' + table[11]+'|' + table[12]) 
    print('-+-+-+-')  
    print(table[13] + '|' + table[14] + '|' + table[15]+'|' + table[16])  
def ability(position):
        if table[position]==' ':
             return True  
        else:
            return False
def inserttable(kind , position) :   
        if  ability(position):
          table[position] =kind 
          printtable(table)
          if  checkdraw():
             print("Draw")
              
          if checkwin()  :      
            if kind == 'o' : 
                print( "Player1 win")
                 
            else  :
                 print( "Player2 win")
                
        else :
                  print("Can't insert there!")
                  position = int(input("Please enter new position:  "))
                  inserttable(kind , position) 
                  return 

def checkwin():
     if   (table[1]==table[2]==table[3]==table[4] and   table[1]!= ' '):
        return True  
     elif (table[5]==table[6]==table[7]==table[8] and   table[5]!= ' '):
        return True 
     elif (table[9]==table[10]==table[11]==table[12] and   table[11]!= ' '):
        return True 
     elif (table[13]==table[14]==table[15]==table[16] and   table[13]!= ' '):
        return True    
     elif (table[1]==table[5]==table[9]==table[13] and   table[13]!= ' '):
        return True 
     elif (table[2]==table[6]==table[10]==table[14] and   table[2]!= ' '):
        return True 
     elif (table[3]==table[7]==table[11]==table[15] and   table[15]!= ' '):
        return True  
     elif (table[4]==table[8]==table[12]==table[16] and   table[16]!= ' '):
        return True  
     elif (table[1]==table[6]==table[11]==table[16] and   table[16]!= ' '):
        return True  
     elif (table[4]==table[7]==table[10]==table[13] and   table[16]!= ' '):
        return True  
     else:
        return False 

def checkdraw()  :
    for key in table.keys():
        if (table[key] == ' '):
          return False
    return True  

def player1Move():
    position = int(input("Enter the position for 'O':  "))
    inserttable(player1 , position)
    return 

def player2Move():
    position = int(input("Enter the position for 'X':  "))
    inserttable(player2, position)
    return 

printtable(table) 

while True: 
      if  (checkwin() or  checkdraw() ) : 
          break
      player1Move()
      if  (checkwin() or  checkdraw() ) : 
          break
      player2Move()
