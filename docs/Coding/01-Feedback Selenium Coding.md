# Automatic Feedback - Selenium
Before we start. Make sure you have Python downloaded, and running. If not, then make sure to go back on Homepage, and follow the steps on how to download Python. Also, be aware of that this is not written in pure Selenium code. This code has been simplified. 
***
## Plugins

First, we need to download our needed plugins via terminal, before we import them to our code.

```shell
pip install selenium
```
```shell
pip install multiprocessing
```
```shell
pip install python-dotenv 
```

<br>When plugins are installed, go ahead and import the needed plugins into your python code.
```shell
from selenium import webdriver
from selenium.webdriver.common.by import By
import time
import multiprocessing
import os
from dotenv import load_dotenv, dotenv_values
```
***
## WebDriver
We're going to start by making our Selenium open a browser. Use one of the supported web drivers down below, that you want to be using.
Remember to change ***"YOURSEARCHENGINE"***, to the webdriver that you want to be using. Also replace ***"YOURLINK"*** and add the link to the website you want to automate.

- Google Chrome
- Mozilla Firefox
- Safari
- Internet Explorer
- Microsoft Edge



```python
def run_selenium_code():
    driver = webdriver.YOURSEARCHENGINE()
    driver.get("YOURLINK")
```
***Example:***
```python
def run_selenium_code():
    driver = webdriver.Firefox()
    driver.get("https://google.com")
```
***
## Action Methods
This code handles clicking an element identified by the XPath. This is a smart way to make your code shorter, more clear and easier to code. 
This code will be standard, so there wont be anything to change here.

```python
    def click_element(xpath):
        while True:
            try:
                driver.find_element(By.XPATH, xpath).click()
                time.sleep(1)
                break
            except:
                time.sleep(0.1)
                continue


    def send_keys(xpath, keys):
        while True:
            try:
                driver.find_element(By.XPATH, xpath).send_keys(keys)
                time.sleep(1)
                break
            except:
                time.sleep(0.1)
                continue

    time.sleep(1)
```
***
## Elements
Elements are webpage components like buttons or text boxes that Selenium lets you find and control. With Selenium, you locate these parts and perform actions on them, such as clicking or entering text, enabling automation on websites. We suggest using XPath as used in this documentation. Some other common ones include:

- CSS Selectors
- ID
- Class Name 
- **XPath**
- Name
- Link Text and Partial Link Text
- Tag Name
- Accessibility Locators
***
### Click Element
In real Selenium code, you wouldn't directly use ***'click_element(' ')'*** But this is function written to simplify way to indicate the action of clicking on an element using its XPath locator. Remember to chagne ***"YOURXPATH"*** to the XPath you want to indicate and click.
```python
click_element('YOURXPATH')
```

***Example:***
```python
click_element('/html/body/div[4]/div[2]/div')
```
***
### Send Keys
This doesnt do the same as a Click Element function, but its intended to simplify your code as much. SendKEys function locates first a text box using XPath, and type in the following text that is entered. Change the text that you want to be written in ***"YOURTEXT"***. Remember to chagne ***"YOURXPATH"*** to the XPath you want to indicate and click.
```python
send_keys('YOURXPATH', 'YOURTEXT')
```
***Example:***
```python
send_keys('/html/div/ul/div/textarea', 'Hello World')
```

## iFrame
Not all websited uses iFrame, but they are quite common. Websites use iFrames to integrate external content or to segregate sections of a webpage. If so you need to change the iFrame you are using, so your code can find the XPath to the element you want to execute an action on.
```python
driver.switch_to.frame(driver.find_element(By.XPATH, 'YOURXPATHIFRAME'))
```
***Example:***
```python
driver.switch_to.frame(driver.find_element(By.XPATH, '/html/body/div[2]/div/iframe'))
```
***
## Parallel Selenium Runner
This code continously runs a loop where it sets the number of threads, to create threads for executing the ***'run_selenium_code()'*** function concurrently, waits for these threads to finish, increments a counter variable ***'f'*** by the number of threads and prints its value, then pauses the program for 0.2 seconds before restarting the loop. 
<br><br>Change ***"YOURNUMTHREADS"***, to how many times you want to simultaneously execute the Selenium code.
```python
if __name__ == '__main__':
    num_threads = YOURNUMTHREADS

    while True:
        threads = []

        for _ in range(num_threads):
            thread = threading.Thread(target=run_selenium_code())
            threads.append(thread)
            thread.start()

        for thread in threads:
            thread.join()

        f += (num_threads)
        print(f)
        time.sleep(0.2)
```
***Example:***
```python
if __name__ == '__main__':
    num_threads = 2

    while True:
        threads = []

        for _ in range(num_threads):
            thread = threading.Thread(target=run_selenium_code())
            threads.append(thread)
            thread.start()

        for thread in threads:
            thread.join()

        f += (num_threads)
        print(f)
        time.sleep(0.2)
```
GitHub

<br><br><br>