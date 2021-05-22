# Espresso
![](img/31a.png)   
- espresso is an type of coffee
- in programing it's way of testing android applications
- it's an easy light weight and fast way.
- the code is easy and always open for optimization
- it's for develpers who are interest in automated testing.
- when you invoke `onView()`, Espresso waits to perform some UI action until  synchronization conditions happen:

    - The message queue is empty.
    - There are no instances of AsyncTask currently executing a task.
    - All developer-defined idling resources are idle.
- there is alot of espresso packages we learn about them in comming weak like `espresso-core` && `espresso-web` && `espresso-idling-resource` && `espresso-contrib` && `espresso-intents` && `espresso-remote`
![](img/31b.png)   
- steps to make an espresso test:
   - turn off automation in the test device
   - record the espresso test:   
      1. record UI interaction
      1. add Assertion to make sure the element are as expected
      1. save the record (at this poing the dependenu of espresso will added automatically) 
   - Run the test locally 