# Python Task Level 3

1. Build a countdown calculator. Write some code that can take two dates as input, and
   then calculate the amount of time between them

   ```py
   from datetime import datetime
   def countdown(start,end):
       format_date='%Y/%m/%d'
       start_d=datetime.strptime(start,format_date)
       end_d=datetime.strptime(end,format_date)
       time_left=end_d - start_d
       return time_left
   
   
   x=input("Enter date (yy/mm/dd)")
   y=input("Enter date (yy/mm/dd)")
   
   print( countdown(x,y))
   
   ```

   
   

2. Build an email slicer : create a function that takes an email as input and retrieve the
   username and domain of the email

   



```py
import re
email=input("enter your email address")
pattern = r"([\w]+)@([\w]+\.[\w]+)"
match=re.match(pattern,email)
username=match.group(1)
domain_name=match.group(2)

print("username:",username)
print("domain name:",domain_name)

```

