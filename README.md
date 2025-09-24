# 🚀 AutomationSample

## 📖 Project Description
**AutomationSample** is a **test automation framework** built using **Java, Selenium WebDriver, and TestNG**.  
It follows the **Page Object Model (POM)** design pattern for maintainability and scalability.  
The project uses **Maven** for dependency management and integrates seamlessly with **Jenkins** for CI/CD pipelines.  

This framework is ideal for:  
- Automating regression and smoke tests  
- Practicing TestNG annotations, assertions, and data providers  
- Learning Maven + Selenium + TestNG integration  
- Generating detailed reports after execution  

---

## 🏗 Project Structure

AutomationSample/
├── pom.xml # Maven configuration (dependencies, plugins)
├── src
│ ├── main
│ │ └── java
│ │ └── pageObjects # Page classes for UI elements (POM)
│ └── test
│ └── java
│ └── testCase # TestNG test classes
├── resources
│ └── testng.xml # TestNG suite configuration
└── test-output # Auto-generated reports (after execution)

| Package / File | Purpose |
|----------------|---------|
| `pageObjects`  | Contains classes with locators and methods to interact with web pages. |
| `testCase`     | Contains TestNG test scripts that use page objects. |
| `testng.xml`   | Controls execution flow (suite level, groups, parallelism, etc.). |
| `pom.xml`      | Defines dependencies (Selenium, TestNG, etc.). |
| `test-output`  | Stores execution reports (`emailable-report.html`, `index.html`, etc.). |

---

## 🚀 How to Run the Tests

### 🔹 Method 1: Run Locally with Maven
```bash
git clone https://github.com/Arbind1234321/AutomationSample.git
cd AutomationSample
mvn clean test

Method 2: Run via Jenkins
Create a Maven job in Jenkins.
Point it to the repo or local project.
Add build step:
mvn clean test
Jenkins will execute the tests and generate reports.
3: Run in IDE
Import the project into Eclipse or IntelliJ IDEA.
Right-click on testng.xml → Run As → TestNG Suite.

🧪 Features

✅ Java + Selenium WebDriver + TestNG

✅ Page Object Model (POM)

✅ Data-driven testing with @DataProvider

✅ HTML & XML TestNG reports

✅ Jenkins CI/CD ready

✅ Extensible design for utility classes, listeners, and retry logic

🛠 Requirements

Java JDK (17 or later)

Maven 3.x

Selenium & TestNG (managed via pom.xml)

ChromeDriver / GeckoDriver installed or set in PATH

📊 Reports

After test execution, reports are available in test-output/:

emailable-report.html

index.html

testng-results.xml

 Test Code
Example LoginPage (Page Object)
public class LoginPage {
    WebDriver driver;

    @FindBy(id="username")
    WebElement usernameInput;

    @FindBy(id="password")
    WebElement passwordInput;

    @FindBy(id="loginBtn")
    WebElement loginButton;

    public LoginPage(WebDriver driver) {
        this.driver = driver;
        PageFactory.initElements(driver, this);
    }

    public void enterUsername(String username) {
        usernameInput.sendKeys(username);
    }

    public void enterPassword(String password) {
        passwordInput.sendKeys(password);
    }

    public void clickLogin() {
        loginButton.click();
    }
}
