# Python Task Level 1 :

Create a python function that takes 2 numbers x,y and prints 2 lists containing the odd and even numbers in
the x,y range
2. Create a python function that takes 2 numbers x,y and prints all the numbers between 1 and 100 than can
  be divided on x,y
3. Create a python function that takes 2 numbers x, y and prints the multiplication table from x to y
4. Create a function that takes a sentence and prints the sentence without duplicated words
5. Create a function that takes a sentence and prints how many words in the sentence (do not count the
  spaces)
6. Create a function that takes a sentence and word and remove the word from the sentence
7. Create a function takes a sentence and a word and prints how many time the word used in the sentence
8. Create a function that takes x,y and prints all the number that can be divide by y from x to 100

```py



class python_all_task:
    def __init__(self):

        while True:
                


            
            print('''
                  1-function to print 2 lists odd and even 
                  2-function prints all the numbers between 1 and 100 than can be divided on x,y
                  3-function that takes 2 numbers x, y and prints the multiplication table from x to y
                  4-function that takes a sentence and prints the sentence without duplicated words
                  5-function that takes a sentence and prints how many words in the sentence 
                  6-function that takes a sentence and word and remove the word from the sentence
                  7-function takes a sentence and a word and prints how many time the word used in the sentence
                  8-Create a function that takes x,y and prints all the number that can be divide by y from x to 100

                  9-exit ...

                  ''')
            num_choice=int(input("enter number form 1 - 8 to choose a function:"))
            if  num_choice==1:
                x=int(input("Enter  numbers X:" ))
                y=int(input("Enter  numbers Y:" ))
                self.odd_even_num(x,y)
                
            elif  num_choice==2:
                 x=int(input("enter first numer:"))
                 y=int(input("enter second numer:"))
                 self.divide_by_xy(x,y)
                 
            elif  num_choice==3:
                 x=int(input("enter first numer:"))
                 y=int(input("enter second numer:"))
                 self.multiplication(x,y)
                 
            elif  num_choice==4:
                 s=input("enter sentence:")
                 self.no_duplicate(s)

            elif  num_choice==5:
                 x=input("write a sentence: ")
                 self.count_word(x)

            elif  num_choice==6:
                 s=input("write a sentence:")
                 w=input("write a word: ")
                 self.remov_word(s,w)

            
            elif  num_choice==7:
                 s=input("write a sentence:")
                 w=input("write a word: ")
                 self.count_wordss(s,w)

            elif  num_choice==8:
                 x=int(input("enter first number :"))
                 y=int(input("enter second number :"))
                 self.divide_by_y(x,y)
                 
            elif  num_choice==9:
                print("log out..")
                break
            
            fun_again=input("prees any key to run functio again, n to exit:")
            if fun_again=="n":
                break

         







    def odd_even_num(self,x,y):
        o=[]
        e=[]
        for num in range(x,y):
            if num%2==0:
                e.append(num)
            else:
                o.append(num)
        print("even number",e)
        print("odd number",o)
        
        
    def divide_by_xy(slef,x,y):
        for i in range(1,101):
           if i%x==0 and i%y==0:
               print( i)
               
    def  multiplication(self,x,y):
        for i in range(x,y+1):
            for j in range(1,13):
                print(f"{i} X {j} = {i*j} ")

    def no_duplicate(self,sentence):
        new_sent=[]
        w=sentence.split(' ')
        for i in w:
            if i not in new_sent:
                new_sent.append(i)
   
        print( ' '.join(new_sent))
        

    def count_word(self,sentence):
        w=sentence.split(' ')
        print( len(w))

    

    def remov_word(self,sentence,word):
        new=sentence.split()
        removed_w=[]
        for i in new :
            if i != word:
                removed_w.append(i)
        print( ' '.join(removed_w)   )


    def count_wordss(self,sentence,word):
        new=sentence.split()
        count =0
        for i in new :
            if i.lower()== word.lower():
                count +=1
            
        print( count)

    
    def divide_by_y(self,x,y):
       for i in range(x,101):
           if i%y==0:
               print(i)




    





    


     


    
            


o=python_all_task()

```

