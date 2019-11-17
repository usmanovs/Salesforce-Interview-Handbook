# Salesforce Develop Questions

Pull requests for suggestions and corrections are welcome!

## Fundamentals
* [What are governor limits? Why are they important?](#what-are-governor-limits-why-are-they-important)
* [What are the Bulkification best practices?](#what-are-the-bulkification-best-practices)
* [What is the difference between force.com and salesforce.com?](#what-is-the-difference-between-forcecom-and-salesforcecom)

Behavioral
* [What are your 3 favourite Salesforce blogs?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [Do you attend Salesforce developer community meetings?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [What do you do when you are stuck when you code?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [How many reputation points do you have on salesforce StackEchange?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [Would you say you are passionate about Salesforce? If so why?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [Have you ever contributed to Salesforce's Ideas? If you could make any idea come true, what would it be?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [Where do you see yourself in 3 years?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [Do you enjoy being a Salesforce developer? Why?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)

Sharing & Security
* [What is Apex Managed Sharing?](#what-is-apex-managed-sharing)
* [How many ways can we share a record?](#how-many-ways-can-we-share-a-record)
* [What is a use case for sharing rules?](#what-is-a-use-case-for-sharing-rules)

SOQL & DML
* [What are the default indexed fields in Salesforce?](#what-are-the-default-indexed-fields-in-salesforce)
* [What is the difference betweeen insert() and database.insert()?](#what-is-the-difference-betweeen-insert-and-databaseinsert)
* [What is the difference between SOQL and SOSL?](#what-is-the-difference-between-soql-and-sosl)

Data Modelling & Data Management 
* [What Are The Types of SOQL Statements in SalesForce?](#are-you-familiar-with-styling-svg)
* [When one wants to pass the collection to the query instead of passing one value which keyword helps us?](#can-you-give-an-example-of-an-media-property-other-than-screen)
* [What is Future Annotation(@Future)?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is “Data Skew”?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Explain skinny table. What are the considerations for Skinny Table?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Which fields are automatically Indexed in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Which fields are excluded from a custom index?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is Future Annotation(@Future)?](#what-are-some-of-the-gotchas-for-writing-efficient-css)

Logic & Process Automation 
* [What are the types of custom settings in Salesforce? What is the advantage of using custom settings?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are custom labels in Salesforce? What is the character limit of custom label?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are deterministic formula fields in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)

Apex
* [Why do we need to write test classes? How to identify if a class is a test class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Why do we use start test & stop test annotations?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Why do we need to write test classes? How to identify if a class is a test class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the best practices for writing test classes?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Name 3 governor limits you know? Why are they important? How do you resolve when you see such errors?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the different types of collections in Apex? What are maps in Apex?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is the use of “@future” annotation?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the different methods of batch Apex class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is Trigger.new?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is the difference between SOQL and SOSL?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is the difference between public and global class in Apex?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the two options for when Apex Triggers can run?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is a use case for sharing rules?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Explain the use of an Outbound Message?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is Trigger.new?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is the Save Order of Execution? Why is it important?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is a wrapper class? Give one use case where you would use a wrapper class.](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Explain various methods of batch Apex class?](#what-is-css-selector-specificity-and-how-does-it-work)
* [What is Apex Email Service?](#whats-the-difference-between-resetting-and-normalizing-css-which-would-you-choose-and-why)
* [Describe the 3 qualities of Apex that make it powerful?](#describe-floats-and-how-they-work)
* [What is Map Class in Apex Salesforce?](#describe-z-index-and-how-stacking-context-is-formed)
* [What is Batch Apex in Salesforce?](#describe-block-formatting-context-bfc-and-how-it-works)
* [What is Apex Scheduler?](#what-are-the-various-clearing-techniques-and-which-is-appropriate-for-what-context)
* [What is the Apex Trigger in Salesforce?](#explain-css-sprites-and-how-you-would-implement-them-on-a-page-or-site)
* [What is an Apex transactions?](#how-would-you-approach-fixing-browser-specific-styling-issues)
* [What are static resources?](#what-are-the-different-ways-to-visually-hide-content-and-make-it-available-only-for-screen-readers)
* [What is the difference between public and global classes in Apex?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [Why use Batch Apex instead of Normal Apex?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [What the difference between isNull and isBlank?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)

Debug & Deployment Tools
* [What are the different ways of deployment in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Why do we need to write test classes? How to identify if a class is a test class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Why do we need to write test classes? How to identify if a class is a test class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Why do we need to write test classes? How to identify if a class is a test class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Why do we need to write test classes? How to identify if a class is a test class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [Why do we need to write test classes? How to identify if a class is a test class?](#what-are-some-of-the-gotchas-for-writing-efficient-css)

Scenario Based Questions
* [ What does it indicate if an error state this “list has no rows for assignment”?](#what-are-some-of-the-gotchas-for-writing-efficient-css)

### What are governor limits? Why are they important?
The governor limits in salesforce are actually applied from salesforce end, so as to ensure that the orgs do not abuse the use of the platform. With these limits in place, developers are forced to write scalable code, which are efficient and optimized so as to use the provided resources as less as possible. There are few limits which you can directly view under "Company Information" like API requests limit. However, for viewing all the governor limits of your org, you can use the link https://workbench.developerforce.com/login.php. Some of the examples of governor limits are:

<img src="/assets/Governor limits.png">

These governor limits are important so that all the companies and organizations using salesforce can use the provided resources without affecting each other because of the non-availability of the resources like memory, space and any script resulting in infinite loop.

###### References

* https://www.janbasktraining.com/blog/handle-governor-limits-salesforce/
* https://www.salesforcecodecrack.com/2018/09/how-to-check-your-org-governor-limits.html

[[↑] Back to top](#salesforce-develop-questions)

### What are the Bulkification best practices?
Bulkification is actually quite different from what it sounds. It is a process of optimizing the queries so that governor limits are not hit and the org is not locked for that duration. As there is a limit for every transaction in salesforce, it will be better if your code can fetch maximum number of records at a time, which can be done through bulkification.

The best practices of bulkification includes:

- Use collections - You can execute a query to fetch all the data and can store it for you. Later on, this result can be used for further queries and you will not have to make database calls with each query.
- There is a governor limit on SOQL queries and DML statements. Thus, if you will use it within a FOR loop, it will reach the governor limit quickly. Thus, always avoid these queries or statements within FOR loop.
- Also, when you are using DML statements, make sure that it fetches large number of records and should not be used for fetching single record.
- If your SOQL query will be returning more than 50,000 records (which is a governor limit), you should consider executing that query inside a FOR loop using DML statements. However, ensure that you do not exceed the use of DML statements from the specified governor limit.
- Use Limits class to keep a track of your usage and to monitor whether you are about to reach the governor limits or not. You can use System.debug statements for that purpose.

###### References

* https://developer.salesforce.com/page/Apex_Code_Best_Practices
* https://www.forcetalks.com/salesforce-topic/how-to-bulkify-a-code-in-salesforce-apex/

[[↑] Back to top](#salesforce-develop-questions)

### What is the difference between force.com and salesforce.com?
Before understanding the difference between them, you need to know that both of them are cloud based services.

<table cellpadding="3">
<tr>
<td align="center">
<b>Salesforce.com</b>
</td>
<td align="center">
<b>Force.com</b>
</td>
</tr>
<tr><td>This is provided as SaaS product, which means Software as a Service.</td><td>This is provided as PaaS product, which means Platform as a Service.
</td></tr>
<tr><td>
This is a cloud CRM service using which a user can create leads, opportunities and accounts.
</td><td>
This is a platform using which a user can create various apps, objects and other things required to create a platform like salesforce.com.
</td></tr>
<tr><td>
Salesforce.com requires a platform called Force.com in order to work as the most powerful cloud CRM.
</td><td>
Force.com does not require salesforce.com for its existence. It uses HTML, CSS, Javascript and other coding languages for creating required applications.
</td></tr>
</table>

###### References

* https://www.zarantech.com/blog/difference-between-salesforce-com-and-force-com/
* https://medium.com/@webuters/what-is-the-difference-between-salesforce-com-and-force-com-de1866449326

[[↑] Back to top](#salesforce-develop-questions)

### What is Apex Managed Sharing?
Sharing basically refers to give access of any particular object or record to a user or group of users who do not have access to it. There are various ways of sharing the access and one of those methods is Apex Managed Sharing. This is basically writing an apex code to share the access, rather than using the pre-defined sharing rules by salesforce. These pre-defined rules are limited and thus, apex managed sharing gives you the freedom to create complex sharing modules.

For all the standard objects, there exists a corresponding sharing object. For example: For Accounts object exists an AccountShare object for sharing purpose. This is different with custom objects. For custom objects, like "MyCustomObject", its sharing object will be named "MyCustomObject__Share".

In order to create apex managed sharing for a standard object, navigate to "object_name" > Triggers > New and create a trigger for apex based sharing.

<img src="/assets/Standard apex sharing.png">

For creating apex managed sharing for a custom object, first create Apex Sharing Reason and then from Triggers, create the apex code for the sharing.

<img src="/assets/Custom apex sharing.png">

###### References

* https://www.jitendrazaa.com/blog/salesforce/apex-based-sharing-in-salesforce/
* https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_bulk_sharing_creating_with_apex.htm

[[↑] Back to top](#salesforce-develop-questions)

### How many ways can we share a record?
There are 5 ways of sharing a record in the salesforce.

1) Roles - A role of the user determines level of its sharing. If the user is higher in role hierarchy, than the user will have access to records owned by the users lower in the hierarchy. This will never work vice versa by default.

2) Manual Sharing - In order to manually share a record, the user can click on "Sharing" button and add the list of users with whom the sharing needs to be done. Here the user can decide what level of access will be given to the shared users. 

<img src="/assets/Sharing button.png">

<img src="/assets/Manual sharing.png">

3) Organization Wide Defaults (OWD) - As the name suggests, this kind of sharing is common across the org. If a record is marked as public, it will be accessible to every user of the org. Apart from public, other sharing levels are private and public read/write. For accessing these levels of sharing, navigate to Setup > Settings > Security > Sharing Settings

<img src="/assets/View sharing settings.png">

4) Apex Sharing - This has been discussed in detail in the answer for the above question.

5) Sharing Rules - These are pre-defined rules provided by the salesforce, customizing which you can create sharing rules manually. These rules can be dependent on certain criteria or conditions to be executed. This can be created for any object through object's sharing rules section. Navigate to Setup > Settings > Security > Sharing Settings and navigate to desired object's sharing rules section. For example: "Accounts Sharing Rules". Fill in the required fields for creating sharing rules for that record.

<img src="/assets/Sharing rules.png">

###### References

* https://www.forcetalks.com/salesforce-topic/in-how-many-ways-we-can-share-a-record-in-salesforce-explain-briefly/

[[↑] Back to top](#salesforce-develop-questions)

### What is a use case for sharing rules?
There can be various use cases for sharing rules, but lets take an example of Account Sharing Rules. Suppose that an organization has two offices, one in the USA and another one in the Canada. We want the sharing rules to work as such the regional directors of respective regions can access all the accounts created by their respective sales reps.

We can start by creating separate groups for directors and sales reps. Once created, we can create sharing rules such that all the accounts created by sales reps of the USA are acccessible to regional director of the USA and the accounts created by sales rep of Canada are accessible to regional director of Canada.

###### References

* http://salesforcefaq.blogspot.com/2013/04/uses-cases-for-sharing-rules-in.html

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are the default indexed fields in Salesforce?
While fetching a data through a query, it can be time consuming and might even result in an error when output records are huge in numbers. In order to rectify that issue, we can create indexes for the data, so that while searching for a specified data through query or statement, only the related data is looked upon using the indexes. There are various fields indexed by default by the salesforce, however, if you are looking to get a field to be indexed based on the data it possesses, you can contact salesforce support for that.

The default indexed fields in salesforce are:

1) Primary key fields such as IDs, Names, OwnerIDs, Emails. These fields can be found in Leads, Contacts and Accounts objects.
2) Foreign key fields - These fields basically consists of all those fields used for Master:detail relationship or lookup relationship.
3) System generated time fields such as CreatedDate and LastModifiedDate.
4) Custom fields which are marked as External IDs

In order to view what all fields are indexed for any object, navigate to "Fields" section of an object. Navigate to Setup > "object name" > Fields

<img src="/assets/Indexed fields.png">

###### References

* http://www.salesforcegeneral.com/salesforce-articles/standard-indexed-fields.html
* https://salesforce.stackexchange.com/questions/218/what-standard-and-custom-fields-are-indexed

[[↑] Back to top](#salesforce-develop-questions)

### What is the difference betweeen insert() and database.insert()?
Both insert() and database.insert() are used as DML for inserting records in the object. However, they are a bit different when it comes to their functionality.

<table cellpadding="3">
<tr>
<td align="center">
<b>insert()</b>
</td>
<td align="center">
<b>database.insert()</b>
</td>
</tr>
<tr><td>This is a DML statement used for inserting records.</td><td>This is a method which can mirror the functionality of insert() with the options of complete or partial success.
</td></tr>
<tr><td>
This does not support partial insertion of the records. If an error occurs, none of the record will be inserted.
</td><td>
This comes with option of complete or partial insertion. In the syntax of this method, "true" means allOrNone functionality which is similar to insert(). However, if the syntax has "false" parameter, it will ignore the failed records and will insert the remaining records.
</td></tr>
<tr><td>
Rollback functionality is not supported with this statement.
</td><td>Rollback funtionality is available with this database method.
</td></tr>
</table>

###### References

* https://www.forcetalks.com/salesforce-topic/what-is-the-difference-between-insert-and-database-insert-in-salesforce/
* https://trailhead.salesforce.com/content/learn/modules/apex_database/apex_database_dml?trail_id=force_com_dev_beginner

[[↑] Back to top](#salesforce-develop-questions)

### What is the difference between SOQL and SOSL?
Both of these languages are used for fetching certain results from objects, however, the result for both the languages is different.

<table cellpadding="3">
<tr>
<td align="center">
<b>SOQL</b>
</td>
<td align="center">
<b>SOSL</b>
</td>
</tr>
<tr><td>SOQL which abbreviates for Salesforce Object Query Language is used for querying field(s) from a single object.</td><td>SOSL which abbreviates for Salesforce Object Search Language is used for querying only certain fields like email, text or phone, but from within multiple objects.
</td></tr>
<tr><td>
SOQL can be used in both apex classes and triggers.
</td><td>SOSL can only be used in apex classes and are not supported in the triggers.
</td></tr>
<tr><td>
SOQL uses "SELECT" keyword for fetching the results from the object.
</td><td>SOSL uses "FIND" keyword for fetching the results from multiple objects.
</td></tr>
<tr><td>
With SOQL, you know exactly in which object or field does your data exists.
</td><td>With SOSL, you do not know as to in which object or field does your data exists.
</td></tr>
<tr><td>
DML operations can be performed on the results of SOQL queries.
</td><td>With SOSL bringing in search results, DML operations cannot be performed on these search results.
</td></tr>
</table>

###### References

* https://developer.salesforce.com/forums/?id=906F00000008lJbIAI
* https://www.forcetalks.com/salesforce-topic/what-is-the-difference-between-soql-and-sosl-in-salesforce/

[[↑] Back to top](#salesforce-develop-questions)