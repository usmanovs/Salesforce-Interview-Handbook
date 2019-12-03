# Salesforce Develop Questions

Pull requests for suggestions and corrections are welcome!

## Fundamentals
* [What are governor limits? Why are they important?](#what-are-governor-limits-why-are-they-important)
* [What are the Bulkification best practices?](#what-are-the-bulkification-best-practices)
* [What is the difference between force.com and salesforce.com?](#what-is-the-difference-between-forcecom-and-salesforcecom)

## Behavioral
* [What are your 3 favourite Salesforce blogs?](#what-are-your-3-favourite-Salesforce-blogs)
* [Do you attend Salesforce developer community meetings?](#do-you-attend-Salesforce-developer-community-meetings)
* [What do you do when you are stuck when you code?](#what-do-you-do-when-you-are-stuck-when-you-code)
* [How many reputation points do you have on salesforce StackEchange?](#how-many-reputation-points-do-you-have-on-salesforce-stackExchange)
* [Would you say you are passionate about Salesforce? If so why?](#would-you-say-you-are-passionate-about-salesforce-if-so-why)
* [Have you ever contributed to Salesforce's Ideas? If you could make any idea come true, what would it be?](#have-you-ever-contributed-to-salesforces-ideas-if-you-could-make-any-idea-come-true-what-would-it-be)
* [Where do you see yourself in 3 years?](#where-do-you-see-yourself-in-3-years)
* [Do you enjoy being a Salesforce developer? Why?](#do-you-enjoy-being-a-salesforce-developer-why)

## Sharing & Security
* [What is Apex Managed Sharing?](#what-is-apex-managed-sharing)
* [How many ways can we share a record?](#how-many-ways-can-we-share-a-record)
* [What is a use case for sharing rules?](#what-is-a-use-case-for-sharing-rules)

## SOQL & DML
* [What are the default indexed fields in Salesforce?](#what-are-the-default-indexed-fields-in-Salesforce)
* [What is difference insert() and database.insert()?](#what-is-difference-insert-and-databaseinsert)
* [What is the difference between SOQL and SOSL?](#what-is-the-difference-between-soql-and-sosl)

## Data Modelling & Data Management
* [What Are The Types of SOQL Statements in SalesForce?](#what-are-the-types-of-soql-statements-in-salesforce)
* [When one wants to pass the collection to the query instead of passing one value which keyword helps us?](#when-one-wants-to-pass-the-collection-to-the-query-instead-of-passing-one-value-which-keyword-helps-us)
* [What is Future Annotation(@Future)?](#what-is-future-annotation-future)
* [What is Data Skew?](#what-is-data-skew)
* [Explain skinny table. What are the considerations for Skinny Table?](#explain-skinny-table-what-are-the-considerations-for-skinny-table)
* [Which fields are excluded from a custom index?](#which-fields-are-excluded-from-a-custom-index)

## Logic & Process Automation 
* [What are the types of custom settings in Salesforce? What is the advantage of using custom settings?](#what-are-the-types-of-custom-settings-in-salesforce-what-is-the-advantage-of-using-custom-settings)
* [What are custom labels in Salesforce? What is the character limit of custom label?](#what-are-custom-labels-in-salesforce-what-is-the-character-limit-of-custom-label)
* [What are deterministic formula fields in Salesforce?](#what-are-deterministic-formula-fields-in-salesforce)

## Apex (in process)
* [Describe the 3 qualities of Apex that make it powerful?](#)
* [Why do we use start test & stop test annotations?](#)
* [Why do we write test classes?](#)
* [What are the best practices for writing test classes?](#)
* [Name 3 governor limits you know? Why are they important? How do you resolve when you see such errors?](#)
* [Why use  “@future” annotation?](#)
* [What are the different methods of batch Apex class?](#)
* [What is Trigger.new?](#)
* [What is the difference between public and global class in Apex?](#wha)
* [What is the Save Order of Execution? Why is it important?](#what)
* [What is a wrapper class? Give one use case where you would use a wrapper class.](#what)
* [What is an Apex transaction?](#)
* [What are static resources?](#)
* [What the difference between isNull and isBlank?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)

## Debug & Deployment Tools
* [What are the different ways of deployment in Salesforce?](#what-are-the-different-ways-of-deployment-in-salesforce)
* [Why do we need to write test classes? How to identify if a class is a test class?](#why-do-we-need-to-write-test-classes-how-to-identify-if-a-class-is-a-test-class)
* [Why make Profiling Finest?](#why-make-profiling-finest)

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

### What Are The Types of SOQL Statements in SalesForce?
There are two types of SOQL Statements in salesforce:

1) Static SOQL - This statement can be used in the Apex method using square brackets []. In this statement you can specify a criteria for the query where you can return results based on some specific input which can be either user input or hard coded. For example: List<Account> lstAccount = [select id,name form account where name ='test'];

2) Dynamic SOQL - In order to create a dynamic SOQL statement, you need to use Database.Query() method. This statement can be used when you want the query to return results based on the results achieved during the runtime. For example: List<sObject> L = Database.query(string);

###### References

* https://www.forcetalks.com/salesforce-topic/what-are-the-types-of-soql-statements-in-salesforce/
* https://www.biswajeetsamal.com/blog/tag/sosl/

[[↑] Back to top](#salesforce-develop-questions)

### When one wants to pass the collection to the query instead of passing one value which keyword helps us?
IN keyword can be used to pass the collection to the query instead of passing one value. For example: SELECT Firstname, Lastname FROM user WHERE firstname IN ('test1','test2')

You can also use a string of data in IN statement using ":string" in place of the values.

###### References

* https://developer.salesforce.com/forums/?id=906F00000008ytAIAQ

[[↑] Back to top](#salesforce-develop-questions)

### What is Future Annotation(@Future)?
The future annotation denoted by "@future" is a method which helps the user to run certain processes asynchronously but in the future when the resources are available. This way one can avoid other users to be blocked for certain operations because of the unavailability of the resources. One can also keep governor limits in check with the use of this method.

An example of future method usage is:

global class YourClassName {
 
  @future
 
  public static void yourFutureMethodName(List<Id> recordIds) {
 
    List<Account> acc = [Select Id, Name from Account Where Id IN :recordIds];
 
    // process account records to do awesome stuff
 
  }
 
}

###### References

* https://www.salesforcetutorial.com/future-method-salesforce-future/
* https://webkul.com/blog/future-annotation-salesforce/

[[↑] Back to top](#salesforce-develop-questions)

### What is Data Skew?
When a particular parent object has more child records (typically more than 10,000 records) or if a single user is an owner of more than 10,000 records, this situation is termed as data skew. This situation can lead to performance problems when any action is been performed on that parent object or any updation is done by the user on the owned records. Based on the objects where data skew is happening, it can be of three types:

1) Account data skew - This happens when a particular parent object has too many child objects.

2) Ownership skew - This happens when a single user owns a large number of records of the same object.

3) Lookup Skew - This happens when a lookup is created on an object which has a great amount of records associated with it.

###### References

* https://sfdcbeginner.com/what-is-data-skew-in-salesforce.html
* https://www.forcetalks.com/salesforce-topic/what-is-data-skew-in-salesforce/

[[↑] Back to top](#salesforce-develop-questions)

### Explain skinny table. What are the considerations for Skinny Table?
Skinny table goes by its name. This is a shredded form of your object which is maintained in a table form only with the frequently used fields. Skinny tables are created from a source table and are in sync to it, so that any changes made to the source table reflect the changes in skinny table too. However, this cannot be created by the user and salesforce customer support needs to be contacted for creating a skinny table. Below image shows as to how a skinny table is formed and can be a performance booster for certain operations.

<img src="/assets/Skinny table.png">

Considerations for Skinny Table:

1) Skinny table should have fields from the same object. An object's skinny table cannot have fields from other object.
2) Skinny table can have a maximum of 100 fields from the object.
3) Skinny tables cannot include soft-deleted records.
4) Skinny tables are not created automatically in any sandbox environment, except Full Sandbox. It can only be created by with the help of Salesforce support.

###### References

* https://developer.salesforce.com/docs/atlas.en-us.salesforce_large_data_volumes_bp.meta/salesforce_large_data_volumes_bp/ldv_deployments_infrastructure_skinny_tables.htm
* https://sfdcbeginner.com/what-are-skinny-tables-in-salesforce.html
* https://www.jitendrazaa.com/blog/salesforce/large-data-volumes-ldv-in-salesforce/#more-3855

[[↑] Back to top](#salesforce-develop-questions)

### Which fields are excluded from a custom index?
A custom index can be created for both standard and custom fields, however, following field types are restricted from being created as custom index:

- Text fields (long or rich)
- Multi select picklist fields
- Non-deterministic formula fields like Today()
- Currency fields
- Excypted text fields 

###### References

* https://help.salesforce.com/articleView?id=000325247&language=en_US%C2%A0&type=1&mode=1
* https://salesforce.stackexchange.com/questions/218/what-standard-and-custom-fields-are-indexed
* https://www.jitendrazaa.com/blog/salesforce/large-data-volumes-ldv-in-salesforce/#more-3855

[[↑] Back to top](#salesforce-develop-questions)

### What are the types of custom settings in Salesforce? What is the advantage of using custom settings?
Custom settings in salesforce is more like creating a custom object, which can be used to create a set of custom data. Depending on the type of custom settings, the data can be accessed organization wide or can be accessed by limited users. Below are the two types of custom settings available in the salesforce:

1) List Custom Settings - This custom setting is used when a reusable set of data is required organization wide. You can create a list of statis data in this custom setting which will not be limited to any profile or user. Example of list custom setting can be a list of abbreviations of country names.

2) Hierarchy Custom Settings - As the name suggests, this custom setting uses an already existing hierarchical pattern in order to personalize some data for certain users or profiles. Hierarchy works in the order of organization, profile and user, where the later overrides the settings of the previous.

In order to create a custom setting, navigate to Setup > Build > Custom Settings and create a new custom setting for your org.

<img src="/assets/Custom settings.png">

The main advantage of using custom settings is that it is available in application cache. This means that you do not have to do any SOQL query everytime for the data which will keep the governor limits in check and is also cost-effective. This plays a crucial rule in the multitenant environment, utilizing the available resources carefully.

###### References

* https://www.janbasktraining.com/blog/custom-setting-salesforce/
* https://help.salesforce.com/articleView?id=cs_define.htm&type=5
* https://www.forcetalks.com/salesforce-topic/what-are-the-types-of-custom-settings-in-salesforce/

[[↑] Back to top](#salesforce-develop-questions)

### What are custom labels in Salesforce? What is the character limit of custom label?
Custom labels basically facilitates the user in creating text labels which can be used in multilingual applications. These labels can be translated into any Salesforce supported language and this helps in creating application which will show texts based on user's native language. In order to create custom label for the org, navigate to Setup > Build > Create > Custom Labels and click on "New Custom Label".

<img src="/assets/Custom label.png">

A user can create a maximum of 5,000 custom labels in an org and they can be a maximum of 1,000 characters long. These custom labels can be accessed through apex classes, lightning components or visualforce pages.

###### References

* https://help.salesforce.com/articleView?id=cl_about.htm&type=5
* https://webkul.com/blog/how-to-use-custom-labels-in-salesforce/

[[↑] Back to top](#salesforce-develop-questions)

### What are deterministic formula fields in Salesforce?
Deterministic formula fields are those formula fields whose value remains static and are not dependent on any other field for the output value. Example of deterministic formula field can be a hyperlink field where we can hardcode a link to be accesses and this will never change unless done by a user manually.

###### References

* https://www.edureka.co/blog/interview-questions/salesforce-interview-questions/
* https://developer.salesforce.com/forums/?id=9060G000000I45EQAS

[[↑] Back to top](#salesforce-develop-questions)

### What are the different ways of deployment in Salesforce?
There are various tools available for the purpose of deployment in salesforce. However, there are three major ways or tools which are usually used by developers for deployment in the salesforce:

1) Change Sets - This is considered to be the best way of doing the deployment as it comes with the feature of point and click. This means that you only have to point to the organization on which you need to deploy the changes and click on Deploy. In order to do deployment using change sets, the user have to first create deployment connection between the two organizations after which deployment can be done swiftly. Deployment using change set can be either outbound change set or inbound change set, where outbound change set refers to sending the changes from your organization to another organization and inbound change set refers to sending changes from another organization to your organization.

In order to do deployment using change sets, navigate to Setup > App Setup > Deploy and select the type of deployment.

<img src="/assets/Change sets.png">

2) Force.com IDE - Force.com IDE is an Eclipse plugin using which you can do the deployment on any Salesforce organization. Unlike change sets, this does not require any deployment connection for doing the deployment. This is another commonly used way of deployment, however, it is not recommended to use if there are more than 100 test classes to be deployed. Eclipse does not response with so many test classes and often end up being hang.

3) Force.com Migration Tool ANT - ANT is a migration tool which provides the user with command line functionality for doing the deployment. This also does not require any prior deployment connection. This is most recommended way of deployment and this tool works well with Jenkins for deployment purpose. This is the best tool if your company is more into CI/CD. 

###### References

* https://www.brcline.com/blog/salesforce-deployment-methods
* https://sfdcbeginner.com/salesforce-deployment-methods.html

[[↑] Back to top](#salesforce-develop-questions)

### Why do we need to write test classes? How to identify if a class is a test class?
Test classes are basically written to perform unit testing by the developer. When a piece of code is written, it is quite essential that it should provide the required output and this can be tested using a test class. This also provides Code Coverage, which should be at least 75% in order for the code to be deployed to the production org. Test classes contain test methods and test data using which a developer can perform unit testing so as to find the bug and fix it before it reaches another level of software development.

A test class is often annotated by @isTest to make it appear different and identifiable.

###### References

* https://www.forcetalks.com/salesforce-topic/why-do-we-need-to-write-test-classes-and-how-to-identify-if-a-class-is-a-test-class-in-salesforce/
* https://www.janbasktraining.com/blog/test-classes-apex-salesforce/

[[↑] Back to top](#salesforce-develop-questions)

### Why make Profiling Finest?
Profiling is basically done to measure the performance of the application and to check for all the bottlenecks which are creating performance issues. In order to do a detailed profiling, debug logs can be created with the debug level being set to "Finest". Setting the debug level to "Finest" will bring you even the minute detail so that you can know as to which area of the application is creating performance issues. This helps in resolving the issues and creating a swift application.

###### References

* https://developer.salesforce.com/blogs/engineering/2013/05/force-com-performance-profiling-using-the-developer-console.html
* https://developer.salesforce.com/blogs/2014/05/a-guide-to-application-performance-profiling-in-force-com.html

[[↑] Back to top](#salesforce-develop-questions)