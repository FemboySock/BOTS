from selenium import webdriver
import random
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
import time

url = "https://bombparty.netlify.app/"
jklm = "https://bombparty-clone.fly.dev/MTSN"
chrome_options = webdriver.ChromeOptions()
chrome_options.add_experimental_option("detach", True)


driver = webdriver.Chrome(options=chrome_options)
driver.get(url=url)


# Bomb Party
game = webdriver.Chrome(options=chrome_options)
game.get(url=jklm)
time.sleep(1)
join_button = game.find_element(By.XPATH, '//*[@id="root"]/div[2]/div/div[1]/div/div[1]/div[1]/button')
join_button.click()
time.sleep(1)
start_game = game.find_element(By.XPATH, '//*[@id="root"]/div[2]/div/div[1]/div/div[1]/div[1]/button[2]')
start_game.click()
time.sleep(6)


for numbie in range(50):
    time.sleep(1)
    text = game.find_element(By.XPATH, '//*[@id="root"]/div[2]/div/div[1]/div/div[1]/div[3]/div[1]')
    syllables = text.text.lower()
    search = driver.find_element(By.XPATH, '//*[@id="main"]/input')
    search.click()

    search.send_keys(syllables)
    time.sleep(1)
    word_list = driver.find_element(By.CLASS_NAME, 'words').text.split()

    print(word_list)
    search.click()
    for x in range(5):
        search.send_keys(Keys.ARROW_LEFT)
        search.send_keys(Keys.DELETE)
    word_list_storage = []
    for x in word_list:
        if syllables in x:
            word_list_storage.append(x)

    typing = game.find_element(By.XPATH, '//*[@id="root"]/div[2]/div/div[1]/div/div[1]/div[3]/form/input')
    typing.click()
    typing.send_keys(random.choice(word_list_storage))
    typing.send_keys(Keys.ENTER)
# ------------------------------------------------------------------------------------
