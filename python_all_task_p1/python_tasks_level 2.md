# Python Task Level 2 :

**Names = ["mahmoud","farida","ali","hassan","mohamed","khaled","taha"]**
**Using the names list above create a python code that :**

1. Transform all names to uppercase using [normal list - list comprehension - functional programming]

   ```py
   
   
   Names = ["mahmoud","farida","ali","hassan","mohamed","khaled","taha"]
   
   new=[]
   for x in Names:
       
       new.append(x.upper())
   print (new)
   
   x=[x.upper() for x in Names]
   print(x)
   
   
   def upper_names(name):
       return name.upper()
   
   result=map(upper_names,Names)
       
   print(list(result))
   
   ```

   

2. Get the names that contains ‘a’ in a list using [normal list - list comprehension - functional
   programming]

   ```py
   
   Names = ["mahmoud","farida","ali","hassan","mohamed","khaled","taha","noor"]
   
   
   result= []
   for n in Names:
       if 'a' in n:
           result.append(n)
   print(result)
   
   
   result=[x for x in Names if 'a' in x]
   print(result)
   
   
   
   
   result=filter(lambda x: 'a' in x,Names)
   print(list(result))
   
   ```

   

   

3. Get the names that starts with ‘t’ in a list using [normal list - list comprehension - functional
   programming]

   ```py
   
   
   Names = ["mahmoud","farida","ali","hassan","mohamed","khaled","taha","noor"]
   
   new=[]
   for i in Names:
       if i[0] == 't':
           new.append(i)
   print(new)    
   
   
   
   
   result=[x for x in Names if x[0]=='t']
   print(result)
   
   
   
   result=filter(lambda x:x[0]=='t' ,Names)
   print(list(result))
   
   ```

   

4. Get the names that contains 2 or more ‘a’ letter using [normal list - list comprehension - functional
   programming]

   ```py
   Names = ["mahmoud","farida","ali","hassan","mohamed","khaled","taha","noor"]
   result= []
   
   for n in Names:
       if n.count('a')>=2:
           result.append(n)
           
   print(result)
   
   
   
   result=[x for x in Names if x.count('a')>=2]
   print(result)
   
   
   
   
   result=filter(lambda x: x.count('a') >=2 ,Names)
   print(list(result))
   ```

   

5. Print a list contains the len of each word in the list using [normal list - list comprehension -
   functional programming]

   

   ```py
   
   Names = ["mahmoud","farida","ali","hassan","mohamed","khaled","taha","noor"]
   
   
   
   result= []
   for n in Names:
       result.append(len(n))
           
   print(result)
   
   
   
   result=[len(x)  for x in Names ]
   print(result)
   
   
   def lenght(word):
       return len(word)
   
   
   result=map(lenght,Names)
   print(list(result))
   
   ```

   

6. Unpack the list in

7. a,b , a= the first index , b = rest of the list

8. a = the first index , b = the last index

9. a = the first index , b = the second index

   ```py
   Names = ["mahmoud","farida","ali","hassan","mohamed","khaled","taha","noor"]
   a,*b=Names
   SyntaxError: multiple statements found while compiling a single statement
   a, *b=Names
   a
   'mahmoud'
   b
   ['farida', 'ali', 'hassan', 'mohamed', 'khaled', 'taha', 'noor']
   
   ####*8*####
   a,*_,b=Names
   a
   'mahmoud'
   b
   'taha'
   ####*9*####
   a,b,*_=Names
   a
   'mahmoud'
   b
   'farida'
   
   
   
   
   ```

   