## Salesforce Admin Questions

Pull requests for suggestions and corrections are welcome!

## Salesforce Fundamentals
* [How can we find out what licenses the org has and how many licenses are available?](#how-can-we-find-out-what-licenses-the-org-has-and-how-many-licenses-are-available)
* [What is a sandbox org? What are the different types of sandboxes in Salesforce?](#what-is-a-sandbox-org-what-are-the-different-types-of-sandboxes-in-salesforce)
* [What useful information can you find on the company information page?](#what-useful-information-can-you-find-on-the-company-information-page)

## Security & Access
* [What is a profile](#what-is-a-profile)
* [What is the difference between a profile & permission set?](#what-is-the-difference-between-a-profile--permission-set)
* [What is the difference between role & profile?](#what-is-the-difference-between-role--profile)
* [What are sharing settings?](#what-are-sharing-settings)
* [What’s the difference between Record Types & Page Layouts? What is the use of each?](#whats-the-difference-between-record-types--page-layouts-what-is-the-use-of-each)
* [Can you delete a user? Why not?](#can-you-delete-a-user-why-not)
* [What are Audit Fields?](#what-are-audit-fields)

## Data Modelling
* [What is the difference between a lookup relationship & master:detail relationship?](#what-is-the-difference-between-a-lookup-relationship--masterdetail-relationship)
* [What is an External lookup?](#what-is-an-external-lookup)
* [Why do we create relationships between objects?](#why-do-we-create-relationships-between-objects)
* [What is a self-relationship?](#what-is-a-self-relationship)
* [What is a junction object? What do we use them for?](#what-is-a-junction-object-what-do-we-use-them-for)
* [What happens if you delete a field?](#what-happens-if-you-delete-a-field)
* [What can you do with a schema builder?](#what-can-you-do-with-a-schema-builder)

## Sales, Service, Analytics, Data Management
* [What is a price book?](#what-is-a-price-book)
* [When you convert a Lead what does it become?](#when-you-convert-a-lead-what-does-it-become)
* [What is a case?](#what-is-a-case)
* [What are the key 3 report formats available in Salesforce?](#what-are-the-key-3-report-formats-available-in-salesforce)
* [What are the 3 key differences between Data Loader & Data Import Wizard?](#what-are-the-3-key-differences-between-data-loader--data-import-wizard)
* [What kind of report can be used in a Salesforce dashboard?](#what-kind-of-report-can-be-used-in-a-salesforce-dashboard)

## Automation
* [What are the key automation tools in Salesforce? How do you know when to use which?](#what-are-the-key-automation-tools-in-salesforce-how-do-you-know-when-to-use-which)
* [What is a validation rule?](#what-is-a-validation-rule)
* [What business problems do approval processes solve?](#what-business-problems-do-approval-processes-solve)
* [Which options do you have to make a field required?](#which-options-do-you-have-to-make-a-field-required)

### How can we find out what licenses the org has and how many licenses are available?
A license enables a user to use certain features of Salesforce in your org. To view  all licenses  available for the org, the user has to be in Setup bar and in the Quick Find type “Company Information” and click on “Company Information” as shown in the image

<img src="/assets/search bar.png">

- Navigate to “User Licenses” section

Here you will be able to see all the available licenses for the org. In this section, you will be able to see all the details related to licenses as to their status, total number of licenses, number of used licenses along with the remaining number of licenses and the expiration date of the licenses.

<img src="/assets/available licenses.png">

###### References

* https://help.salesforce.com/articleView?id=users_understanding_license_types.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### What is a sandbox org? What are the different types of sandboxes in Salesforce?
Sandbox org is a replica of the metadata (and data if it is a partial or full sandbox) from the production org. Sandbox can be used for development and testing. Metadata changes from sandbox can be migrated from sandbox to production using change sets.

1) Developer Sandbox
2) Developer Pro Sandbox
3) Partial Sandbox
4) Full Sandbox

In order to create a sandbox, the user can navigate to Setup > Data Management > Sandboxes and the user will see following page:

<img src="/assets/sandbox.png">

Here the user can view as to what all sandbox licenses does an org have and how many are still available to be created. From the “New Sandbox” button, the user can create a new sandbox org. For a detailed difference between the four types of sandbox orgs, please refer to the following image:

<img src="/assets/types of sandboxes.png">

###### References

* https://www.salesforcetutorial.com/introduction-to-sandboxes/

[[↑] Back to top](#salesforce-admin-questions)

### What useful information can you find on the company information page?
Here you can find info on User Licenses, Permission Set Licenses, Feature Licenses and Usage-based Entitlements. Furthermore, here is other critical information that you find on this page:

1) Default Locale of the org >>>  France vs USA
2) Default Time Zone of the org which will be assigned to all the users >>> what date shows when a record is created
3) Used Data Space (in MBs) >>> records (i.e. Account records) you create count toward this
4) Used File Space (in MBs) >>> attached files (i.e. images) you attach to the records count toward this
5) Salesforce.com Organization ID >>> critical when you contact Salesforce support 
6) Organization Edition >>> controls what Salesforce features are available for you. 
7) API requests made in last 24 hours >>> you will be restricted from making API requests if you are hitting the limit
8) Instance >>> used to see if Salesforce has any Trust issues for your instance

There are other useful fields which are available to the user, for which you can refer to the following screenshot:

<img src="/assets/organization information.png">

###### References

* https://help.salesforce.com/articleView?id=users_understanding_license_types.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### What is a profile?
A profile is a combination of various settings and permissions which enables the user to perform certain tasks in salesforce. For example, they can be: Access to Tabs, Administrative Permissions, General User Permissions, Object Permissions. A profile can have multiple users but a user can have only one profile in the org. There are two types of profiles in the salesforce:

1) Standard Profiles - Standard profiles are the default profiles provided by the salesforce, even for the free license. These profiles cannot be deleted by anyone and they are generally six (6):
 - System Administrator
 - Standard User
 - Solution Manager
 - Read Only
 - Marketing User
 - Contract Manager

2) Custom Profiles - These are the profiles created by users and can be deleted. Custom profiles have "Custom" column checked for them on the view profile screen.

###### References

* https://www.salesforcetutorial.com/working-profiles-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What are the differences between a profile & permission set?
A user can have only 1 profile but many permissions ets. Typically, a profile is used to provide basic permissions to the user (i.e. access to certain Apps, Opportunity object) while permission sets are used to expand the permissions to certain users of the profile (i.e. edit or delete Opportunities). A case in point: the sales team uses the Sales profile but you want the sales manager to have more powers so you give him/her a permission set.

One more difference between a profile and permission set is that a profile can be used to grant or revoke a permission to the user, but a permission set can only grant or extend the permission. One cannot remove a permission with the help of a permission set.

A list of all other differences between a profile & permission set can be found on this helpful StackExchange [post](https://salesforce.stackexchange.com/questions/119220/exclusive-differences-profiles-vs-permission-sets/119297)
###### References

* https://www.salesforcetutorial.com/working-profiles-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What is the difference between role & profile?
A role in salesforce is basically defining a role of the user in the organization. It works in hierarchy; hence, by default all the users with superior roles can view and edit the records created by their subordinates. This can be changed by unchecking the checkbox under the column "Grant Access Using Hierarchies" under Sharing Settings.

What records a user will see is defined by its role, however, what  the user can do with the record will be defined by the user's profile. Another major difference between them is that defining profile is mandatory, whereas, defining role is not mandatory.

###### References

* https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/admin_roles.htm#!
* https://developer.salesforce.com/forums/?id=9060G000000UUa0QAG

[[↑] Back to top](#salesforce-admin-questions)

### What are sharing settings?
The sharing settings control a users access to records that they don't own. The 3 different levels of sharing available are:
1) Private - Only the owner of the record has access to the record
2) Public Read only - The record will be available for public access but the users will only be able to view it and cannot edit it
3) Public Read/Write - The record will be available for public access and everyone having access to the record can edit it as well

This is from here the user can change the access settings for both default (limited to few objects like Account and Contract, Contact, Case, Opportunity) and all custom objects. Also from here, a user can define rules based on which the sharing settings will apply and only those records will be shared which matches the defined rules. For viewing sharing settings and to create rules, you can navigate to Setup > Settings > Security > Sharing Settings.

<img src="/assets/View sharing settings.png">

###### References

* https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_bulk_sharing_understanding.htm#!

[[↑] Back to top](#salesforce-admin-questions)

### What’s the difference between Record Types & Page Layouts? What is the use of each?
An organization can have multiple businesses and accordingly can have various picklist values. Record types let you collaborate them and assign it to the users as per their profiles. While creating a record type, you can assign a page layout which can be default to all the profiles in the org, or you can even designate different layouts to different profiles.

<img src="/assets/Record type page layout setting.png">

On the other hand, as the name suggests, page layouts basically lets you define as to what all elements will be visible on the record. With the help of page layouts, you can place Fields, Buttons, Related Lists and many more, as per your convenience. You can also control the settings of a field as to what all fields will be visible, which field will be read-only field and what all fields will be required fields. There are three ways of assigning page layout:

1) From record types page

<img src="/assets/Page layout assignment 1.png">

2) From page layouts page

<img src="/assets/Page layout assignment 2.png">

3) From profiles page

<img src="/assets/Page layout assignment 3.png">

###### References

* https://inspireplanner.com/blog/differences-record-types-page-layouts-to-know/

[[↑] Back to top](#salesforce-admin-questions)

### Can you delete a user? Why not?
A user cannot be deleted in the salesforce. The only way is to deactivate the user and to do so, you can navigate to Setup > Administration > Users > Users > Edit <user>.

<img src="/assets/Deactivate user.png">

On the edit user page, uncheck the checkbox for "Active" field and click on Save.

The reason why a user cannot be deleted is that the user might be an owner of certain records and deleting the user will make the record inaccessible to other users of the org. This will release the license assigned to the user and you can create a new user with that revoked license.

###### References

* https://success.salesforce.com/answers?id=90630000000ZepDAAS

[[↑] Back to top](#salesforce-admin-questions)

### What are Audit Fields?
Audit fields are the important fields available to keep a track of all the information of the org. These are quite valuable fields at the time of auditing. Below mentioned fields combined are known as audit fields:

- CreatedDate
- CreatedById
- LastModifiedDate
- LastModifiedById
- systemModStamp

These fields play important role when you are trying to import your data into your salesforce org and are willing to keep the audit fields similar to the source. In order to do so, you will have to enable "Enable "Set Audit Fields upon Record Creation” and “Update Records with Inactive Owners"" permission. This can be done from Setup > Platform Tools > User Interface > User Interface.

<img src="/assets/Audit fields permission.png">

The only field for which you cannot set any value is "systemModStamp".

###### References

* https://developer.salesforce.com/docs/atlas.en-us.api.meta/api/system_fields.htm
* https://www.linkedin.com/pulse/system-fields-audit-salesforce-santosh-chitalkar

[[↑] Back to top](#salesforce-admin-questions)

### What is the difference between a lookup relationship & master:detail relationship?
<table cellpadding="3">
<tr>
<td align="center">
<b>Lookup Relationship</b>
</td>
<td align="center">
<b>Master:Detail relationship</b>
</td>
</tr>
<tr><td>This relationship can be created between any two objects, i.e., standard and custom objects.</td><td>
This relationship can also be created between standard and custom objects, but standard object should be the master.
</td></tr>
<tr><td>
</td><td>
This is a parent child relationship where master is parent and detail is child.
</td></tr>
<tr><td>
The related two objects does not require any parent object.
</td><td>
All the child objects need to have a parent object.
</td></tr>
<tr><td>
If the parent record is deleted, child record remains unaffected.
</td><td>
If the parent record is deleted, all the related child records are also deleted.
</td></tr>
<tr><td>
Every object has its own sharing and security properties.
</td><td>
All the related child objects inherits the security and sharing properties from the parent.
</td></tr>
<tr><td>
There can be a maximum of 25 lookups on an object.
</td><td>
An object can be a master to a maximum of 2.
</td></tr>
</table>

In order to create any of the above relationship between the objects:

1) Navigate to Setup > Create > Objects

<img src="/assets/Objects.png">

2) Click on any object
3) Navigate to Custom Fields & Relationships
4) Click on New

<img src="/assets/Types of relationships.png">

From here you can select the type of relationship you want to create by following the steps of the wizard.

###### References

* https://www.forcetalks.com/salesforce-topic/what-is-the-difference-between-look-up-and-master-detail-relationship/
* https://developer.salesforce.com/forums/?id=906F00000008mhlIAA
* http://sfdcsrini.blogspot.com/2015/10/difference-between-master-detail.html

[[↑] Back to top](#salesforce-admin-questions)

### What is an External lookup?
External lookup in salesforce is used when we have to link an external source of data with our salesforce org. In this case, we can use all the available objects including standard, custom and even external objects to be linked with the external database. However, the only condition here is that only the external object can be treated as a parent object and no other object type can be a parent here.

The linking can be made with the help of fields in the linked objects which have the same data. An External ID is created in the parent external object which maps with the appropriate field in the child object. In order to create an external lookup, you need to follow the following steps:

1) Navigate to Setup > Create > Objects

<img src="/assets/Objects.png">

2) Click on any object
3) Navigate to Custom Fields & Relationships
4) Click on New

<img src="/assets/External lookup.png">

###### References

* https://cloudworks.ae/what-is-the-external-lookup-relationship-in-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### Why do we create relationships between objects?
Objects contain data and all the data cannot be maintained in one single table. Thus, all the objects have their specific data and in order to get the data from different objects and show it in one single place, we create relationships between the objects. It is just like combining two tables from the database using unique and foreign key. There are various types of relationships including master:detail relationship, lookup relationship, and many-to-many relationships.

[[↑] Back to top](#salesforce-admin-questions)

### What is a self-relationship?
As the name suggests, this is a kind of relationship where an object is linked with itself. So, in here rather than combining two different tables in order to show the data, we create a lookup on the same object to be referred. This could be understood with an example. Let us say we have an object “Part” and it can be a possibility that the same part is replaced later with some other parts. Thus, in order to link both the parts, we would require to reference the same table rather than some other object’s table.

###### References

* https://www.edureka.co/blog/salesforce-tutorial
* https://www.forcetalks.com/salesforce-topic/what-is-a-self-relationship-in-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What is a junction object? What do we use them for?
Junction object is a custom object basically used to create a many-to-many relationships between the objects. In order to achieve the junction functionality, we have to use two master-detail relationships, each of them pointing to specific objects. For example, we have a car dealership where a customer can have multiple vehicles and a vehicle can be owned by various customers, via selling or exchange programs. Thus, we will have to create a many-to-many relationships between the customer and vehicle objects and in order to do so, we will create a junction object “Cars” which will link them both.

Junction object can be created as any other custom object and then from within the junction object, you can use master-detail relationship under “Custom Fields & Relationships” related list by selecting respective objects.

###### References

* https://www.forcetalks.com/salesforce-topic/what-is-the-use-of-junction-object-in-salesforce/
* https://www.sfdc-lightning.com/2018/11/what-is-junction-object-in-salesforce.html

[[↑] Back to top](#salesforce-admin-questions)

### What happens if you delete a field?
When a field is deleted, its associated data is also deleted and you will not be able to track the changes to the field anymore. All these deleted fields and data are stored for 15 days so that the user can restore the deleted data, if required. Or else after 15 days it will be permanently deleted or it can be deleted by the user permanently before that as well. Standard fields cannot be deleted, however, custom fields can be deleted.

In order to delete a field, navigate to the required object and click on the name of the object. On the fields which can be deleted, you will see a drop down arrow as shown in the screenshot below. From the drop down, select the Delete option and click on Save/Confirm/Delete button on the next screen.

<img src="/assets/Delete field.png">

###### References

* https://help.salesforce.com/articleView?id=deleting_fields.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### What can you do with a schema builder?
Schema builder is a graphical representation of all your objects and their relationships with each other.

<img src="/assets/Schema builder details.png">

As you can see in the above image, you can view all the fields of the selected objects from the left sidebar under Objects column. Also, at the top right corner, you can view all the legends which will help you in better understanding the relationships between the objects. From this place, it is not just viewing the details, you can even add and modify objects from here.

To reach to the schema builder navigate to Setup > App Setup > Schema Builder

<img src="/assets/Schema builder.png">

###### References

* https://www.tutorialspoint.com/salesforce/salesforce_schema_builder.htm

[[↑] Back to top](#salesforce-admin-questions)

### What is a price book?
A price book in salesforce is to store the prices of the products that your company deals in. Like if your company is providing some services to the customers, so this book will contain all the prices of your services. These are the standard prices which are stored in standard price book. However, if you have to customize the prices as per the customers, you can always create a custom price book.

To create a price book:

1) Click on "+" icon on the top row of the home page.
2) Search for "Price Books"

<img src="/assets/+sign.png">

3) Click on New to create a new price book

<img src="/assets/New price book.png">

###### References

* https://help.salesforce.com/articleView?id=pricebooks_landing_page.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### When you convert a Lead what does it become?
When an initial contact with the customer is initiated, a lead is generated in the salesforce. Now, depending on the further interactions, a lead can be converted into either an opportunity, an account or a contact.

If the customer shows any interest in buying the product/service you are offering, a lead turns into an opportunity. When a customer buys your product/service, the opportunity is closed with the status of "Closed/Won". This creates an account in the salesforce under your org and a corresponding contact is also created for the purpose of further communication.

However, if the customer shows no interest in buying the product/services, it is closed with the status of "Closed/Lost".

###### References

* https://salesforce.stackexchange.com/questions/42212/what-happens-when-a-lead-is-converted

[[↑] Back to top](#salesforce-admin-questions)

### What is a case?
A case in salesforce can be looked upon as a support ticket. With the help of this case, a customer can raise their concern either through a phone call or sending an email to a specific support email or can log a case/ticket from the customer support portal provided by the company.

###### References

* https://help.salesforce.com/articleView?id=cases_def.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### What are the key 3 report formats available in Salesforce?
In salesforce, in order to represent some data on a report, a user can use these key 3 report types, depending on the type of data they want to represent:

1) Tabular - As the name suggests, you will generate a report which will have the data in a tabl format showing all the selected columns and their respective rwos with data. This is the best type of report which can be utilized for the export purpose, when the data will only be used for representation purpose.

<img src="/assets/Tabular format.png">

2) Summary - This is the most commonly used report type. When you are looking for a report based on a "Group By" column, this is the report you will need. You can do grouping based on any available fields of the table.

<img src="/assets/Summary format.png">

3) Matrix - Matrix report type is somewhat similar to summary report. The only difference being that in summary report you can do the grouping based on the rows, whereas, in matrix report you can do the grouping based on both, columns and rows.

<img src="/assets/Matrix format.png">

To reach to the page for creating reports, follow these steps:

1) Click on "+" icon on the top row of the home page.
2) Search for "Reports"

<img src="/assets/+ sign (1).png">

3) Click on New to create a new report

<img src="/assets/New report.png">

4) Select the appropriate object for which you want to create a report and click on Create.

<img src="/assets/Select object.png">

###### References

* https://www.salesforceben.com/creating-reports-salesforce/
* https://www.appseconnect.com/create-reports-and-dashboards-in-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What are the 3 key differences between Data Loader & Data Import Wizard?
The key 3 differences between Data Loader & Data Import Wizard lies in their functionality.

<table cellpadding="3">
<tr>
<td align="center">
<b>Data Loader</b>
</td>
<td align="center">
<b>Data Import Wizard</b>
</td>
</tr>
<tr><td>With data loader you can do both import and export of data.</td><td>
With data import wizard, you can only import the data to your org. You will not be able to export data using this wizard.
</td></tr>
<tr><td>
With data loader, you first have to install the setup of data loader.
</td><td>
With data import wizard, it does not require any installation and is available as a step-by-step guided wizard.
</td></tr>
<tr><td>
With the help of data loader, you can import data of any object including both standard and custom objects.
</td><td>
In data import wizard, you are allowed to import data for all custom objects, but have access to limited standard objects including Account, Contacts, Leads, and Solutions.
</td></tr>
</table>

For doing data import through data import wizard, navigate to Setup > Administer > Data Management > Data Import Wizard

<img src="/assets/Data import wizard.png">

For doing data import through data loader, navigate to Setup > Administer > Data Management > Data Loader

<img src="/assets/Data loader.png">

Install the data loader setup and then you can do the import of data with ease.

###### References

* https://developer.salesforce.com/forums/?id=906F00000008m4MIAQ
* https://www.biswajeetsamal.com/blog/difference-between-data-loader-and-import-wizard-in-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What kind of report can be used in a Salesforce dashboard?
A salesforce dashboard supports all types of reports including Tabular, Summary, Matrix and even Joined. However, for creating a tabular report in the dashboard, you will have to put a row limit as all the rows cannot be shown the dashboard. Also, on the dashboard, you can have a maximum of 20 components for which you can analyze the data directly from the dashboard.

To reach to the page for creating a dashboard, follow these steps:
1) Click on "+" icon on the top row of the home page.
2) Search for "Dashboards"

<img src="/assets/Dashboards.png">

3) Click on "New Dashobard" to create a new dashboard

<img src="/assets/New dashboard.png">

4) Select the appropriate Components and Data Sources for creating a required dashboard.

<img src="/assets/Create dashboard.png">

###### References

* https://www.salesforceben.com/creating-reports-salesforce/
* https://www.appseconnect.com/create-reports-and-dashboards-in-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What are the key automation tools in Salesforce? How do you know when to use which?
Here are the key 4 automation tools in Salesforce:

1) Workflows - The most basic of the automation tools. It can: 1) create tasks 2) send email alerts 3) update fields 4) send outbound messages 5) create a flow trigger 6) select an existing action. Not visually appealing thou and easy to show to stakeholders.

2) Process Builder - Much more visually appealing because you can have a series of if/then statements. All it requires is an entry criteria along with the required action which will take place when the criteria is met. For example: An email alert should be sent to the manager if a customer writes a bad review on a case.

3) Lightning Flow - Good for complex client needs that cannot be met by worfklows or process builders. Ideal for scenarios where you need to guide a customer through a series of steps, i.e. client going through different screens to request a new credit card.

4) Approval Process - As the name suggests, this tool will automate those processes, where a user has to wait for approval from some other user in order to proceed further with the transaction. For example: When a salesman has to apply discount of 10% on a product, they have to wait for manager's approval. This is something which can be automated using approval processes.

In order to use these automation tools, navigate to Setup > Process Automation

<img src="/assets/Automation tools.png">

###### References

* https://help.salesforce.com/articleView?id=process_which_tool.htm&type=5
* https://www.appshark.com/tools-to-automate-business-processes-in-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What is a validation rule?
A validation rule ensures that data being entered into a field meets company's requirements. For example: A user can create a validation rule on "email id" field where if the user does not use a valid format "abc@xyz.com", the entry will not be accepted and the user will receive an error message. Validation rule can be applied only on fields of an object.

<img src="/assets/Validation rules.png">

Attached is the screenshot of an object "Accounts". Here we are creating a validation rule on the field "Phone". If the "Phone" field is blank, the user will get an error message stating that phone field is required.

###### References

* https://help.salesforce.com/articleView?id=fields_about_field_validation.htm&type=5
* https://www.salesforcetutorial.com/validation-rules-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What business problems do approval processes solve?
When a user has to get something approved by another user the approval process comes handy. For example: An employee submits their weekly timesheet and submits it to his manager for approval. This process can be easily automated by approval processes.

Doing all this manually will take up much time and will not be easy. With approval processes all the requests come in to the manager's queue for approval or denial.

###### References

* https://help.salesforce.com/articleView?id=process_which_tool.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### Which options do you have to make a field required?
There are four options available to the user to make a field required:

1) Validation Rule - Validation rules can be make a field required. Have you tried doing that? You should.

<img src="/assets/Validation rules.png">

2) Triggers - Triggers are a way of making a field required using command line. Here you can write your own apex code to make a field required rather than using any other methods involving UI elements.

<img src="/assets/Triggers.png">

3) Page Layout - While selecting fields for defining a page layout, a field can be marked as required. Please see the attached screenshot for reference.

<img src="/assets/Page Layout.png">

4) Field Definition - When creating a custom field, a user can mark the field as required.

<img src="/assets/Creating field.png">

###### References

* https://www.quora.com/What-are-the-different-ways-to-make-a-field-as-mandatory-in-salesforce

[[↑] Back to top](#salesforce-admin-questions)

### How do you restrict "Read" access to Opportunity object?
To restrict access to the Opportunity object remove the "Read" access that has been granted either by the Profile or the Permission Set . If it was the Profile then you need to navigate to Object Permissions and from there you can uncheck the "Read" access.

<img src="/assets/Restrict access.png">

###### References

* https://help.salesforce.com/articleView?id=bi_security_salesforce_object_field_levels_control_access.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### How do you give access to a certain object?
To give access to a certain object you can use either a profile or a permission set.

<img src="/assets/Grant access.png">

###### References

* https://help.salesforce.com/articleView?id=bi_security_salesforce_object_field_levels_control_access.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### I am looking at an Opportunity record. The record does not have a 'Share' button. Why?
If you dont' seesee the "Share" button on an opportunity record that means that the sharing settings on Opportunity Object are Public Read/Write. If that is the case yet you still don't see the Share button then you must be one of the following:

1) Record Owner
2) Any user with higher hierarchy role than the record owner
3) System Administrator

###### References

* https://www.proprofs.com/discuss/q/270157/1-who-can-select-the-sharing-button-account-and-opportunity-
* https://help.salesforce.com/articleView?id=faq_general_why_cant_i_see_the_sharing.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)
