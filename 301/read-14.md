# Database normalization

Database normalization is a process used to organize a database into tables and columns. The main idea with this is that a table should be about a specific topic and only supporting topics included. Take a spreadsheet containing the information as an example, where the data contains salespeople and customers serving several purposes:


To achieve these objectives, we’ll use some established rules. As you apply these rules, new tables are formed. The progression from unruly to optimized passes through several normal forms.
There are three normal forms most databases adhere to using. As tables satisfy each successive database normalization form, they become less prone to database modification anomalies and more focused toward a sole purpose or topic. Before we move on be sure you understand the definition of a database table.

# Reasons for Database Normalization
There are three main reasons to normalize a database. The first is to minimize duplicate data, the second is to minimize or avoid data modification issues, and the third is to simplify queries.


The first thing to notice is this table serves many purposes including:
Identifying the organization’s salespeople
Listing the sales offices and phone numbers
Associating a salesperson with an sales office
Showing each salesperson’s customers
As a DBA this raises a red flag. In general I like to see tables that have one purpose. Having the table serve many purposes introduces many of the challenges; namely, data duplication, data update issues, and increased effort to query data.


## Data Duplication and Modification Anomalies

Notice that for each SalesPerson we have listed both the SalesOffice and OfficeNumber. There are duplicate salesperson data. Duplicated information presents two problems:
It increases storage and decrease performance.
It becomes more difficult to maintain data changes

The forms are progressive, meaning that to qualify for 3rd normal form a table must first satisfy the rules for 2nd normal form, and 2nd normal form must adhere to those for 1st normal form. Before we discuss the various forms and rules in detail, let’s summarize the various forms:
First Normal Form – The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.
Second Normal Form – The table is in first normal form and all the columns depend on the table’s primary key.
Third Normal Form – the table is in second normal form and all of its columns are not transitively dependent on the primary key
If the rules don’t make too much sense, don’t worry. I’ve linked to article to help you understand them.
For now it’s important to understand there are three rules for database normalization that upon each other. Some people make database normalization seem complicated.

![1](https://files.slack.com/files-pri/TNGRRLUMA-F021LCUBUSC/image.png)


Deletion Anomaly
Deletion of a row causes removal of more than one set of facts. For instance, if John Hunt retires, then deleting that row cause us to lose information about the New York office.

![2](https://files.slack.com/files-pri/TNGRRLUMA-F0212PGJNBW/image.png)

## Search and Sort Issues

The last reason we’ll consider is making it easier to search and sort your data. In the SalesStaff table if you want to search for a specific customer such as Ford, you would have to write a query like
Clearly if the customer were somehow in one column our query would be simpler. Also, consider if you want to run a query and sort by customer.
Our current table makes this tough. You would have to use three separate UNION queries! You can eliminate or reduce these anomalies by separating the data into different tables. This puts the data into tables serving a single purpose.
The process to redesign the table is database normalization.