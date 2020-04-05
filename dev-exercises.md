## 10 Day Dev Challenge

Repetition is a key learning aid because it helps transition a skill from the conscious to the subconscious. Through repetition, a skill is practiced and rehearsed over time and gradually becomes easier. Below are exercises to help make coding a habit. All the exercises are to be done via code, not clicks. 

### Day 1 (Apex: Collections & Inserting Records)
1. Create a free dev org (if don't have one)
1. *Insert*:
   1. 1 Account record
   1. 1 Contact record
   1. 1 Case record
   1. 1 Opportunity record
1. Create a set that can hold Strings
1. Add these strings (One, Two, Three) to the Set
1. Create a list that can hold Account records
1. Create a list with 3 new Account records
1. Insert the list of Account records
1. *Create a map of*:
   1. Account records
   1. 3 Opportunity records
   1. 5 countries and their capitals (i.e. USA => DC). Name the Map **capitals**. Print out the map in Debug Log.
1. From the **capitals** map print out the capitals
1. From the **capitals** map print out the countries
1. From the **capitals** map print out 1 capital
1. Create **capitals2** map, which is a copy of **capitals** map
1. Explain to someone everything we did above.
1. Watch videos by Deepeka Khana

[[↑] Back to top](#salesforce-exercises)

### Day 2 (SOQL intro)
1. *Query Editor*:
   1. Query for 10 Account records. Change the name field on 2 of the records and save the records.
   1. Query for 10 Account records & display them in ascending order of name
   1. Query for 3 Account records and their child Contact records
   1. Sum the amount of opportunity records where the amount size is less then $10,000
   1. What is the average of all Opportunity records in your org?
   1. How many account records do you have in your org?
   1. How many contact records do you have in your org?
1. *Execute Anonymous*:
   1. Query for 10 Account records and print out the record's in the debug log
   1. Print out the sum of all your Opportunity records in system.debug
   1. Query all Opportunity records and print out their Close Date, Stage and Name in the debug log.
   1. Query for 5 contact records and print out the record's IDs in system.debug
   1. Create a list of 3 Opportunity records, store results in a Map and print the map in the debug log. What do you see?
1. Explain to someone everything we did above.

### Day 3 (For Loops)
1. Pull 3 Contact records and change first name on all to: One, Two, Three. Check in Salesforce that these Contacts exist.
1. Delete the 3 Contact records whose first names are One, Two, Three
1. Query 100 Account records and change their description to be "I will become a Salesforce developer"
1. Query 10 Opportunity records from Salesforce. Print out their Stage in system.debug. Update their stage to Closed Won. Print out their Stage in system.debug.
1. Do the above in a SOQL for loop
1. Insert 100 Account records
1. Delete 100 Account records that you just inserted
1. Insert 150 Account records whose names are "Account i", where I is an integer
1. Explain to someone everything we did above.

### Day 4 (Error Handling)
1. _Try Catch_
   1. Insert an Account without defining its name. What do you get?
   1. Do the same as above but with a try/catch
   1. What should we do in the catch? Populate the name of the Account to be "Seyit" in the catch.
1. _List Methods_
   1. Create a list that holds all your Contacts records in the org. How do you know how many records are in that list?
   1. Create a list with 10 Contact records. Create a list with 5 Contacts records. How do you add the 2 lists to a 3rd List?    1. How many records does your new list have?
   1. SOQL and SOSL statements in Apex can reference Apex code variables and expressions if they’re preceded by a colon (:). Can you demonstrate a simple example of this?
1. Explain to someone everything we did above.

### Day 5 (Governor Limits)
1. Insert 200 Account records. Insert the Account record one by one. What governor limit did we hit? How do we overcome this error?
1. Write code such that you generate the error "System.LimitException: Too many SOQL queries"?
1. What are the top 3 governor limits? Why are they important?
1. Explain to someone what governor limits are.
1. Create triggers that:
   1. populates Description of new Account record to be "Yes I can"
   1. runs only on Contact updates >>> creates a task for Contact owner with subject "call the contact asap"
1. Create a test class for the trigger

### Day 6 (Apex Class)
1. Write a class that accepts a string, creates an Account, returns nothing
1. Write a class that accepts a string, creates an Account, returns ID of the account
1. Write a class that does not accept a string, creates an Account, returns nothing
1. Write a class that does not accept a string, creates an Account in a try catch, returns nothing
1. Write a static method. How do you call it?
1. Create a test class for each of the above classes. Achieve 100% code coverage.
1. Explain to someone 3 things that you learned today.
1. Insert 1 account record & analyze the debug log. What do you see?
1. Create a validation rule, workflow & process biulder on account object. 
   1. In Debug Levels, set Apex to Info & Workflow to Info. Insert 1 account & analyze the debug log. What do you notice?
   1. In Debug Levels, set Apex to Finest & Workflow to Finer. Insert 1 account & analyze the debug log. What do you notice?
   1. In Debug Levels, set Apex Profiling to Finest. What do you see? What is Apex Profiling used for?
1. What do you use Debug Logs for?
1. Open a Debug Log in Developer Console. Go to Debug > Switch Perspective > Analysis. What do you see?
   1. What is the Execution Tree?
   1. In "Execution Overview" panel what is the use of "Save Order" window?
   1. In "Execution Overview" panel what is the use of "Limits" window?
   1. In "Execution Overview" panel what is the use of "Timeline" window?
1. Explain to someone 3 things you learned today.   

### Day 7 (GitHub)
1. Create a github account (if you don't have one)
1. Install Github for Desktop
1. Star this repository: https://github.com/usmanovs/Salesforce-Interview-Handbook
1. Fork this repository: https://github.com/usmanovs/Salesforce-Interview-Handbook
1. Make 3 improvements to this file: https://github.com/usmanovs/Salesforce-Interview-Handbook/blob/master/dev-exercises.md
1. Push your changes to your fork
1. Make a pull request with your changes and a small summary of what changes you suggest.
1. Create your own repository (i.e. Seyit 10 Day Dev Challenge)
1. Push all your classes & triggers to your repository
1. Create a new branch called “Branch2”
1. Checkout your master
1. Explain to someone what you just did today

### Day 8 (IntelliJ or VS Code)
1. Install IntelliJ. Install Illuminated Cloud extension. Do the rest of the tasks in IntelliJ.
1. Create a Project called "10 Day Dev Challenge".
1. Run 3 DML operations 
1. Run 3 Anonymous Apex operations
1. Look at the Debug Log
1. Write a class that accepts a string, creates an Account, returns nothing. Commit that class & push it to Github
1. Change your branch using the Terminal
1. In the Query Editor query for 5 Account records

### Day 9 (Googling- the quintessential skill of a developer)
1. What is this error? "Unable to lock row"
1. Can you delete a user?
1. What is the average salary of a salesforce developer in Austin?
1. What is the most popular Salesforce blog?
1. Where can you find the abridged version of Winter 2020 release notes?
1. Can you find the latest release notes for Illuminated Cloud?

### Day 10 (Engaging the Community)
1. Register an account at https://success.salesforce.com/
1. Register at an upcoming Salesforce Admin Group meeting and make a goal to meet 3 interesting people.
1. Register at an upcoming Salesforce Developer Group meeting and make a goal to meet 3 interesting people.
1. Register a Reddit account. Review the last 10 posts in  https://www.reddit.com/r/salesforce/. Search for "Salesforce Developer Interview" posts
1. Register with https://salesforce.stackexchange.com/. Read the last 5 posts. Upvote those that you find interesting.
1. Explain to someone the importance of each of the above tasks
1. Pat yourself on the back for completing the last day of the 10 Day Challenge! Now let's start over so that coding tasks are easier next time round.

[[↑] Back to top](#salesforce-exercises)

