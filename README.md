# Smart Building Project

* Project based on the seminar paper I wrote about a particular 'Smart Building' topic.
* The full version of the seminar paper is available in this repository. Unfortunately it is entirely written in Croatian,
but to make up for that, I will write this README that explains the core of the project in English


## Summary of the paper (and the project)

In this seminar paper I have given you a look at one of the projects that has the potential to be part of our everyday life in the near future. 
It is a project that would **automate and optimize heating management** in the building.  

In my implementation, I used the **model of a residential building**, but this model is very easy to use in many other situations that could prosper from something like this.
The **user-right management application for the heating management system** in the building consists of a few elements.  
We can not choose the most important or least important element, because it highly depends on our perspective.

The application contains a **repository of data** where it can efficiently record new data and retrieve previously written data.
The **user interface** of the application can be implemented in a variety of ways, and the optimum choice depends largely on the scale of our application.
To deploy the user interface, I used the **desktop application template**.   

The user interface does not perform any significant operations, but passes the specific requirements of the component that does this insted.  
This component is a **communication system** between the user (through the user interface) and the database, and ultimately, the application approval algorithm that is the last component in this application model.
When approving a request, **advantage is given to the recent demands given by people of higher priority**.   

Given the structure of the database, we can easily retrieve this data and determine in which relationship the priorities of a new request are currently in effect.
Obviously how wide a seemingly simple idea can come to light. After the basic definition of the idea, we quickly met the need for a more detailed definition and perhaps even redefining some of the project components, because this technology has a big difference in detail, both in implementation and in the use of technology.

## Basic components and structure of the application

The application must contain some kind of **data repository** in which it will be able to **write new data efficiently and retrieve previously recorded data**. For this purpose, I will use a database that is already internally optimized for these and many other operations.
The structure and logic of the database itself are explained in the next chapter.  

The next component that an application requires is a **user interface**. The user interface can be implemented in various ways, and the optimal selection depends largely on the extent to which our application goes through. To implement a user interface, I will use the **desktop application model**. The user interface in my model can be viewed as **a layer of abstraction between the user and the application itself**. It does not perform any significant operations, but it passes certain requirements of the components that do it for it.  

This component is a **system of communication** between the user (through the user interface) and the database, and ultimately, the **optimization algorithm** that is the last component in this application model.

## Creating the Application
### Database
I started the application making process by drawing a relational database sketch. The base is modeled so that each table in it represents an entity from the real world, and the tables are interrelated with certain relationships.  

  
![](/Visuals/Baza-podataka.jpg)  

Starting with the user in mind, I first built a table that approximates relevant user data in the context of this application.
Each user must have a unique identification number, which can not be selected by himself, but is selected by the database.  
In my implementation, the identification number is incremented for each user and is assigned to the order in which users are registered in the database.  

One of the data that a user can choose is a username, if it is not already occupied by another user. The user can also select their password, which will be used in conjunction with the user name when applying to the application. These three elements, though not the only data that the database will have about the user, are the only data that contains the **'user'** table.  
The reason why I decided to disclose user information to other tables is one-part object-oriented design, but also a certain level of security against interlinked data dependency.

The following table in the base is a table of **authority levels**. This table helps us expand this model of apps relatively easily to something larger that can be used from different perspectives of the user. It defines the levels of rights a user can own. Each level of rights is marked with its own identifier, level number, and short description.  

The level of rights of a particular user can be found in the following table, **'user-authority'**. It keeps the user identification numbers and the identification numbers of the rights level. By knowing the user's identification number, we can easily access the information that tells us about its level of rights.  

The following table in the model contains **building** data. Each building in the database contains its own identification number, location, number of floor counts, and (optional) identification number of the building owner. The reason for creating this table may not be clear within the project within just one building but it becomes very clear as soon as we step out of these frames. In a system with several buildings, it is very important that these buildings can be distinguished and have access to some basic information about them.  

The table that binds to this table is an abstraction of one **floor**. Each floor, as well as the remaining abstractions, has its own identifier, along with the building identifier and the number of floors it represents in that building.  

Very analogous to the 'user-authority' table, I made a **'user-floor'** table that contains the identification numbers of both of these abstractions.  

The last table in the base is a table of **requests**. It contains an identifier for each request, a user-table identifier, which can give us many data at once, and an additional description of the request. This is one example in which we clearly see why it is efficient to factorize elements in multiple tables.
