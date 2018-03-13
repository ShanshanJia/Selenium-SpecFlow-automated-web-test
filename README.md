# Selenium-SpecFlow-automated-web-test
Automated Web tests on a sample loan application site using Page Object Model with Selenium and SpecFlow.

## Description
Automated browser UI tests written(designed) for manipulating a simple loan application web app. To make the automated tests more efficient, bussiness readable and maintainable, the major techniques stack covered in the test implementation include:
* Web UI automation, BDD
* Selenium WebDriver, Selenium Page Object Models
* SpecFlow, Gherkin
* xUnit.net
* Microsoft Visual Studio
* C#, .Net

## App-under-test
A sample ASP.NET MVC web application called LoanApplicationSite, as shown in the views below.
![StartLoanApplication view](https://github.com/ShanshanJia/Selenium-SpecFlow-automated-web-test/raw/master/StartLoanApplicationView.png)

![ApplicationComplete view](https://github.com/ShanshanJia/Selenium-SpecFlow-automated-web-test/raw/master/ApplicationCompleteView.png)

## Prerequisites
* Microsoft Visual Studio
* Unit testing framework (xUnit.net)
* xunit.runner.visualstudio NuGet package
* SpecFlow Visual Studio Extension
* Specflow.xUnit NuGet package
* Selenium.WebDriver NuGet package
* Selenium.Support NuGet package

## Feature
Loan application

### Test Scenario 1 - Application completed successfully.
On StartLoanApplication page, if we enter a first name and a second name, select the option that we've got an existing loan account, accept the terms and conditions and submit our application, then we should be taken to the correct ApplicationComplete page and we get the correct first name output.

### Test Scenario 2 - Cannot submit application unless terms and conditions accepted
In Test Scenario 1, if we try to submit the application without accepting the terms and conditions, we should get the validation error message.

## Test design details
1. Creating business readable SpecFlow scenarios
	* Add SpecFlow feature file
	* Add Feature description
	* Write Given, When, and Then steps
2. Generate step definitions file containing C# methods
3. Adding Selenium automation code into step definitions
	* Create FirefoxDriver in Given step
	* IWebDriver interface and inheritance hierarchy
	* HTML element selection with Selenium WebDriver
	* Dispose in \[AfterScenario] SpecFlow hook method
4 Insulate test code from UI changes using page object models
	* Create LoanApplicationPage and ApplicationConfirmationPage classes
	* Ctor with IWebDriver parameter
	* Refactor steps code with added properties and methods 
5 Selenium page object model support
	* Add private fields decorated with \[FindsBy(...)]
	* PageFactory.InitElements(\_driver, this)
  * Reference fields from methods and properties
