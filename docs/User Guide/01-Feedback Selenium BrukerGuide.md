# Selenium Brukerguide
This is a documentation of how you get a project up and running in short time.

Open the link down below, and download and then open the project:
<br>
[Github Feedback Selenium Project](https://github.com/VaagenIM/02-frontend-med-flask-CallMeRubb/tree/main/VinnPremier)
***
## Setup
If you have downloaded and opened the project. Type in the following in your [terminal](https://www.jetbrains.com/help/pycharm/terminal-emulator.html).
```shell
pip install requirements.txt
```
<br>
Once all the plugins have been installed. Make sure to change the "Name" and "PhoneNum", so that the code is personally fit for your use.
You will find this line of code on row 98.
```python
#Telefon
send_keys('/html/body/div[4]/div/div/ul/li[23]/div[1]/div[2]/div[2]/input', os.getenv("Name" + "PhoneNum"))
click_element('/html/body/div[4]/div/div/ul/li[23]/div[1]/div[2]/div[3]')
```
<br> Code will now run 5 times, at the same time. Due to the default set 5 time multiprocessing. 
You can change this ,by changhign the numbmer that is visible down below, at ***"num_processes = 5"***

```python
if __name__ == '__main__':
    num_processes = 5
    while True:
```


