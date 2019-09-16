## Title

Phili, the chatbot. Phili helps in selecting Philips patient monitors for purchase.


## Acceptance criteria

-   The web-based chatbot should accept input and give its response on the browser
    
-   The conversation (sequence of messages) should lead the customer to a purchase-suggestion
    
-   It must be easy to re-use this chatbot for another domain (such as without having to re-compile it)

## Brief Description of the API

The project is not complete. We developed a RESTful service for the chatbot which suggests one or more patient monitors to users from the list of available patient monitors in Philips ([List of patient monitors](https://www.philips.co.in/healthcare/solutions/patient-monitoring/patient-monitoring)) depending upon their requirements. The service vice was developed as a springboot application. The user interface is not developed for this project.

## Algorithm design

-   The chatbot will **display MCQ questions** one by one with options for the user to select. The user should select an option for each question only from the given options
    
-   **The first question is default**. The subsequent question is selected depending on the user’s selected input for the first question and the other questions are selected the same way
    
-   When there are no more questions to ask for finalizing a product, the chatbot will display the name(s) of the relevant patient monitor(s) to the user

## Built With

-   Spring boot
    
-   Maven
    
-   RESTful service
- H2 database

## Getting started

We used h2 database to store the list of questions and options. This database is embedded within the java application, so there is no need to install any software separately to run the application. There is no software needed to run the application other than java.

The database dependency is already included in the pom (project object model) file of the project so when the project is executed, the application will create the database itself. When the project is running, the database console could be seen using the url, `http://localhost: [the server port number on which the application is running]/h2-console`.

>**We created two tables**
>
>-   List of questions with question IDs
>
>-   List of options with option IDs for all the question IDs along with the next question ID or the list of patient monitors

The tables are automatically created by the embedded h2 database application when the entity classes are present. The tables could be edited either in the h2-console or in the data.sql file which could be found in the ‘resources’ folder. The SQL commands are used in data.sql file to edit the database tables. `application.properties` file under the same `resources` folder could be used to edit the port number of the server on which the application should run.

## Deployment

Clone the project onto your system and run the `ChatbotApplication.java` class. The springboot application will run as a java application and the service could be tested on any browser or postman software using the urls.

## Standard
The test coverage that we achieved was 70%.

## Support

Contact authors

-   [vaishali.shrivastava@philips.com](mailto:Vaishali.shrivastava@philips.com)
    
-   [harshit.mangwani@philips.com](mailto:Harshit.mangwani@philips.com)
    
-   [gopinath.shanmugam@philips.com](mailto:Gopinath.shanmugam@philips.com)

## Request for contributors

Develop an attractive user interface for the chatbot RESTful service we developed

## Authors and acknowledgement

Vaishali Shrivastava, Harshit Mangwani, and Gopinath Shanmugam are the developers of this project. We sincerely thank Bnil Nath, Sudeep Prasad, and Sunil Jacob for their immense support.

