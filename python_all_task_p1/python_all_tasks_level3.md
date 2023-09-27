# Python Task Level 3

1. Build a countdown calculator. Write some code that can take two dates as input, and
   then calculate the amount of time between them

   ```py
   from datetime import datetime
   
   
   
   def countdown(start_date, end_date,format_str):
        
       start_datetime = datetime.strptime(start_date, "%Y-%m-%d %H:%M:%S")
       end_datetime = datetime.strptime(end_date, "%Y-%m-%d %H:%M:%S")
   
       time_difference = end_datetime - start_datetime
   
   
       years = time_difference.days // 365
       months = (time_difference.days % 365) // 30
       days = (time_difference.days % 365) % 30
       hours = time_difference.seconds // 3600
       minutes = (time_difference.seconds % 3600) // 60
       seconds = (time_difference.seconds % 3600) % 60
       time_dict = {
           'years': years,
           'months': months,
           'days': days,
           'hours': hours,
           'minutes': minutes,
           'seconds': seconds
       }
   
       formatted_time = format_str.format(**time_dict)
       return formatted_time
   
   format_str = "{years} years, {months} months, {days} days, {hours} hours, {minutes} minutes, {seconds} seconds"
   
   start_t=input("enter start date :")
   end_t=input("enter end date :")
   print(countdown(start_t,end_t,format_str))
   
   
   
   
   
   
   
   
   
   ```

   

2. Make a temperature/measurement converter. Write a script that can convert
   Fahrenheit to Celcius and back, or inches to centimeters and back, etc in 3 dierent
   ways

   ```py
   
   
   class  temperature_measuremen_converter:
       def __init__(self):
   
           while True:
                   
               print(""" 
                   temperature/measurement converter:
                       1- convert Fahrenheit to Celcius
                       2-convert Celcius to Fahrenheit
                       3-convert inches to centimeters
                       4-convert centimeters to inches
                       5-Exit
   
                   """)
               input_number=int(input("Choose number from above: "))
   
               if input_number ==1:
                   f=int(input("Enter Fahrenheit : "))
                   self.fahrenheit_to_celsius(f)
                           
   
               elif input_number ==2:
                   c=int(input("Enter Celsius : "))
                   self.celsius_to_fahrenheit(c)     
   
               elif input_number ==3:
                   i=int(input("Enter Inches : "))
                   self.inches_to_centimeters(i)     
               
               elif input_number ==4:
                   c=int(input("Enter Inches : "))
                   self.centimeters_to_inches(c)      
   
               elif input_number==5:
                   print("......")
                   return
               paly_again=input("""
                                 enter any key to continue ... 
                                 enter (e) to exit""")
               if paly_again=='e':
                   break
               
       def fahrenheit_to_celsius(self,f):
           print( (f -32)* 5/9)
   
       def celsius_to_fahrenheit(self,c):
           print( (c* 9/5)+32)
   
       def inches_to_centimeters(self,inches):
           print(inches * 2.54)
   
       def centimeters_to_inches(self,centimeters):
           print(centimeters / 2.54)
   
   
   o=temperature_measuremen_converter()
   
   ```
   
   
   
   ```py
   import pint 
   
   class  temperature_measuremen_converter:
       
           
       def __init__(self):
   
           self.ureg=pint.UnitRegistry()
   
   
           while True:
                   
               print("""
                   temperature/measurement converter:
                       1- convert Fahrenheit to Celcius
                       2-convert Celcius to Fahrenheit
                       3-convert inches to centimeters
                       4-convert centimeters to inches
                       5-Exit
   
                   """)
               input_number=int(input("Choose number from above: "))
   
               if input_number ==1:
                   f=int(input("Enter Fahrenheit : "))
                   self.fahrenheit_to_celsius(f)
                           
   
               elif input_number ==2:
                   c=int(input("Enter Celsius : "))
                   self.celsius_to_fahrenheit(c)     
   
               elif input_number ==3:
                   i=int(input("Enter Inches : "))
                   self.inches_to_centimeters(i)     
               
               elif input_number ==4:
                   c=int(input("Enter Inches : "))
                   self.centimeters_to_inches(c)      
   
               elif input_number==5:
                   print("......")
                   return
               paly_again=input("""
                                 enter any key to continue .. 
                                 enter (e) to exit""")
               if paly_again=='e':
                   break
               
       def fahrenheit_to_celsius(self,f):
           print((f * self.ureg.degF).to(self.ureg.degC)) 
   
       def celsius_to_fahrenheit(self,c):
            return (c*self.ureg.degC).to(self.ureg.degF)
   
   
       def inches_to_centimeters(self,inches):
           return (inches * self.ureg.inch).to(self.ureg.centimeter)
           
   
       def centimeters_to_inches(self,centim):
           return (centim * self.ureg.centimeter).to(self.ureg.inch)
   
   
   o=temperature_measuremen_converter()
   
   
   
   ```
   
   
   
3. Build an email slicer : create a function that takes an email as input and retrieve the
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

   

   

   

   

4. Currency converter : create a python script that takes a money with currency sign and
   convert it to some other currencies , the code should be like the game we did before

   

   

```py
import requests

class RealTimeCurrencyConverter():
    
    def __init__(self,url):

        while True:


            self.data= requests.get(url).json()
            self.currencies = self.data['rates']
            print('''
                    1-To convert currency write your currency 
                    2:to exist 
                    ''')
                
        

            use_choice=int(input("enter number ( 1 ) to start convert currency: "))
            if use_choice==1: 
                from_c=input("From currency :")
                to_c=input("to currency :")
                amount=int(input("amount :"))
                f_c=from_c.upper()
                t_c=to_c.upper()
                self.convert(f_c,t_c,amount)
            
            elif use_choice==2: 
                print('Goodby....')
                return
            
            convert_again=input("prees any key to convert again, n to exit:")
            if convert_again=="n":
                break
                        

    def convert(self, from_currency, to_currency, amount): 
        initial_amount = amount  
        if from_currency != 'USD' : 
            amount = amount / self.currencies[from_currency] 
    
        amount = round(amount * self.currencies[to_currency], 4) 
        print(amount ) 


url='https://api.exchangerate-api.com/v4/latest/USD'
converter = RealTimeCurrencyConverter(url)






```





