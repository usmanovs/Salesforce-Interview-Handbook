# TRIGGER
1. Write a trigger that creates 5 Contact records for a new Account record
1. Can you insert a Contact record for a new Account record in a before insert context?
1. Create a trigger with before insert and after insert for Account object. System.debug a new Account record's ID.
1. What are 3 trigger best practices?
1. 


## TERMINOLOGY
1. what is refactoring?
1. 

## INTERESTING
1. Salesforce likes people to use static methods because it is 1 less line of code. Makes code simpler.
1. Why was it historically called "debugging"? 
1. Prepare a document outlining steps to debugging an error.
1. Developer Consoler is better for debugging.
1. syntax error vs runtime error
1. i liked the try catch error. x = 22, y = 0. try x/y. use specific exceptions in beginning and end with generic exception
1. 

## Review
1. How many records can a trigger process at one time?
1. What does it mean to "bulkify" a trigger?
1. What happens if a governor limit is exceeded?
1. What happens if you run the below code:

<pre><code>Account act = new Account ();
try {
  insert Accounts;
  }
catch (System.DMLException dmlx){
  system.debug('there was DML Exception '+ dmlx.getMessage());
}
</code></pre>


1. Create the below trigger & insert a case record

<pre><code>List<Case> childCases = new List<Case>();
for (Case parent : Trigger.new){
      Case child = new Case(ParentId = parent.Id, Subject = parent.Subject);
     childCases.add(child);}
insert childCases; 
</code></pre>




Good Reading:
1. [Developers: How to Overcome Imposter Syndrome](https://medium.com/learn-love-code/developers-how-to-overcome-imposter-syndrome-48edee803cf4)
1. [The Unicorn Project: A Novel about Developers, Digital Disruption, and Thriving in the Age of Data Kindle Edition](https://www.amazon.com/Unicorn-Project-Developers-Disruption-Thriving-ebook/dp/B07QT9QR41)
