# Salesforce Develop Questions

Pull requests for suggestions and corrections are welcome!

Fundamentals
* [What are governor limits? Why are they important?](#what-are-governor-limits-why-are-they-important)
* [What are the Bulkification best practices?](#what-are-the-bulkification-best-practices)
* [What are the key automation tools in Salesforce? How do you know when to use which?](#what-are-the-key-automation-tools-in-Salesforce-how-do-you-know-when-to-use-which)
* [What is the difference between force.com and salesforce.com?](#what-is-the-difference-between-force.com-and-salesforce.com)

Sharing & Security
* [What are the different ways we can share a record?](#what-are-the-different-ways-we-can-share-a-record)
* [What are sharing settings? Why are they important?](#what-are-sharing-settings-why-are-they-important)
* [What is Apex Managed Sharing?](#what-is-apex-managed-sharing)
* [How many ways can we share a record?](#how-many-ways-can-we-share-a-record)


Behavioral
* [What are your 3 favourite Salesforce blogs?](#what-are-your-3-favourite-Salesforce-blogs)
* [Do you attend Salesforce developer community meetings?](#do-you-attend-Salesforce-developer-community-meetings)
* [What do you do when you are stuck when you code?](#what-do-you-do-when-you-are-stuck-when-you-code)
* [How many reputation points do you have on salesforce StackEchange?](#how-many-reputation-points-do-you-have-on-salesforce-stackExchange)
* [Would you say you are passionate about Salesforce? If so why?](#would-you-say-you-are-passionate-about-salesforce-if-so-why)
* [Have you ever contributed to Salesforce's Ideas? If you could make any idea come true, what would it be?](#have-you-ever-contributed-to-salesforce-s-ideas-if-you-could-make-any-idea-come-true-what-would-it-be)
* [Where do you see yourself in 3 years?](#where-do-you-see-yourself-in-3-years)
* [Do you enjoy being a Salesforce developer? Why?](#do-you-enjoy-being-a-salesforce-developer-why)

SOQL & DML
* [What are the default indexed fields in Salesforce?](#can-you-give-an-example-of-an-media-property-other-than-screen)
* [What is difference insert() and database .insert()?](#what-are-some-of-the-gotchas-for-writing-efficient-css)


Data Modelling & Data Management 
* [What Are The Types of SOQL Statements in SalesForce?](#are-you-familiar-with-styling-svg)
* [When one wants to pass the collection to the query instead of passing one value which keyword helps us?](#can-you-give-an-example-of-an-media-property-other-than-screen)
* [What is Future Annotation(@Future)?](#)
* [What is “Data Skew”?](#what-are-some-of)
* [Explain skinny table. What are the considerations for Skinny Table?](#what-are-some-of-the-gotchas-for)
* [Which fields are automatically Indexed in Salesforce?](#what-are-some-of-the)
* [Which fields are excluded from a custom index?](#what-are-some-of-the-gotchas-for-writi)
* [What is Future Annotation(@Future)?](#what-are-some-of-the-gotchas-for)

Logic & Process Automation 
* [What are the types of custom settings in Salesforce? What is the advantage of using custom settings?](#)
* [What are custom labels in Salesforce? What is the character limit of custom label?](#)
* [What are deterministic formula fields in Salesforce?](#)

Apex
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [Why do we use start test & stop test annotations?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [What are the best practices for writing test classes?](#)
* [Name 3 governor limits you know? Why are they important? How do you resolve when you see such errors?](#)
* [What are the different types of collections in Apex? What are maps in Apex?](#w)
* [What is the use of “@future” annotation?](#)
* [What are the different methods of batch Apex class?](#)
* [What is Trigger.new?](#)
* [What is the difference between SOQL and SOSL?](#what)
* [What is the difference between public and global class in Apex?](#wha)
* [What are the two options for when Apex Triggers can run?](#whats)
* [What is a use case for sharing rules?](#what-are-some-of-the)
* [Explain the use of an Outbound Message?](#what)
* [What is Trigger.new?](#what)
* [What is the Save Order of Execution? Why is it important?](#what)
* [What is a wrapper class? Give one use case where you would use a wrapper class.](#what)
* [Explain various methods of batch Apex class?](#what)
* [What is Apex Email Service?](#)
* [Describe the 3 qualities of Apex that make it powerful?](#)
* [What is Map Class in Apex Salesforce?](#)
* [What is Batch Apex in Salesforce?](#)
* [What is Apex Scheduler?](#)
* [What is the Apex Trigger in Salesforce?](#)
* [What is an Apex transactions?](#)
* [What are static resources?](#)
* [What is the difference between public and global classes in Apex?](#h)
* [Why use Batch Apex instead of Normal Apex?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)
* [What the difference between isNull and isBlank?](#have-you-ever-used-a-grid-system-and-if-so-what-do-you-prefer)



Debug & Deployment Tools
* [What are the different ways of deployment in Salesforce?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)
* [Why do we need to write test classes? How to identify if a class is a test class?](#)


Scenario Based Questions
* [ What does it indicate if an error state this “list has no rows for assignment”?](#)


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

[[↑] Back to top](#css-questions)

### What are the key automation tools in Salesforce? How do you know when to use which?

- In salesforce, Process builder , Workflow, Flow builder and approval process are some key tools for automation.
- All these tools have separate significance to perform various business processes in salesforce.
- When you have a requirement of processing multiple statements together, process builder or flow builder should be your choice.
- When you want some action to be performed automatically on basis of time, you should refrain from using approval process.
- If you want an activity to be done based on user action, Flow builder is an ideal choice.
- If calling an apex class is a necessity, Process builder can be used.
- For Sending outbound messages, workflows have been recommended.
 So based on the various needs various automation can be utilized. Please have a look at below table which describes the uses of each automation in a better way.
 
Factors									| Process builder			| Flow Builder	| Workflow				| Approval process		|
Visuals Supported						|	Yes						|	Yes			|	No					|	No					|
Processing complexity					|	Multiple if statements	| Very Complex	| Single if statements	| Single if statements	|
Starts when user clicks on button		|	No						|	Yes			|	No					|	Yes					|
Starts when platform event is received	|	Yes						|	No			|	No					|	No					|
Starts when record is changed			|	Yes						|	No			|	Yes					|	No					|
Time based actions supported			|	Yes						|	Yes			|	Yes					|	No					|
Invoke processes						|	Yes						|	No			|	No					|	No					|
User interaction supported				|	No						|	Yes			|	No					|	No					|
Call apex code							|	Yes						|	Yes			|	No					|	No					|
Delete records							|	No						|	Yes			|	No					|	No					|
Send email								|	Yes						|	Yes			|	Yes					|	Yes					|
Outbound messages support				|	No						|	No			|	Yes					|	Yes					|
Sending custom notifications			|	Yes						|	Yes			|	No					|	No					|
Update child records					|	Yes 					|	Yes			|	No					|	No					|

[[↑] Back to top](#css-questions)

### What are the different ways we can share a record?

We can share records using Roles, orgwidedefaults, Apex Sharing, Manual sharing and Sharing rules.

[[↑] Back to top](#css-questions)

### What are sharing settings? Why are they important?

- The whole concept of access control can be visualized as 3 gates before you reach the treasury box (Speaking in layman terms)
- Like you have to cross all the gates to reach the treasure, the same way you have to cross path with 3 levels of configuration to actually achieve a successful access control on data. You can consider the 3 gates as metadata accesses to achieve the access on actual data. These gates are object setting, field settings and sharing settings which relates to object, field and the record respectively. Once you have object and field level permissions, you can choose to have record level permissions using sharing settings.
- Sharing settings can be achieved through Orgwidedefaults, Sharing rules or Apex sharing.
- For understanding its importantance, lets take a scenario: A multinational company does their business in various regions. Director of Finland watches the business in Finland and Director of India watches it in India. If director of india starts to see the business done by company in Finland too with total figures of India then it will becomes cumbersome for him to do analysis for a specific region. Hence, allowing the respective directors to see data of their region only may lead to increased analysis and sales. This simple scenario can be achieved using OWDs and sharing rules.

[[↑] Back to top](#css-questions)

### What is Apex Managed Sharing?

Apex Sharing is a ability provided to force.com developers to explicitly fullfill the requirement of record sharing of an application or a product programatically. If you want to built an app which shares records based on some criteria due to an event occurance, then nothing other than apex sharing can help you.
For example, AccountShare is the sharing object for the Account object, ContactShare is the sharing object for the Contact object, MyCustomObject will be named as MyCustomObject__Share.

[[↑] Back to top](#css-questions)

### How many ways can we share a record?

We can share records in five different ways. We can share records using Roles, orgwidedefaults, Apex Sharing, Manual sharing and Sharing rules.

[[↑] Back to top](#css-questions)

### What are your 3 favourite Salesforce blogs?

`TextBook Definition:`
I mostly have been searching for technical and current affairs related blogs for salesforce all over.
- Technical blogs by Jeff Douglas are one of my favourites as they tend to detail things very preciously.
- Video logs by Salesforce Chef are also very favorable to me as the description of stuffs by him stays longer in my head due to the unique way of explanation.
- Blog by Salesforce itself in the form of weekly news article informs me about current salesforce practises and even raise my vocabulary to a huge extent.

`Street Definition:`
Although i read less blogs but some i have, to update myself.
- Whenever i am stuck somewhere technically, Technical blogs by Jeff Douglas are my first preference for answer. I read it only during technical challenges!
- As you know, Reading is boring. I watch videos by Salesforce Chef to gain deep understanding of the topic. Afterall Audio visual is interesting then reading.
- Further, if i dont know what salesforce have realeased, what peeks they reach, what was dreamforce all about this year etc then i am already outdated. Hence, i read salesforce blogs but they are sometimes too hard to understand but don't worry dictionary helps.

[[↑] Back to top](#css-questions)

### Do you attend Salesforce developer community meetings?

`TextBook Definition:`
Yes I do attend developer community meetings every single time. These meetings boosts myself in terms of knowledge gains and public relations. I have even got chance to speak in the community and share my knowledge. I have been rewarded with more than 10 rewards by community which motivates myself a lot.

`Street Definition:`
You know, Salesforce developer community meetings are my favourite. I make new friends every time. I learn and share in these meetings. Moreover, the food offered in the break is awesome. I am always excited for Q&A section where i had already grabbed tens of gifts and planning to pull more.

[[↑] Back to top](#css-questions)

### What do you do when you are stuck when you code?

`TextBook Definition:`
There are certain times when i get stuck while coding. In such case, I generally do some r&d on the internet crawling through many blogs and vlogs searching for solution. I try to find my doubts in developer forums or even post a question when no similiar question have been found. Once i find a solution, i apply it or in case no solution is available then i find a workaround. My first step generally is to google the exact error and know the root cause. Before moving to a workaround, i always consult a senior developer as experience is the key to solution.
Ex: I faced an error called "Mixed Dml exception" someday. I searched for the error on the internet for knowing the root cause. After reading few blogs, i came to know that it happens due to Dml of setup and non setup objects in the same transaction. Then i searched for the ways to separate that transaction. I found a clue Future methods. Then i searched for future methods and its syntax and embedded the solution.

`Street Definition:`
The first and foremost thing to fight to such a situation is not to loose faith in yourself. The best solution can be generated by you and you only. With that in mind, start googling the exact error or exception. Be brave, search for more blogs if the root cause is still hazy. There are leads or others developers to help you but you have to try to solve it on your own within a specified timeframe. If it's too much time consumed without even a clue, consult the lead immediately. You have already won the half way if you know the root cause. Because once you know the reason, you may have various way to solve it. Once sorted, say thanks to google and god!

[[↑] Back to top](#css-questions)

### How many reputation points do you have on salesforce StackExchange?

`TextBook Definition:`
On StackExchange i just have 100 points currently. Reputation points on Stackexchange came on to my priority list a bit late but yes it is there in my bucket. Moreover, i am targetting to reach 1000 points very soon in a month or so.

`Street Definition:`
I use stackexchange relatively very less. Whenever i am stuck technically, i search for solutions on it and apart from this i am very less active. But recently i have started answering the questions for which i am pretty sure and you won't believe it gives me immense pleasure to help the community and earn a label in return. I compete with friends nowadays and excel myself. I have 100 points now which will be 1000 soon.

[[↑] Back to top](#css-questions)

### Would you say you are passionate about Salesforce? If so why?

`TextBook Definition:`
I started working on salesforce due to a project requirement. The UI and funtionalities in salesforce attracted me towards it. When i came to know about solid functionality like sharing settings, I was absolutely amazed because when i compare it will other technologies or CRMs, it is really time consuming job to make such a funtionality whereas in salesforce you are getting it prebuilt. Hence it increased me interest. I started believing in salesforce when saw its thrice in a year upgrade process and most probably the dreamforce. Even writting code in apex and lightning are pretty straightforward and there are huge bunch of blogs and a wide community always ready to help. Finally it became my passion when i successfully deployed one project with full support from salesforce partners, salesforce community and the salesforce case support. Moreover, it also provided cetified developers and admins, hence finally with passion i selected it as my career.

`Street Definition:`
Frankly speaking, i came into salesforce due to high market demand and less developers available. Obviously a good pay was my first reason, but when i started exploring this CRM in depth i had no clue what i was looking it. At first it looked really difficult, so mamy thing so many functionality at one place but once i got a command using trailhead and the blogs, i was unstoppable. Sharing settings, profile and users, all other setup stuffs were mind bending initially but i grasped them and now i feel that there can be no better CRM to do this. Writting code in salesforce seems very much easy to me then any other technologies due to the really good supportive development environment. I started loving salesforce when i realized i am growing day by day in terms of knowledge, market upgradation, working with better clients and infrastructure and finally in payscale. Even such rapid growth of salesforce motivated me to stay connected to the community and love what you do. Hence salesforce became my passion and career both.

[[↑] Back to top](#css-questions)

### Have you ever contributed to Salesforce's Ideas? If you could make any idea come true, what would it be?

`TextBook Definition:`
Yes, i always wished the Lookup rollup functionality should be a part of salesforce itself due to the daily demands. I hope salesforce may find it useful. By the way, we can't add rollup summary fields on lookup relationship and i wished if that is possible too with restrictions.

`Street Definition:`
I have already contribited the idea of Lookup rollup and asked the community to vote it. Tht thing is - in the intial stage of the project you sometimes are not sure what relation should be taken up, consider you choose lookup at that time, further at the later part of the project you got a functionlity to count child records and that becomes a mess at that time. You may have to write custom code for that. I believe that should already be there and recommend salesforce to add it. But again they are the better judge.

[[↑] Back to top](#css-questions)

### Where do you see yourself in 3 years?

`TextBook Definition:`
Currently i am a developer with good coding and learning skills but i know that not enough. I have to rise to a technical lead position next coming years and despite of coding, i have to focus on becoming a good observer, orator, multi-tasker and a quick issue discoverer. With all these, new platform changes should also be grasped. I also have to serve the company by becoming their crucial asset earning handful of appreciations for myself. So in conclusion i want to be an expert of this domain, lead the projects and take the managerial responsibilities.

`Street Definition:`
In next 3 years, i want to learn every aspect of salesforce development. Either it is lightning components or lightning web components, i want to be fully expert on them with a live project hands on. I am looking for a designation step up with full confidence in handling a project smoothly. I have already handled modules in the past and i feel i am ready for the whole project itself. Although, every four month salesforce produces something new, it would also make myself a better developer day by day. Further, buying a car, marriage etc are also the part of my life in next 3 years. Yah, One thing i forgot is the World tour, hope to save much to complete a world tour soon.

[[↑] Back to top](#css-questions)

### Do you enjoy being a Salesforce developer? Why?

`TextBook Definition:`
First things, you are working with a world dominating technology and you should be happy about it. This is an innovative platform which does innovations and ask you to be part of them. You may always find some traning guides and issue resolution steps somewhere. Readily available code repositories, appexchange products and function librabaries are always available to skip to start from scratch. The compiler and interpreter of the apex engine are seriously appreciated which helps you rectify your code in minutes. Further, the community trains and certify you also. So all in all salesforce development is the one i love.

`Street Definition:`
I am glad being one. Being salesforce developer is really an exciting job. It is for the people who seek adventure and never wish to settle down. The new generation is of that kind which wants to keep learning daily and salesforce is always ready to teach you. It keeps on upgrading the technology as per modern needs and forces its community to learn to catch up the market. It shows trust on you by certifying you and ensuring the community that he is worth it. You learn from trailhead, you apply it in real time, you search in community to help and you deliver it. There is no way you will be stuck, someone will always be there to help you. That's why i like being a exciting salesforce developer.

[[↑] Back to top](#css-questions)


### What are governor limits? Why are they important?

Governor limits are runtime limits enforced by the Apex runtime engine to ensure that code does not monopolizes the resources which have been shared by various customers and organizations. These limits ensure the efficient processing of resources on the Force.com multitenant platform.


[[↑] Back to top](#css-questions)

### What is the difference between force.com and salesforce.com?

- Salesforce.com is SAAS and force.com is PAAS.
- All the prebuilt products like sales or service, leads, reports, tabs etc are a part of salesforce.com and the possible customization products like visualforce page, classes, triggers, components etc are a part of force.com.
- Licenses for salesforce.com are pretty expensive than force.com's license.
- Salesforce.com is a leading CRM which have been built for targetting customers and social objectives whereas force.com helps delivering world class customized apps within short period of time.
- Salesforce.com focuses more on prebuilt functionality to complete stuffs by points and clicks whereas force.com uses programming or markup languages to build a product or output which is not offered as a part of salesforce CRM.
- Salesforce.com is a product built on the top of force.com platform.

[[↑] Back to top](#css-questions)

### What are the advantages/disadvantages of using CSS preprocessors?

**Advantages:**

* CSS is made more maintainable.
* Easy to write nested selectors.
* Variables for consistent theming. Can share theme files across different projects.
* Mixins to generate repeated CSS.
* Sass features like loops, lists, and maps can make configuration easier and less verbose.
* Splitting your code into multiple files. CSS files can be split up too but doing so will require an HTTP request to download each CSS file.

**Disadvantages:**

* Requires tools for preprocessing. Re-compilation time can be slow.
* Not writing currently and potentially usable CSS. For example, by using something like [postcss-loader](https://github.com/postcss/postcss-loader) with [webpack](https://webpack.js.org/), you can write potentially future-compatible CSS, allowing you to use things like CSS variables instead of Sass variables. Thus, you're learning new skills that could pay off if/when they become standardized.

[[↑] Back to top](#css-questions)

### Describe what you like and dislike about the CSS preprocessors you have used.

**Likes:**

* Mostly the advantages mentioned above.
* Less is written in JavaScript, which plays well with Node.

**Dislikes:**

* I use Sass via `node-sass`, which is a binding for LibSass written in C++. I have to frequently recompile it when switching between node versions.
* In Less, variable names are prefixed with `@`, which can be confused with native CSS keywords like `@media`, `@import` and `@font-face` rule.

[[↑] Back to top](#css-questions)

### How would you implement a web design comp that uses non-standard fonts?

Use `@font-face` and define `font-family` for different `font-weight`s.

[[↑] Back to top](#css-questions)

### Explain how a browser determines what elements match a CSS selector.

This part is related to the above about [writing efficient CSS](#what-are-some-of-the-gotchas-for-writing-efficient-css). Browsers match selectors from rightmost (key selector) to left. Browsers filter out elements in the DOM according to the key selector and traverse up its parent elements to determine matches. The shorter the length of the selector chain, the faster the browser can determine if that element matches the selector.

For example with this selector `p span`, browsers firstly find all the `<span>` elements and traverse up its parent all the way up to the root to find the `<p>` element. For a particular `<span>`, as soon as it finds a `<p>`, it knows that the `<span>` matches and can stop its matching.

###### References

* https://stackoverflow.com/questions/5797014/why-do-browsers-match-css-selectors-from-right-to-left

[[↑] Back to top](#css-questions)

### Describe pseudo-elements and discuss what they are used for.

A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s). They can be used for decoration (`:first-line`, `:first-letter`) or adding elements to the markup (combined with `content: ...`) without having to modify the markup (`:before`, `:after`).

* `:first-line` and `:first-letter` can be used to decorate text.
* Used in the `.clearfix` hack as shown above to add a zero-space element with `clear: both`.
* Triangular arrows in tooltips use `:before` and `:after`. Encourages separation of concerns because the triangle is considered part of styling and not really the DOM. It's not really possible to draw a triangle with just CSS styles without using an additional HTML element.

###### References

* https://css-tricks.com/almanac/selectors/a/after-and-before/

[[↑] Back to top](#css-questions)

### Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.

The CSS box model describes the rectangular boxes that are generated for elements in the document tree and laid out according to the visual formatting model. Each box has a content area (e.g. text, an image, etc.) and optional surrounding `padding`, `border`, and `margin` areas.

The CSS box model is responsible for calculating:

* How much space a block element takes up.
* Whether or not borders and/or margins overlap, or collapse.
* A box's dimensions.

The box model has the following rules:

* The dimensions of a block element are calculated by `width`, `height`, `padding`, `border`s, and `margin`s.
* If no `height` is specified, a block element will be as high as the content it contains, plus `padding` (unless there are floats, for which see below).
* If no `width` is specified, a non-floated block element will expand to fit the width of its parent minus `padding`.
* The `height` of an element is calculated by the content's `height`.
* The `width` of an element is calculated by the content's `width`.
* By default, `padding`s and `border`s are not part of the `width` and `height` of an element.

###### References

* https://www.smashingmagazine.com/2010/06/the-principles-of-cross-browser-css-coding/#understand-the-css-box-model

[[↑] Back to top](#css-questions)

### What does `* { box-sizing: border-box; }` do? What are its advantages?

* By default, elements have `box-sizing: content-box` applied, and only the content size is being accounted for.
* `box-sizing: border-box` changes how the `width` and `height` of elements are being calculated, `border` and `padding` are also being included in the calculation.
* The `height` of an element is now calculated by the content's `height` + vertical `padding` + vertical `border` width.
* The `width` of an element is now calculated by the content's `width` + horizontal `padding` + horizontal `border` width.
* Taking into account `padding`s and `border`s as part of our box model resonates better with how designers actually imagine content in grids.

###### References

* https://www.paulirish.com/2012/box-sizing-border-box-ftw/

[[↑] Back to top](#css-questions)

### What is the CSS `display` property and can you give a few examples of its use?

* `none`, `block`, `inline`, `inline-block`, `table`, `table-row`, `table-cell`, `list-item`.

TODO

[[↑] Back to top](#css-questions)

### What's the difference between `inline` and `inline-block`?

I shall throw in a comparison with `block` for good measure.

|                                      | `block`                                                                                     | `inline-block`                                                      | `inline`                                                                                                                                                                                                             |
| ------------------------------------ | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Size                                 | Fills up the width of its parent container.                                                 | Depends on content.                                                 | Depends on content.                                                                                                                                                                                                  |
| Positioning                          | Start on a new line and tolerates no HTML elements next to it (except when you add `float`) | Flows along with other content and allows other elements beside it. | Flows along with other content and allows other elements beside it.                                                                                                                                                  |
| Can specify `width` and `height`     | Yes                                                                                         | Yes                                                                 | No. Will ignore if being set.                                                                                                                                                                                        |
| Can be aligned with `vertical-align` | No                                                                                          | Yes                                                                 | Yes                                                                                                                                                                                                                  |
| Margins and paddings                 | All sides respected.                                                                        | All sides respected.                                                | Only horizontal sides respected. Vertical sides, if specified, do not affect layout. Vertical space it takes up depends on `line-height`, even though the `border` and `padding` appear visually around the content. |
| Float                                | -                                                                                           | -                                                                   | Becomes like a `block` element where you can set vertical margins and paddings.                                                                                                                                      |

[[↑] Back to top](#css-questions)

### What's the difference between a `relative`, `fixed`, `absolute` and `static`ally positioned element?

A positioned element is an element whose computed `position` property is either `relative`, `absolute`, `fixed` or `sticky`.

* `static` - The default position; the element will flow into the page as it normally would. The `top`, `right`, `bottom`, `left` and `z-index` properties do not apply.
* `relative` - The element's position is adjusted relative to itself, without changing layout (and thus leaving a gap for the element where it would have been had it not been positioned).
* `absolute` - The element is removed from the flow of the page and positioned at a specified position relative to its closest positioned ancestor if any, or otherwise relative to the initial containing block. Absolutely positioned boxes can have margins, and they do not collapse with any other margins. These elements do not affect the position of other elements.
* `fixed` - The element is removed from the flow of the page and positioned at a specified position relative to the viewport and doesn't move when scrolled.
* `sticky` - Sticky positioning is a hybrid of relative and fixed positioning. The element is treated as `relative` positioned until it crosses a specified threshold, at which point it is treated as `fixed` positioned.

###### References

* https://developer.mozilla.org/en/docs/Web/CSS/position

[[↑] Back to top](#css-questions)

### What existing CSS frameworks have you used locally, or in production? How would you change/improve them?

* **Bootstrap** - Slow release cycle. Bootstrap 4 has been in alpha for almost 2 years. Add a spinner button component, as it is widely used.
* **Semantic UI** - Source code structure makes theme customization extremely hard to understand. Its unconventional theming system is a pain to customize. Hardcoded config path within the vendor library. Not well-designed for overriding variables unlike in Bootstrap.
* **Bulma** - A lot of non-semantic and superfluous classes and markup required. Not backward compatible. Upgrading versions breaks the app in subtle manners.

[[↑] Back to top](#css-questions)

### Have you played around with the new CSS Flexbox or Grid specs?

Yes. Flexbox is mainly meant for 1-dimensional layouts while Grid is meant for 2-dimensional layouts.

Flexbox solves many common problems in CSS, such as vertical centering of elements within a container, sticky footer, etc. Bootstrap and Bulma are based on Flexbox, and it is probably the recommended way to create layouts these days. Have tried Flexbox before but ran into some browser incompatibility issues (Safari) in using `flex-grow`, and I had to rewrite my code using `inline-blocks` and math to calculate the widths in percentages, it wasn't a nice experience.

Grid is by far the most intuitive approach for creating grid-based layouts (it better be!) but browser support is not wide at the moment.

###### References

* https://philipwalton.github.io/solved-by-flexbox/

[[↑] Back to top](#css-questions)

### Can you explain the difference between coding a website to be responsive versus using a mobile-first strategy?

Note that these two 2 approaches are not exclusive.

Making a website responsive means the some elements will respond by adapting its size or other functionality according to the device's screen size, typically the viewport width, through CSS media queries, for example, making the font size smaller on smaller devices.

```css
@media (min-width: 601px) {
  .my-class {
    font-size: 24px;
  }
}
@media (max-width: 600px) {
  .my-class {
    font-size: 12px;
  }
}
```

A mobile-first strategy is also responsive, however it agrees we should default and define all the styles for mobile devices, and only add specific responsive rules to other devices later. Following the previous example:

```css
.my-class {
  font-size: 12px;
}

@media (min-width: 600px) {
  .my-class {
    font-size: 24px;
  }
}
```

A mobile-first strategy has 2 main advantages:

* It's more performant on mobile devices, since all the rules applied for them don't have to be validated against any media queries.
* It forces to write cleaner code in respect to responsive CSS rules.

[[↑] Back to top](#css-questions)

### How is responsive design different from adaptive design?

Both responsive and adaptive design attempt to optimize the user experience across different devices, adjusting for different viewport sizes, resolutions, usage contexts, control mechanisms, and so on.

Responsive design works on the principle of flexibility - a single fluid website that can look good on any device. Responsive websites use media queries, flexible grids, and responsive images to create a user experience that flexes and changes based on a multitude of factors. Like a single ball growing or shrinking to fit through several different hoops.

Adaptive design is more like the modern definition of progressive enhancement. Instead of one flexible design, adaptive design detects the device and other features and then provides the appropriate feature and layout based on a predefined set of viewport sizes and other characteristics. The site detects the type of device used and delivers the pre-set layout for that device. Instead of a single ball going through several different-sized hoops, you'd have several different balls to use depending on the hoop size.

Both have these methods have some issues that need to be weighed:

* Responsive design can be quite challenging, as you're essentially using a single albeit responsive layout to fit all situations. How to set the media query breakpoints is one such challenge. Do you use standardized breakpoint values? Or, do you use breakpoints that make sense to your particular layout? What if that layout changes?
* Adaptive design generally requires user agent sniffing, or DPI detection, etc., all of which can prove unreliable.

###### References

* https://developer.mozilla.org/en-US/docs/Archive/Apps/Design/UI_layout_basics/Responsive_design_versus_adaptive_design
* http://mediumwell.com/responsive-adaptive-mobile/
* https://css-tricks.com/the-difference-between-responsive-and-adaptive-design/

[[↑] Back to top](#css-questions)

### Have you ever worked with retina graphics? If so, when and what techniques did you use?

_Retina_ is just a marketing term to refer to high resolution screens with a pixel ratio bigger than 1. The key thing to know is that using a pixel ratio means these displays are emulating a lower resolution screen in order to show elements with the same size. Nowadays we consider all mobile devices _retina_ defacto displays.

Browsers by default render DOM elements according to the device resolution, except for images.

In order to have crisp, good-looking graphics that make the best of retina displays we need to use high resolution images whenever possible. However using always the highest resolution images will have an impact on performance as more bytes will need to be sent over the wire.

To overcome this problem, we can use responsive images, as specified in HTML5. It requires making available different resolution files of the same image to the browser and let it decide which image is best, using the html attribute `srcset` and optionally `sizes`, for instance:

```html
<div responsive-background-image>
  <img src="/images/test-1600.jpg"
    sizes="
      (min-width: 768px) 50vw,
      (min-width: 1024px) 66vw,
      100vw"
    srcset="
      /images/test-400.jpg 400w,
      /images/test-800.jpg 800w,
      /images/test-1200.jpg 1200w">
</div>
```

It is important to note that browsers which don't support HTML5's `srcset` (i.e. IE11) will ignore it and use `src` instead. If we really need to support IE11 and we want to provide this feature for performance reasons, we can use a JavaScript polyfill, e.g. Picturefill (link in the references).

For icons, I would also opt to use SVGs and icon fonts where possible, as they render very crisply regardless of resolution.

###### References

* https://css-tricks.com/responsive-images-youre-just-changing-resolutions-use-srcset/
* http://scottjehl.github.io/picturefill/
* https://aclaes.com/responsive-background-images-with-srcset-and-sizes/

[[↑] Back to top](#css-questions)

### Is there any reason you'd want to use `translate()` instead of `absolute` positioning, or vice-versa? And why?

`translate()` is a value of CSS `transform`. Changing `transform` or `opacity` does not trigger browser reflow or repaint but does trigger compositions; whereas changing the absolute positioning triggers `reflow`. `transform` causes the browser to create a GPU layer for the element but changing absolute positioning properties uses the CPU. Hence `translate()` is more efficient and will result in shorter paint times for smoother animations.

When using `translate()`, the element still occupies its original space (sort of like `position: relative`), unlike in changing the absolute positioning.

###### References

* https://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/

[[↑] Back to top](#css-questions)

### Other Answers

* https://neal.codes/blog/front-end-interview-css-questions
* https://quizlet.com/28293152/front-end-interview-questions-css-flash-cards/
* http://peterdoes.it/2015/12/03/a-personal-exercise-front-end-job-interview-questions-and-my-answers-all/
