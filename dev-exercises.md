## Salesforce Exercises

Repetition is a key learning aid because it helps transition a skill from the conscious to the subconscious. Through repetition, a skill is practiced and rehearsed over time and gradually becomes easier. Below are exercises to help make coding a habit. All the exercises are to be done via Apex.

### Day 1 (Apex: Collections & Inserting Records)
1. Create a free dev org
1. *Insert:
   1. Account record
   1. Contact record
   1. Case record
   1. Opportunity record
1. Create a list that can hold Account records
1. Create a list of 3 Account records
1. Insert the list of Account records
1. *Create a map of:
   1. Account records
   1. 3 Opportunity records
   1. 5 countries and their capitals (i.e. USA => DC). Name the Map **capitals**. Print out the map in Debug Log.
1. From the **capitals** map print out the capitals
1. From the **capitals** map print out the countries
1. Explain to someone everything we did above.

[[↑] Back to top](#salesforce-exercises)

### Day 2 (SOQL intro)
1. *Query Editor:
   1. Query for 10 Account records. Change the name field on 2 of the records and save the records.
   1. Query for 10 Account records & display them in ascending order of name
   1. Query for 3 Account records and their child Contact records
   1. Sum the amount of opportunity records where the amount size is less then $10,000
   1. What is the average of all Opportunity records in your org?
   1. How many account records do you have in your org?
   1. How many contact records do you have in your org?
1. *Execute Anonymous:
   1. Query for 10 Account records and print out the record's in the debug log
   1. Print out the sum of all your Opportunity records in system.debug
   1. Query all Opportunity records and print out their Close Date, Stage and Name in the debug log.
   1. Query for 5 contact records and print out the record's IDs in system.debug
   1. Create a list of 3 Opportunity records, store results in a Map and print the map in the debug log. What do you see?
1. Explain to someone everything we did above.

### Day 3 (For Floops)
1. Pull 3 Contact records and change first name on all to: One, Two, Three
1. Delete the 3 Contact records whose first names are One, Two, Three
1. Pull 10 Account records from Salesforce. Print out their Stage in system.debug. Update their stage to Closed Won. Print out their Stage in system.debug.
1. Do the same as above but in a SOQL for loop
1. Insert 100 Account records
1. Delete 100 Account records that you just inserted
1. Insert 150 Account records whose names are "Account i", where I is an integer
1. Explain to someone everything we did above.

### Day 3 (Error Handling)
1. _Try Catch
   1. Insert an Account without defining its name. What do you get?
   1. Do the same as above but with a try/catch
   1. What should we do in the catch? Populate the name field to be "Seyit" in the catch.
1. List Methods
   1. Create a list that holds all your Contacts records in the org. How do you know how many records are in that list?
   1. Create a list with 10 Contact records. Create a list with 5 Contacts records. How do you add the 2 lists to a 3rd List?    1. How many records does your new list have?
   1. SOQL and SOSL statements in Apex can reference Apex code variables and expressions if they’re preceded by a colon (:). Can you demonstrate a simple example of this?

### Day 4 (Governor Limits)
1. Insert 200 Account records. Insert the Account record one by one. What governor limit did we hit? How do we overcome this error?
1. How can you generate the error "System.LimitException: Too many SOQL queries"?
1. What are the top 3 governor limits? Why are they important?
1. Explain to someone what governor limits are.

[[↑] Back to top](#salesforce-exercises)

### Triggers
1. Create a trigger that:
* populates Description of new Account record to be "Yes I can"
* runs only on Contact updates >>> creates a task for Contact owner with subject "call the contact asap"
1. 

[[↑] Back to top](#salesforce-exercises)

### Class
1. Write a class that accepts a string, creates an Account, returns nothing
2. Write a class that accepts a string, creates an Account, returns ID of the account
3. Write a class that does not accept a string, creates an Account, returns nothing
4. Write a class that does not accept a string, creates an Account in a try catch, returns nothing
5. Write a static method. How do you call it?

[[↑] Back to top](#salesforce-exercises)

### Test Class (unit test)
1. Create a test class for each of the above classes
2. Create a test class for the trigger

[[↑] Back to top](#salesforce-exercises)

### Debug Log
1. Insert 1 account record & analyze the debug log. What do you see?
2. Create a validation rule on account object
   1. Insert 1 account & analyze the debug log

[[↑] Back to top](#salesforce-exercises)

### Governor Limits
1. Write a class that breaks a governor limit
2. Write a class that breaks another governor limit
3. Rewrite #1 so that it does not break gov limit
4. Rewrite #2 so that it does not break gov limit

[[↑] Back to top](#salesforce-exercises)

### Github
1. Push all your classes & triggers into your github repository
2. Create a new branch called “Branch2”
3. Checkout your master

[[↑] Back to top](#salesforce-exercises)

### IDE (IntelliJ or VS Code)
1. Run 3 DML operations 
2. Run 3 Anonymous Apex operations
3. Look at Debug Log
4. Push changes to a class to github

[[↑] Back to top](#salesforce-exercises)

### Googling (critical skill of a developer)
1. What is this error? "Unable to lock row"
2. Can you delete a user?
3. What is the average salary of a salesforce developer in Austin?
4. What is the most popular Salesforce blog?
5. Where can you find the abridged version of Winter 2020 release notes?


