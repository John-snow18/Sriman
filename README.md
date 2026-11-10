11th exp:-
const { Builder, By } = require("selenium-webdriver");
const chrome = require("selenium-webdriver/chrome");

async function testWebsite() {

    let options = new chrome.Options();
    options.setChromeBinaryPath("/usr/bin/chromium");

    let driver = await new Builder()
        .forBrowser("chrome")
        .setChromeOptions(options)
        .build();

    try {
        await driver.get("https://www.example.com");

        let title = await driver.getTitle();
        console.log("Page Title:", title);

        let heading = await driver.findElement(By.tagName("h1"));
        console.log("Heading:", await heading.getText());

        if (title === "Example Domain") {
            console.log("Test Passed!");
        } else {
            console.log("Test Failed!");
        }

    } finally {
        await driver.quit();
    }
}

testWebsite().catch(console.error);


12th:-
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

try:
    driver.get("http://localhost:8082")

    print("Page Title:", driver.title)

    heading = driver.find_element(By.TAG_NAME, "h1")

    print("Heading:", heading.text)

    print("Experiment 12 Successful!")

finally:
    driver.quit()



    10th:-

    
from selenium import webdriver
from selenium.webdriver.common.by import By

# Open Chromium browser
driver = webdriver.Chrome()

# Open a webpage
driver.get("https://www.example.com")

# Display the page title
print("Page title:", driver.title)

# Find and display the heading
heading = driver.find_element(By.TAG_NAME, "h1")
print("Heading:", heading.text)

# Close the browser
driver.quit()
