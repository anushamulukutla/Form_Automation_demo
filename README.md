# Form_Automation_demo
This repository is for practice, where I automate the process of filling out and submitting a web form using **Selenium** and **Python**. The purpose is to gain hands-on experience with web automation techniques.
# Web Automation Project

This project demonstrates how to automate web interactions using **Selenium WebDriver** in **Python**. The automation script performs tasks such as filling forms, interacting with buttons, checkboxes, radio buttons, and extracting web content.

## Features

- **Form Filling:** Automates the process of filling out web forms.
- **Checkbox and Radio Button Selection:** Automatically selects checkboxes and radio buttons based on predefined inputs.
- **Dropdown Interaction:** Selects options from dropdown menus.
- **Web Scraping:** Extracts web data such as text and attributes of various HTML elements.
- **Automation of Common Web Tasks:** Simulates user actions such as clicks, keyboard input, and form submission.

## Requirements

- **Python 3.x**
- **Selenium WebDriver**
- **ChromeDriver** (if using Chrome as your browser)
- A web browser (Chrome or Firefox)

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/automation-project
    cd automation-project
    ```

2. **Install the required packages:**
    Install Selenium via pip:
    ```bash
    pip install selenium
    ```

3. **Download ChromeDriver:**
    - If you're using Google Chrome, download the corresponding version of **ChromeDriver** from [https://sites.google.com/a/chromium.org/chromedriver/](https://sites.google.com/a/chromium.org/chromedriver/).
    - Ensure the ChromeDriver is in your system's PATH or specify the path in your script.

## Usage

1. **Run the script:**
    - Open your terminal and run the Python script.
    ```bash
    python automation_script.py
    ```

2. **Interacting with the browser:**
    - The script will open the browser and start performing tasks such as form filling, button clicks, or scraping data from the specified website.

3. **Modify the script:**
    - Customize the automation script by changing the URLs, form fields, or web elements in the `automation_script.py` file to suit your needs.

## Script Breakdown

### 1. **Launching the Browser:**
    The script launches the browser using Selenium WebDriver, maximizes the window, and navigates to the desired website.

    ```python
    from selenium import webdriver
    driver = webdriver.Chrome()
    driver.maximize_window()
    driver.get("https://example.com")
    ```

### 2. **Filling Out Forms:**
    Automates filling out a form by locating input fields using **ID**, **XPATH**, or **CSS selectors**.

    ```python
    name_input = driver.find_element_by_id("name")
    name_input.send_keys("John Doe")
    ```

### 3. **Selecting Checkboxes or Radio Buttons:**
    Automates selecting checkboxes or radio buttons by finding elements using attributes like **name** or **value**.

    ```python
    checkbox = driver.find_element_by_name("subscribe")
    checkbox.click()
    ```

### 4. **Selecting from Dropdowns:**
    The script interacts with dropdown menus using the **Select** class.

    ```python
    from selenium.webdriver.support.ui import Select
    dropdown = Select(driver.find_element_by_id("dropdown"))
    dropdown.select_by_value("option1")
    ```

### 5. **Submitting Forms:**
    Automates form submission by clicking the submit button.

    ```python
    submit_button = driver.find_element_by_id("submit")
    submit_button.click()
    ```

### 6. **Closing the Browser:**
    Once the tasks are completed, the browser is closed.

    ```python
    driver.quit()
    ```

## Project File Structure

- **automation_script.py:** The main Python script that contains the automation logic.
- **requirements.txt:** A list of the required packages (e.g., `selenium`) for easy installation using pip.
- **chromedriver.exe:** (Optional) ChromeDriver binary, if it's not set up globally in your system's PATH.

## Functions Overview

- **find_element_by_id:** Locates an element on the webpage using its HTML ID.
- **find_element_by_name:** Locates an element using the name attribute.
- **find_elements:** Finds multiple elements, useful for handling checkboxes, lists, etc.
- **send_keys:** Simulates typing into an input field.
- **click:** Simulates a click event on buttons or checkboxes.
- **get_attribute:** Extracts attribute values like href, class, etc., from web elements.
- **Select:** A class to interact with dropdown menus.

## Example Scenario

The script automates the following scenario on a demo website:

1. Opens the browser and navigates to the website.
2. Fills in the "Name" and "Email" fields.
3. Selects the "Subscribe" checkbox.
4. Chooses an option from a dropdown menu.
5. Submits the form.
6. Closes the browser.

## Customization

- You can modify the **XPATH**, **CSS Selectors**, and URLs within the script to target different websites or web elements based on your use case.
- Change the input data to test different scenarios.

## Troubleshooting

1. **ChromeDriver Version Mismatch:**
   Ensure your Chrome browser version matches the ChromeDriver version. You can check the version of ChromeDriver you need [here](https://sites.google.com/a/chromium.org/chromedriver/).

2. **ElementNotInteractableException:**
   This can occur if the element is not visible or interactable. Make sure to use waits like **WebDriverWait** for handling dynamically loaded elements:
   ```python
   from selenium.webdriver.common.by import By
   from selenium.webdriver.support.ui import WebDriverWait
   from selenium.webdriver.support import expected_conditions as EC

   WebDriverWait(driver, 10).until(EC.element_to_be_clickable((By.ID, "submit")))

## Acknowledgements

- **[Selenium Documentation](https://www.selenium.dev/documentation/):** For reference and learning about Selenium WebDriver.
- **[ChromeDriver Downloads](https://sites.google.com/a/chromium.org/chromedriver/):** Download the ChromeDriver matching your Chrome browser version.


