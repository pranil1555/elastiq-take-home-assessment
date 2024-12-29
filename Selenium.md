import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC


def test_table_sort_search_demo():
    
    driver = webdriver.Chrome()
    driver.maximize_window()

    try:
        
        URL = "https://www.lambdatest.com/selenium-playground/table-sort-search-demo"
        driver.get(URL)

        
        wait = WebDriverWait(driver, 10)
        search_box = wait.until(EC.visibility_of_element_located((By.CSS_SELECTOR, "#example_filter > label > input[type=search]")))

        
        search_query = "software engineer"
        search_box.send_keys(search_query)
        print("successfully 1")

        search_query = "Auditor"
        search_box.send_keys(search_query)
        print("successfully 2")

        search_query="Edinburgh	"
        search_box.send_keys(search_query)
        print("successfully 3")

        search_query="Williamson"
        search_box.send_keys(search_query)
        print("successfully 4")

        search_query="Senior Javascript Developer"
        search_box.send_keys(search_query)
        print("successfully 5")


    finally:
        
        driver.quit()
