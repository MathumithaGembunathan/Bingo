# Bingo
~~~
def display(l):
  a=[l[i:i+5] for i in range(0,25,5)]
  print(tabulate.tabulate(a,tablefmt='fancy_grid'))         
def bingo(l):
  num=0
  while (num<26):
    num=int(input("Enter the number: "))
    for i in range(0,len(l)):
      if l[i]==num:
        l[i]=0
      elif l[i]==0:
        continue
      else:
        continue
      display(l)
      w=check_win(l)
      if w == 5:
        print("You won!")
        return 0
      print("Computer's turn: ")
      b=random.choice(l)
      print(b)
      for i in range (len(l)):
        while b==0:
          b=random.choice(l)
          print(b)
        if b==l[i]:
          l[i]=0
          break
      display(l)
      w=check_win(l)
      if w == 5:
        print("Computer won!")
        return 0
~~~
# MAIN PART
~~~
print("----------------------------------------------BINGO--------------------------------------------")
print("RULES:\n\t\t1.The goal is to be the first to get the score of 5.\n\t\t2.To start the game press 'n'\n\t\t3.To resume an old game press'c'\n\t\t4.To quit enter number greater than 25.\n\t\t5.To continue giving the input enter values between 1-25.")
print(" To start a new game press 'n' to continue old game press 'c'")
ch=input("Enter your choice: ")
if ch=='n':
  l=new_game()
  display(l)
  bingo(l)
elif ch=='c':
  display(l)
  bingo(l)
else:
  print("Thank you for ur time :)")
~~~
