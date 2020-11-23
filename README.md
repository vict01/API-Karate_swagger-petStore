# Karate Automation Testing For PetStore API based On Swagger Repository

## Overview
This is the test automation for swagger-based PetStore API, which contains a set of automated scenarios based on Karate API Framework. 
The test scope encompasses testing each type of methods for Pet information. 

## Framework structure
* src/test/java:
  
  - feature folder:
    Contain the features files with the scenarios and its corresponding steps.

  - helper folder:
    Contains the data and methods used in testing, as well a JSON file as external file against which is validated some outcomes or used as input data as appropriate. 

  - TestRunner class:
    Contains the runner class through which we can generate a cucumber report (overview-features.html) after running it.
    Also, it enables to run all features simultaneously and skip some scenario as appropriate. 

* In the root path of the project:
  
  In general there are the configuration files within which the most important are:

  - pom.xml File: Contains the dependencies and plugins required for the operation of the framework and testing.
  - karate-config.js: Contains global variables used for general purposes like environments handling, etc.
  - log4j2.properties and logback-test.xml: Complements to make more readable and graceful the console log output. 


## Technologies and tools used:
In this framework we used different components, which we break them down below with its respective descriptions:
```
1. Karate: Framework that allows the API test-automation.
2. Cucumber: BBD tool which provides a logical language that customers can understand.
3. Java: Programing language to coding and build the test logic.
4. JavaScript: Scripting language to handle js and json files, as well to build functions within features files.
5. JUnit: The framework to create, organize and execute tests.
6. Maven: The software application that allows packaging and manage dependencies.
7. jetty server: Web server and javax.servlet container (only if you decide to use http://localhost:8080/api/v3/openapi.json 
                 instead of https://petstore3.swagger.io/api/v3/openapi.json)
```

## Instructions to run the tests and review test results:

### To run all tests together at once:
1. In the project panel, right click on TestRunner class, pick up "Run TestRunner".
   Besides, in some IDE within the Java class you can see a run symbol (button) next to the statements "public class <className>" through which you can execute the class.

2. Once test finish running, you'll be able to see the symbols/mark corresponding to failed / successful / warning
   in the left Junit panel, according to the results obtained in general. 
   As well within the console log output, at the end of each feature run you can see a section with a summary result for such a feature.

3. To see a readable and graphical report in HTML about testing result, just go to the "target/surefire-reports" folder in the project root path and open the  karate-summary.html file with any web browser, through this we can see a report for 3 views: summary, by features and by tags, just click on each option as appropriate. 

4. In addition, there is much better and complete report located in: "target/cucumber-html-reports/js/overview-features.html", just open it with any web browser and navigate through links accordingly. 

### To run a specific feature file entirely (with all its scenarios):
1. In the project panel, right click on any feature files > and pick up "Run Feature: <file name>". 
   Besides, in some IDE within the features files you can see a run symbol next to the statements "Feature" through which you can execute the tests.
2. From now on, take into account the points 2 and 3 in the previous section likewise. 
    
    Note: The karate-summary.html is replaced every time you run a feature, however also is generated an individual html report for each feature with the same name as the file. Not so for report mentioned in point 4 in the previous section.  

### To run a specific scenario within any feature file:
1. Go to any feature file
2. Within the features files you can see a run symbol (button) next to the statements "Scenario" through which you can execute it.
3. Now take into account the same consideration mentioned in the point 2 of the previous section. 

### To omit a specific feature while running the runner class:
1. Go to the feature which you want to skip/omit and on top of the statement "Feature" place the tag "@ignore".
3. Run you feature as appropriate.

### To omit a specific scenario while running the runner class:
1. Do the same as the previous point but for Scenario statement instead of feature.

### To prevent any scenario  from running in parallel when runner class is executed:
1. Go to the scenario which you want to prevent from running in parallel and place on the top of it the tag "@parallel=false".
