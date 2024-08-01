# JWA Foundation Project
The Planetarium is a web application designed by Revature Space Initiative for astronomers to track celestial bodies they discover in the night sky. Development work on the application is progressing, and the company wants to bring in testers to improve Quality Control to further improve product quality. Your job this Sprint is to perform manual testing on the application  with two main goals: to look for defects in the product, and to give feedback on the user experience working with the app. 

## Project Focus
- Jira
- Manual Testing
- Test Case Creation
- Test Reporting
- System Testing
- Acceptance Testing

## Software Requirements  
- Users should have unique usernames
- Usernames and passwords should not be longer than 30 characters
- Planet and Moon names should not have more than 30 characters
- Planets and moons should have unique names
- Planets should be “owned” by the user that added it to the Planetarium
- Moons should be “owned” by the Planet the User adding the moon associated it with
- Planets and Moons should allow adding an associated image, but an image should not be required for the data to be added to the database

## Use Cases
- Users should be able to open a new User account with the Planetarium
- Users should be able to securely access their account
- Users should be able to see planets and moons added to the Planetarium
- Users should be able to add new Planets to the Planetarium
- Users should be able to remove Planets from the Planetarium
- Users should be able to add Moons to the Planetarium associated with a Planet
- Users should be able to remove Moons from the Planetarium

## Testing Requirements
- All Test Reporting should be done in Jira
- All Use Cases require a minimum of one positive test
- All Use Cases with associated software requirements require negative testing to verify requirements are met
- All Use Cases with Software Requirements that limit data **input** require Boundary Analysis Testing
- All Use Cases with Software Requirements that limit data **visibility** require Error Guess Testing
- All Use Cases with Software Requirements that limit data **interaction** require Error Guess Testing
- All tests that fail should be logged in a Defect Report inside of Jira
- Acceptance testing for the user experience should answer the following questions in detail:
    - Is the intended use of the service intuitive?
    - Is the service easy to use?
    - Does the service inspire confidence?
    - Is the service pleasing to look at?

## MVP Requirements
- Test Cases are created for Use Cases
- Test Cases are saved in Jira
- Manual Tests are complete
- Test Results are saved in Jira
- Defect Reports are created for each failed test
- Defect Reports are saved in Jira

## Suggested Stretch Goals
- perform extra Error Guess Testing
- perform Non-Functional System testing

## Setup Requirements
- an environment variable called "PLANETARIUM" needs to be set with the JDBC url for the planetarium database
    - SQLite3 is used by the application
- a database needs to be created and set up for the planetarium to work properly. Use the ```setup-reset.sql``` file to create the database at the same location as your "PLANETARIUM" environment variable
-  start the application with the command ```java -jar path/to/Planetarium-1.0-shaded.jar```

# Use Case
- Id: 1
- Name: user registration
- Description: Users Should be able to register with the Bank
- System: Planetarium application
- Preconditions:
    - No registered user with username "Robin"
    - registered user with username "Batman"
- Actors:
    - User (creating a new account)
    - Planetarium application (handles the creation of the new account)

# Scenarios
**Positive Scenario**:
1. get to landing page
2. pick option to register
3. provide valid username
4. provide valid password
5. user should be registered with the bank

**Negative Scenario Username not unique**:
1. get to landing page
2. pick option to register
3. provide non-unique username
4. provide valid password
5. user should be informed registration failed

**Negative Scenario Username too long**:
1. get to landing page
2. pick option to register
3. provide too long username
4. provide valid password
5. user should be informed registration failed

**Negative Scenario Password too long**:
1. get to landing page
2. pick option to register
3. provide valid username
4. provide too long password
5. user should be informed registration failed

**Negative Scenario credentials too long**:
1. get to landing page
2. pick option to register
3. provide too long username
4. provide too long password
5. user should be informed registration failed

**Negative Scenario username taken and password too long**:
1. get to landing page
2. pick option to register
3. provide non-unique username
4. provide too long password
5. user should be informed registration failed

# Test Data
Positive:
- valid username = "Batman and Robin unite now!!!!"
- valid password = "Riddler and Joker disagree!!!!"

Negative:
- non-unique username = "Batman"
- too long username = "Gordon and Clark are friends!!!"
- too long password = "Reverse Flash strikes again!!!!"

## Decision Table
<table>
    <tr>
        <th>Scenario</th><th>Username</th><th>Password</th><th>result</th>
    </tr>
    <tr>
        <td>Positive Scenario</td><td>valid username</td><td>valid password</td><td>user registered</td>
    </tr>
    <tr>
        <td>Negative Scenario Username not unique</td><td>non-unique username</td><td>valid password</td><td>user not registered</td>
    </tr>
    <tr>
        <td>Negative Scenario Username too long</td><td>too long username</td><td>valid password</td><td>user not registered</td>
    </tr>
    <tr>
        <td>Negative Scenario Password too long</td><td>valid username</td><td>too long password</td><td>user not registered</td>
    </tr>
    <tr>
        <td>Negative Scenario credentials too long</td><td>too long username</td><td>too long password</td><td>user not registered</td>
    </tr>
    <tr>
        <td>Negative Scenario username taken and password too long</td><td>non-unique username</td><td>too long password</td><td>user not registered</td>
    </tr>
</table>

# Test Cases
|Test Case Id|Description|Preconditions|Test Data|Steps|Expected Outcome|Actual Outcome|Tester|Status|
|------------|-----------|-------------|---------|-----|----------------|--------------|------|------|
|1|given a valid username and password a user should be able to register with the bank|No registered user with username "Robin"|valid username, valid password|<ol><li>get to landing page </li><li>pick option to register </li><li>provide valid username</li><li>provide valid password</li><li>user should be registered with the bank</li></ol>|user should be registered with the bank|TBD|Mark|TBD|
|2|given a non unique username and valid password a user should not be able to register an account|registered user with username "Batman"|non-unique username, valid password|<ol><li>get to landing page </li><li>pick option to register </li><li>provide non-unique username</li><li>provide valid password</li><li>user should be informed the username is already taken</li></ol>|user not registered|TBD|Mark|TBD|
|3|given a too long username and valid password a user should not be able to register an account|N/A|too long username, valid password|<ol><li>get to landing page </li><li>pick option to register </li><li>provide too long username</li><li>provide valid password</li><li>user should be informed the username is too long</li></ol>|user not registered|TBD|Mark|TBD|
|4|given a valid username and too long password a user should not be able to register an account|N/A|valid username, too long password|<ol><li>get to landing page </li><li>pick option to register </li><li>provide valid username</li><li>provide too long password</li><li>user should be informed the password is too long</li></ol>|user not registered|TBD|Mark|TBD|
|5|given a too long username and too long password a user should not be able to register an account|N/A|too long username, too long password|<ol><li>get to landing page </li><li>pick option to register </li><li>provide too long username</li><li>provide too long password</li><li>user should be informed the password is too long</li></ol>|user not registered|TBD|Mark|TBD|
|6|given a non unique username and too long password a user should not be able to register an account|N/A|non-unique username, too long password|<ol><li>get to landing page </li><li>pick option to register </li><li>non unique valid username</li><li>provide too long password</li><li>user should be informed registration failed</li></ol>|user not registered|TBD|Mark|TBD|