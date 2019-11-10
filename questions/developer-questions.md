# Salesforce Develop Questions

Pull requests for suggestions and corrections are welcome!

## Fundamentals
* [What are governor limits? Why are they important?](#what-are-governor-limits-why-are-they-important)
* [What are the Bulkification best practices?](#what-are-the-bulkification-best-practices)
* [What are the key automation tools in Salesforce? How do you know when to use which?](#what-are-the-key-automation-tools-in-Salesforce-how-do-you-know-when-to-use-which)
* [What is the difference between force.com and salesforce.com?](#what-is-the-difference-between-force.com-and-salesforce.com)

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
* [What are the different ways we can share a record?](#what-are-the-different-ways-we-can-share-a-record)
* [What are sharing settings? Why are they important?](#what-are-sharing-settings-why-are-they-important)
* [What is Apex Managed Sharing?](#what-is-apex-managed-sharing)
* [How many ways can we share a record?](#how-many-ways-can-we-share-a-record)
* [What is a use case for sharing rules?](#what-are-some-of-the)


## SOQL & DML
* [What are the default indexed fields in Salesforce?](#what-are-the-default-indexed-fields-in-Salesforce)
* [What is difference insert() and database.insert()?](#what-is-difference-insert-and-database.insert)

## Data Modelling & Data Management
* [What Are The Types of SOQL Statements in SalesForce?](#what-are-the-types-of-soql-statements-in-salesforce)
* [When one wants to pass the collection to the query instead of passing one value which keyword helps us?](#when-one-wants-to-pass-the-collection-to-the-query-instead-of-passing-one-value-which-keyword-helps-us)
* [What is Future Annotation(@Future)?](#what-is-future-annotation-future)
* [What is Data Skew?](#what-is-data-skew)
* [Explain skinny table. What are the considerations for Skinny Table?](#explain-skinny-table-what-are-the-considerations-for-skinny-table)
* [Which fields are automatically Indexed in Salesforce?](#what-are-the-default-indexed-fields-in-Salesforce)
* [Which fields are excluded from a custom index?](#which-fields-are-excluded-from-a-custom-index)

## Logic & Process Automation 
* [What are the types of custom settings in Salesforce? What is the advantage of using custom settings?](#what-are-the-types-of-custom-settings-in-salesforce-what-is-the-advantage-of-using-custom-settings)
* [What are custom labels in Salesforce? What is the character limit of custom label?](#what-are-custom-labels-in-salesforce-what-is-the-character-limit-of-custom-label)
* [What are deterministic formula fields in Salesforce?](#what-are-deterministic-formula-fields-in-salesforce)

## Apex (in process)
* [Describe the 3 qualities of Apex that make it powerful?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [Why do we use start test & stop test annotations?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [What are the best practices for writing test classes?](#)
* [Name 3 governor limits you know? Why are they important? How do you resolve when you see such errors?](#)
* [What are the different types of collections in Apex? What are maps in Apex?](#w)
* [Why use of “@future” annotation?](#)
* [What are the different methods of batch Apex class?](#)
* [What is Trigger.new?](#)
* [What is the difference between SOQL and SOSL?](#what)
* [What is the difference between public and global class in Apex?](#wha)
* [What are the two options for when Apex Triggers can run?](#whats)
* [Explain the use of an Outbound Message?](#what)
* [What is the Save Order of Execution? Why is it important?](#what)
* [What is a wrapper class? Give one use case where you would use a wrapper class.](#what)
* [What is Batch Apex in Salesforce?](#)
* [What is Apex Scheduler?](#)
* [What is the Apex Trigger in Salesforce?](#)
* [What is an Apex transactions?](#)
* [What are static resources?](#)
* [What is the difference between public and global classes in Apex?](#h)
* [Why use Batch Apex instead of Normal Apex?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [What the difference between isNull and isBlank?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)

## Debug & Deployment Tools
* [What are the different ways of deployment in Salesforce?](#what-are-the-different-ways-of-deployment-in-salesforce)
* [Why do we need to write test classes? How to identify if a class is a test class?](#why-do-we-need-to-write-test-classes-how-to-identify-if-a-class-is-a-test-class)

## Scenario Based Questions
* [ What does it indicate if an error state this “list has no rows for assignment”?](#what-does-it-indicate-if-an-error-state-this-list-has-no-rows-for-assignment)


### What are the Bulkification best practices?
- Nested loops must be boycotted.
- Soql queries inside loops must be avoided.
- Use simple FOR loop instead of FOR each for better efficiency.
	Ex: 
	List<String> Accountkeys = new List<String>();
	for(integer i=0; i < Accountkeys.size(); ++i) { system.debug(Accountkeys[i])} <== Consumes lesser time
	for(String key : Accountkeys){ system.debug(key)} <== consumes more time
- Use collections like map to store data locally, so that you can get rid of expensive database calls.
- Always keep one trigger per object. No matter how complex one trigger becomes but multiple trigger misbehaves during bulk execution. You can use helper methods to reduce the complexity of the trigger also.
- Use batch class as much as you can during bulk operations as they have been designed to handle bulk easily.
- Keep track of limits by using Limits class to avoid hitting governor limits.
- Future methods are very helpful when you have to update a large set of data. You can continue with your synchronous transaction and save time for updation by asking future method to update records asynchronously.

[[↑] Back to top](#Salesforce-Develop-Questions)


### What are the key automation tools in Salesforce? How do you know when to use which?

- In salesforce, Process builder , Workflow, Flow builder and approval process are some key tools for automation.
- All these tools have separate significance to perform various business processes in salesforce.
- When you have a requirement of processing multiple statements together, process builder or flow builder should be your choice.
- When you want some action to be performed automatically on basis of time, you should refrain from using approval process.
- If you want an activity to be done based on user action, Flow builder is an ideal choice.
- If calling an apex class is a necessity, Process builder can be used.
- For Sending outbound messages, workflows have been recommended.
 So based on the various needs various automation can be utilized. Please have a look at below table which describes the uses of each automation in a better way.
 
<img src="/assets/Automated_features.PNG">

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are the different ways we can share a record?
We can share records using:
1. Roles
1. OWDs
1. Apex Sharing
1. Manual sharing
1. Sharing rules.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are sharing settings? Why are they important?

- The whole concept of access control can be visualized as 3 gates before you reach the treasury box (Speaking in layman terms)
- Like you have to cross all the gates to reach the treasure, the same way you have to cross path with 3 levels of configuration to actually achieve a successful access control on data. You can consider the 3 gates as metadata accesses to achieve the access on actual data. These gates are object setting, field settings and sharing settings which relates to object, field and the record respectively. Once you have object and field level permissions, you can choose to have record level permissions using sharing settings.
- Sharing settings can be achieved through Orgwidedefaults, Sharing rules or Apex sharing.
- For understanding its importantance, lets take a scenario: A multinational company does their business in various regions. Director of Finland watches the business in Finland and Director of India watches it in India. If director of india starts to see the business done by company in Finland too with total figures of India then it will becomes cumbersome for him to do analysis for a specific region. Hence, allowing the respective directors to see data of their region only may lead to increased analysis and sales. This simple scenario can be achieved using OWDs and sharing rules.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What is Apex Managed Sharing?

Apex Sharing is a ability provided to force.com developers to explicitly fullfill the requirement of record sharing of an application or a product programatically. If you want to built an app which shares records based on some criteria due to an event occurance, then nothing other than apex sharing can help you.
For example, AccountShare is the sharing object for the Account object, ContactShare is the sharing object for the Contact object, MyCustomObject will be named as MyCustomObject__Share.

[[↑] Back to top](#Salesforce-Develop-Questions)

### How many ways can we share a record?
There are 5 ways to share a record:
1. Roles
1. OWDs
1. Apex Sharing
1. Manual sharing
1. Sharing rules.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are your 3 favourite Salesforce blogs?

My personal favourites Salesforce bloggers are:
1. http://www.asagarwal.com         >>> lots of fantastic step-by-step guides
1. http://www.jitendrazaa.com/blog/ >>> fantastic articles on different topics, i.e. best chrome extensions for Salesforce
1. http://sfdcmonkey.com/	    >>> brings together best articles on everything related to Lightning

[[↑] Back to top](#Salesforce-Develop-Questions)

### Do you attend Salesforce developer community meetings?
Salesforce developer community meetings are my favourite. This might sound unreal but I attend every single developer community. These meetings improve my Salesforce knowledge gains and I meet Salesforce developers who inspire me. I make new friends every time. Moreover, the food offered in the break is awesome.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What do you do when you are stuck when you code?

`TextBook Definition:`
There are certain times when i get stuck while coding. In such case, I generally do some r&d on the internet crawling through many blogs and vlogs searching for solution. I try to find my doubts in developer forums or even post a question when no similiar question have been found. Once i find a solution, i apply it or in case no solution is available then i find a workaround. My first step generally is to google the exact error and know the root cause. Before moving to a workaround, i always consult a senior developer as experience is the key to solution.
Ex: I faced an error called "Mixed Dml exception" someday. I searched for the error on the internet for knowing the root cause. After reading few blogs, i came to know that it happens due to Dml of setup and non setup objects in the same transaction. Then i searched for the ways to separate that transaction. I found a clue Future methods. Then i searched for future methods and its syntax and embedded the solution.

`Street Definition:`
The first and foremost thing to fight to such a situation is not to loose faith in yourself. The best solution can be generated by you and you only. With that in mind, start googling the exact error or exception. Be brave, search for more blogs if the root cause is still hazy. There are leads or others developers to help you but you have to try to solve it on your own within a specified timeframe. If it's too much time consumed without even a clue, consult the lead immediately. You have already won the half way if you know the root cause. Because once you know the reason, you may have various way to solve it. Once sorted, say thanks to google and god!

[[↑] Back to top](#Salesforce-Develop-Questions)

### How many reputation points do you have on salesforce StackExchange?

`TextBook Definition:`
On StackExchange i just have 100 points currently. Reputation points on Stackexchange came on to my priority list a bit late but yes it is there in my bucket. Moreover, i am targetting to reach 1000 points very soon in a month or so.

`Street Definition:`
I use stackexchange relatively very less. Whenever i am stuck technically, i search for solutions on it and apart from this i am very less active. But recently i have started answering the questions for which i am pretty sure and you won't believe it gives me immense pleasure to help the community and earn a label in return. I compete with friends nowadays and excel myself. I have 100 points now which will be 1000 soon.

[[↑] Back to top](#Salesforce-Develop-Questions)

### Would you say you are passionate about Salesforce? If so why?

`TextBook Definition:`
I started working on salesforce due to a project requirement. The UI and funtionalities in salesforce attracted me towards it. When i came to know about solid functionality like sharing settings, I was absolutely amazed because when i compare it will other technologies or CRMs, it is really time consuming job to make such a funtionality whereas in salesforce you are getting it prebuilt. Hence it increased me interest. I started believing in salesforce when saw its thrice in a year upgrade process and most probably the dreamforce. Even writting code in apex and lightning are pretty straightforward and there are huge bunch of blogs and a wide community always ready to help. Finally it became my passion when i successfully deployed one project with full support from salesforce partners, salesforce community and the salesforce case support. Moreover, it also provided cetified developers and admins, hence finally with passion i selected it as my career.

`Street Definition:`
Frankly speaking, i came into salesforce due to high market demand and less developers available. Obviously a good pay was my first reason, but when i started exploring this CRM in depth i had no clue what i was looking it. At first it looked really difficult, so mamy thing so many functionality at one place but once i got a command using trailhead and the blogs, i was unstoppable. Sharing settings, profile and users, all other setup stuffs were mind bending initially but i grasped them and now i feel that there can be no better CRM to do this. Writting code in salesforce seems very much easy to me then any other technologies due to the really good supportive development environment. I started loving salesforce when i realized i am growing day by day in terms of knowledge, market upgradation, working with better clients and infrastructure and finally in payscale. Even such rapid growth of salesforce motivated me to stay connected to the community and love what you do. Hence salesforce became my passion and career both.

[[↑] Back to top](#Salesforce-Develop-Questions)

### Have you ever contributed to Salesforce's Ideas? If you could make any idea come true, what would it be?

`TextBook Definition:`
Yes, i always wished the Lookup rollup functionality should be a part of salesforce itself due to the daily demands. I hope salesforce may find it useful. By the way, we can't add rollup summary fields on lookup relationship and i wished if that is possible too with restrictions.

`Street Definition:`
I have already contribited the idea of Lookup rollup and asked the community to vote it. Tht thing is - in the intial stage of the project you sometimes are not sure what relation should be taken up, consider you choose lookup at that time, further at the later part of the project you got a functionlity to count child records and that becomes a mess at that time. You may have to write custom code for that. I believe that should already be there and recommend salesforce to add it. But again they are the better judge.

[[↑] Back to top](#Salesforce-Develop-Questions)

### Where do you see yourself in 3 years?

`TextBook Definition:`
Currently i am a developer with good coding and learning skills but i know that not enough. I have to rise to a technical lead position next coming years and despite of coding, i have to focus on becoming a good observer, orator, multi-tasker and a quick issue discoverer. With all these, new platform changes should also be grasped. I also have to serve the company by becoming their crucial asset earning handful of appreciations for myself. So in conclusion i want to be an expert of this domain, lead the projects and take the managerial responsibilities.

`Street Definition:`
In next 3 years, i want to learn every aspect of salesforce development. Either it is lightning components or lightning web components, i want to be fully expert on them with a live project hands on. I am looking for a designation step up with full confidence in handling a project smoothly. I have already handled modules in the past and i feel i am ready for the whole project itself. Although, every four month salesforce produces something new, it would also make myself a better developer day by day. Further, buying a car, marriage etc are also the part of my life in next 3 years. Yah, One thing i forgot is the World tour, hope to save much to complete a world tour soon.

[[↑] Back to top](#Salesforce-Develop-Questions)

### Do you enjoy being a Salesforce developer? Why?

`TextBook Definition:`
First things, you are working with a world dominating technology and you should be happy about it. This is an innovative platform which does innovations and ask you to be part of them. You may always find some traning guides and issue resolution steps somewhere. Readily available code repositories, appexchange products and function librabaries are always available to skip to start from scratch. The compiler and interpreter of the apex engine are seriously appreciated which helps you rectify your code in minutes. Further, the community trains and certify you also. So all in all salesforce development is the one i love.

`Street Definition:`
I am glad being one. Being salesforce developer is really an exciting job. It is for the people who seek adventure and never wish to settle down. The new generation is of that kind which wants to keep learning daily and salesforce is always ready to teach you. It keeps on upgrading the technology as per modern needs and forces its community to learn to catch up the market. It shows trust on you by certifying you and ensuring the community that he is worth it. You learn from trailhead, you apply it in real time, you search in community to help and you deliver it. There is no way you will be stuck, someone will always be there to help you. That's why i like being a exciting salesforce developer.

[[↑] Back to top](#Salesforce-Develop-Questions)


### What are governor limits? Why are they important?

Governor limits are runtime limits enforced by the Apex runtime engine to ensure that code does not monopolizes the resources which have been shared by various customers and organizations. These limits ensure the efficient processing of resources on the Force.com multitenant platform.


[[↑] Back to top](#Salesforce-Develop-Questions)

### What is the difference between force.com and salesforce.com?

- Salesforce.com is SAAS and force.com is PAAS.
- All the prebuilt products like sales or service, leads, reports, tabs etc are a part of salesforce.com and the possible customization products like visualforce page, classes, triggers, components etc are a part of force.com.
- Licenses for salesforce.com are pretty expensive than force.com's license.
- Salesforce.com is a leading CRM which have been built for targetting customers and social objectives whereas force.com helps delivering world class customized apps within short period of time.
- Salesforce.com focuses more on prebuilt functionality to complete stuffs by points and clicks whereas force.com uses programming or markup languages to build a product or output which is not offered as a part of salesforce CRM.
- Salesforce.com is a product built on the top of force.com platform.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are the default indexed fields in Salesforce?

`Textbook Definition:`
There are certain types of index fields in salesforce as stated below.
- Primary keys (Id, Name, and Owner fields).
- Foreign keys (Relationship fields like lookup or master detail).
- Dates fields (such as LastModifiedDate,createddate).

`Street Definition:`
Most of the system fields which acts as the key in their particular table are indexed fields. Like Account ID is an primary field of account table so it have been indexed. OwnerId on account is also an indexed field as it is a foreign key in account table representing users table. Indexing a fields makes database operation really fast so i many times use an external id field also for many purposes, but that is not default, rather a custom solution.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What is difference insert() and database.insert()?

`Textbook Definition:`
- DML Insert is known as a Dml statement whereas Database.insert() is a method derived from database class.
- Database insert is parameterized to support partial insert which is not possible in DML insert.
- DML insert doesn't support rollback which is a useful feature of Database.insert().
- DML insert doesn't return error or success records for further processing whereas Database.insert does.

`Street Definition:`
- For a bulk operation, if you wish to cancel the operation even if a single record gets errored out of bulk then you should use Insert() or if you wish you partially insert records and separate the failed once then you should use Database.insert().
- For exception handling, Database.insert() returns database.saveResult class so you can automatically create your own failed records object and process the inserted one. But if you want to rerun the operation then use Try catch block with insert() as per your needs.
- Using Database.insert() you can rollback very easily through parameters. However, rolling back using insert() is bit indirect. You can use try catch block and rollup in catch statement using Databse.rollback() method.
Example:
If we are inserting 200 records in an object, Where 5 records are prone to error and remaining others records are good.
In DML statement (Insert) all the 200 records will be failed, because if one record is incorrect or error means all other remaining records will not be inserted. It will throw error.
In Database.insert 195 records will be inserted, remaining 5 records will be failed.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What Are The Types of SOQL Statements in SalesForce?

`Textbook Definition:`
There are two types of SOQl statements Dynamic and Static. You can use either of them as per your needs.
Example-
String accountname = 'Salesforce Chef';
[select id from account where name=:accountname] ==> Static
String query = 'select id from account where name=\'' + accountname + '\''; ==> Dynamic

[[↑] Back to top](#Salesforce-Develop-Questions)

### When one wants to pass the collection to the query instead of passing one value which keyword helps us?

`Textbook Definition:`
IN keyword is used to pass a collection to the query.
Example-
List<String> AccountNames =  new List<String>('Youtube','Microsoft');
[select id from account where name IN :AccountNames]

[[↑] Back to top](#Salesforce-Develop-Questions)

### What is Future Annotation(@Future)?

`Textbook Definition:`
Future annotation identifies the method to run in separate thread asynchronously whenever the resources are available.

`Street Definition:`
Future annotation is used to mark a method as future method and future methods have the capability to run apart of the current context so that performance of the current operation can be enhanced by ensuring less chances of hitting a governor limit. Future methods run whether system have available resources so it will never hamper other processes.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What is Data Skew?

`Textbook Definition:`
When a parent have huge number of child records related to it through special relationships, then an imbalance occurs in the system which directly impacts the performance of the org. This situation is called as Data Skew. This huge number represents 10,000 or more.

`Street Definition:`
When a record or an account have more than 10,000 childs associated with it, we call this situation as Data Skew.

[[↑] Back to top](#Salesforce-Develop-Questions)

### Explain skinny table. What are the considerations for Skinny Table?

`Textbook Definition:`
Skinny tables generally contain frequently used fields and avoid joins. They tend to improve the performance of many read-only operations. Skinny tables are kept in sync with their source tables when the source tables are modified.
Considerations:
-Skinny tables can contain a maximum of 100 columns.
-Skinny tables can’t contain fields from other objects.
-For Full sandboxes: Skinny tables are copied to your Full sandbox orgs.

`Street Definition:`
Consider the skinny table as the index of the book. How easy it is to move to the topic of a heavy book you want to read by refering its page number from the index? and imagine the situation when the index of the book had been torn and you need to reach the particular topic, very disgusting! Similarly, when there are more than 2 million records in the org for a single object and you want to query one it will be a havok as you may face performance issues. To get rid of that, contact salesforce customer support and ask them to create a skinny table to the particular object. These skinny tables will act as an index in the database and may speed up many operations. These skinny tables are invisible to us and may be automatically used whereever applicable. Simple meaning of creating a skinny table is to make a field indexed and add it to a separate table. Every time you want to make a field indexed you need to contact salesforce support and ask the particular field to be added into the skinny table. With that benefit, salesforce have also placed some restricted on skinny table, please read the textbook definition for these restrictions or considerations.

[[↑] Back to top](#Salesforce-Develop-Questions)

### Which fields are excluded from a custom index?

`Textbook definition`
Various custom fields like multi-select picklists, text area (long), text area (rich), non-deterministic formula fields, and encrypted text field are excluded from the custom index.

`Street Definition:`
The fields which are either encrypted or designed to carry huge data like comments or description are excluded from custom index. Index is a key which takes you to main data so there is no point of storing huge data in the index rather your index should point to huge data.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are the types of custom settings in Salesforce? What is the advantage of using custom settings?

`Textbook Definition:`
There are two types of custom settings Heirarchy and List. The custom settings are basically stored in application cache memory and hence you don't need expensive DML calls to retrieve them. Even they are faster to access.

`Street Definition:`
Types of custom settings are already known to you. Since cache memory have better read write speeds than hard drives, custom settings are stored in this memory in order to retrieve data urgently and without any DML calls. So store your frequently used data in custom setting to stay away from governor limit hit.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are custom labels in Salesforce? What is the character limit of custom label?

`Textbook Definition:`
Custom labels are custom multilingual text values that can be accessed from Apex classes or Visualforce pages. They are generally used to develop custom multilingual applications. Each custom label has a limit of 1000 characters.

`Street Definition:`
Consider you are a end user and you downloaded an app exchange product. You liked the product and want to switch to your native lamguage instead of english. How can developers achieve this? They can't write various langugues on the visualforce page or component, hence they use custom labels which change their language dynamically based on user language selection.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are deterministic formula fields in Salesforce?

`Textbook Definition:`
The Formula fields whose value will be static and might not vary over time when a transaction updates a related entity, are called as deterministic formula fields. For being deterministic, value of formula fields should not be calculated on fly.

`Street Definition:`
You can make your formula fields deterministic by using only current object fields in the formula (no cross object formulas), not making dependency on current date and no reference to special fields.
Example:
Consider you have two fields on account: Company name and Account number.
You want to create a key which concates both the fields, creating formula will be a wisely decision and such a field is deterministic.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What are the different ways of deployment in Salesforce?

`Textbook Definition:`
Change Sets - native salesforce solution
Eclipse with Force.com IDE - widely used IDE
Ant migration tool - java based utility
Salesforce Package - managed or unmanged package

[[↑] Back to top](#Salesforce-Develop-Questions)

### Why do we need to write test classes? How to identify if a class is a test class?

`Textbook Definition:`
Salesforce strongly recommends using a test-driven development process which occurs at the same time as code development that means only the quality code should be deployed to production. For checking the quality of code, salesforce performs unit testing at their end while deployment. This unit testing is achieved using test classes and hence without test classes there can be no deployment in salesforce. Such a test class should cover minimum 75% test cases and is identified by @isTest annontation over the class declaration.

[[↑] Back to top](#Salesforce-Develop-Questions)

### What does it indicate if an error state this “list has no rows for assignment”?

`Textbook Explanation:`
This is System.Query Exception. This error means that the query which you fired returned no records from the database so the program can't assign anything to the variable.
Example:
Account acc = [select id from account where name='Salesforce Chef'];
Consider the above query, if the there is no record in database with the name "Salesforce Chef" then the “list has no rows for assignment” error will occur saying "no records were found to assign data to acc".

[[↑] Back to top](#Salesforce-Develop-Questions)
