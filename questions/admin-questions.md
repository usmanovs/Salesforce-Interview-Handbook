## Salesforce Admin Questions

Pull requests for suggestions and corrections are welcome!

## Salesforce Fundamentals
* [How can we find out what licenses the org has? And how many licenses are available?](#how-can-we-find-out-what-licenses-the-org-has-and-how-many-licenses-are-available)
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
* [What is the difference between a lookup relationship & master:detail relationship?](#how-would-you-approach-fixing-browser-specific-styling-issues)
* [What is an External lookup?](#what-are-the-different-ways-to-visually-hide-content-and-make-it-available-only-for-screen-readers)
* [Why do we create relationships between objects?](#explain-css-sprites-and-how-you-would-implement-them-on-a-page-or-site)
* [What is a self-relationship?](#how-do-you-serve-your-pages-for-feature-constrained-browsers-what-techniquesprocesses-do-you-use)
* [What is a junction object? What do we use them for?](#are-you-familiar-with-styling-svg)
* [What happens if you delete a field?](#have-you-used-or-implemented-media-queries-or-mobile-specific-layoutscss)
* [What can you do with a schema builder?](#have-you-used-or-implemented-media-queries-or-mobile-specific-layoutscss)
* [What is a junction object? What do we use them for?](#are-you-familiar-with-styling-svg)

## Sales, Service, Analytics, Data Management
* [What is a price book?](#are-you-familiar-with-styling-svg)
* [When you convert a Lead what does it become?](#are-you-familiar-with-styling-svg)
* [What is a case?](#are-you-familiar-with-styling-svg)
* [What are the key 3 report types available in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the 3 key differences between Data Loader & Data Import Wizard?](#are-you-familiar-with-styling-svg)

## Automation
* [What are the key automation tools in Salesforce? How do you know when to use which?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What is a validation rule?](#what-are-some-of-the-gotchas-for-writing-efficient-css)


## Scenario Based Questions
* [How do you restrict access to a certain object?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [How do you give access to a certain object?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [I am looking at an Opportunity record. The record does not have a 'Share' button. Why?](#what-are-some-of-the-gotchas-for-writing-efficient-css)
* [What are the key automation tools in Salesforce?](#what-are-some-of-the-gotchas-for-writing-efficient-css)


### How can we find out what licenses the org has? And how many licenses are available?
A license in salesforce enables a user to use the features of the org. A user can also be restricted to using only a few features of the org, based on the user assigned license. In order to view what all licenses are available for the org, the user has to follow these steps:

- Select Setup from the admin drop down

<img src="/assets/Setup.png">

- From the left sidebar select Administration/Administer/Administration Setup > Company Profile > Company Information

<img src="/assets/Company profile drop down.png">

OR
- On the left sidebar, navigate to the search bar and type “company information” and click on “Company Information” as shown in the image

<img src="/assets/search bar.png">

- Navigate to “User Licenses” section

Here you will be able to see all the available licenses for the org. In this section, you will be able to see all the details related to licenses as to their status, total number of licenses, number of used licenses along with the remaining number of licenses and the expiration date of the licenses.

<img src="/assets/available licenses.png">

###### References

* https://help.salesforce.com/articleView?id=users_understanding_license_types.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### What is a sandbox org? What are the different types of sandboxes in Salesforce?
Sandbox org is basically a replica of the production org which can be used for various purposes including, but not limited to, development and testing. This is done in order to make the required changes in your production org, but without actually working on the production org. All the changes made in sandbox org does not affect your production org directly. These orgs are very useful in fixing bugs which can only be reproduced in the production environment. However, one can define as to what kind of copy needs to be created for the required purpose and the user has four options to select from:

1) Developer Sandbox
2) Developer Pro Sandbox
3) Partial Sandbox
4) Full Sandbox

In order to create a sandbox, the user can navigate to Setup > Data Management > Sandboxes and the user will see following page:

<img src="/assets/sandbox.png">

Here the user can view as to what all sandbox licenses does an org have and how many are still available to be created. From the “New Sandbox” button, the user can create a new sandbox org.

For a detailed difference between the four types of sandbox orgs, please refer to the following image:

<img src="/assets/types of sandboxes.png">

###### References

* https://www.salesforcetutorial.com/introduction-to-sandboxes/

[[↑] Back to top](#salesforce-admin-questions)

### What useful information can you find on the company information page?
The company information page provides all the necessary details about the org. For steps on how to reach the company information page, please refer to the first question. Beginning from the org name to the Org Id, this is the page where you will get all the required details of the org. This page also provides various sections which includes User Licenses, Permission Set Licenses, Feature Licenses and Usage-based Entitlements. But, as far as useful information is concerned, let us take a look at some of the key information one can extract from this page:

1) Default Locale of the org
2) Default Time Zone of the org which will be assigned to all the users, by default, created under this org
3) Used Data Space (in MBs)
4) Used File Space (in MBs)
5) Salesforce.com Organization ID
6) Organization Edition
7) API requests made in last 24 hours and the available limit of the allowed requests
8) Instance, the server name which will appear in the url of the org, when logged in

These are some necessary information which one can find on the company information page, however, there are various other fields which are available to the user, for which you can refer to the following screenshot:

<img src="/assets/organization information.png">

###### References

* https://help.salesforce.com/articleView?id=users_understanding_license_types.htm&type=5

[[↑] Back to top](#salesforce-admin-questions)

### What is a profile?
A profile in salesforce is a combination of various settings and permissions which enables the user to perform certain tasks in salesforce. This is where you can define as to what all things a user can do in the respective org. With a single profile, one can control various permissions including, but not limited to, Tab Settings, Administrative Permissions, General User Permissions, Standard Object Permissions, Password Policies etc. In order to view all the profiles of the org, you can navigate to Setup > Administration > Users > Profiles.

<img src="/assets/View profile.png">

From the same screen, the system administrator can create a new profile from "New Profile" button as shown in the above screenshot. A profile can have multiple users but a user can have only one profile in the org. There are two types of profiles in the salesforce:

1) Standard Profiles - Standard profiles are the default profiles provided by the salesforce, even for the free license. These profiles cannot be deleted by anyone and they are generally six (6) in number:

 - System Administrator
 - Standard User
 - Solution Manager
 - Read Only
 - Marketing User
 - Contract Manager

2) Custom Profiles - These are the profiles provided by the user and can be deleted if required. Custom profiles have "Custom" column checked for them on the view profile screen.

###### References

* https://www.salesforcetutorial.com/working-profiles-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What is the difference between a profile & permission set?
As mentioned above for the profile, it is a collection of certain permissions, and similar is the case with permission set. As the name suggests, permission set also consist of various permissions, however, it is an extension to the already assigned permissions to the user via profile. To outline the difference between the two, we can understand that profile provides some basic permissions to the user, whereas, in order to provide some additional permissions to the user one can define permission set.

One more difference between a profile and permission set is that a profile can be used to grant or revoke a permission to the user, but a permission set can only grant or extend the permission. One cannot remove a permission with the help of a permission set.

Another difference between the two is that only one profile can be assigned to the user but a user can have number of permission sets extending their allowed permissions.

For viewing all the permission sets of the org, you can navigate to Setup > Administration > Users > Permission Sets.

<img src="/assets/View permission sets.png">

###### References

* https://www.salesforcetutorial.com/working-profiles-salesforce/

[[↑] Back to top](#salesforce-admin-questions)

### What is the difference between role & profile?
A role in salesforce is basically defining a role of the user in the organization. This helps in understanding and defining the level of permission being provided to the user. It works in hierarchy and by default all the users with superior roles can view and edit the records created by their subordinates. This can be changed by unchecking the checkbox under the column "Grant Access Using Hierarchies" under Sharing Settings.

When looking at the difference between role and profile, one can clearly understand the difference between them just by one simple statement. What a user will see will be defined by its role, however, what all the user can do with the record will be defined by the profile of the user. Another major difference between them is that defining profile is mandatory, whereas, defining role is not mandatory.

For viewing and defining the roles, you can navigate to Setup > Administration > Users > Roles.

<img src="/assets/View roles.png">

###### References

* https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/admin_roles.htm#!
* https://developer.salesforce.com/forums/?id=9060G000000UUa0QAG

[[↑] Back to top](#salesforce-admin-questions)

### What are sharing settings?
The sharing settings allows access to data of each user based on their role.
Different levels of sharing available in the salesforce are:

1) Private - Only the creator of the record will have access to the record
2) Public Read only - The record will be available for public access but the users will only be able to view it and cannot do any editing
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
