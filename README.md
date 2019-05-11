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

## More stuff coming soon..
