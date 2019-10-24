## Salesforce Admin Questions

Pull requests for suggestions and corrections are welcome!

## Salesforce Fundamentals
* [How can we find out what licenses the org has? And how many licenses are available?](#how-can-we-find-out-what-licenses-the-org-has-and-how-many-licenses-are-available)
* [What is a sandbox org? What are the different types of sandboxes in Salesforce?](#What-is-a-sandbox-org?-What-are-the-different-types-of-sandboxes-in-Salesforce?)
* [What useful information can you find on the company information page?](#What-useful-information-can-you-find-on-the-company-information-page?)

## Security & Access
* [What is a profile](#describe-z-index-and-how-stacking-context-is-formed)
* [What is the difference between a profile & permission set?](#describe-block-formatting-context-bfc-and-how-it-works)
* [What is the difference between role & profile?](#what-are-the-various-clearing-techniques-and-which-is-appropriate-for-what-context)
* [What are sharing settings?](#describe-z-index-and-how-stacking-context-is-formed)
* [What’s the difference between Record Types & Page Layouts? What is the use of each?](#what-is-css-selector-specificity-and-how-does-it-work)
* [Can you delete a user? Why not?](#what-is-css-selector-specificity-and-how-does-it-work)
* [What are Audit Fields?](#whats-the-difference-between-resetting-and-normalizing-css-which-would-you-choose-and-why)

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