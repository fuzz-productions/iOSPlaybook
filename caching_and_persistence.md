
# Caching and Persistence

### Definition

Caching is the temporary storage of data in-memory in order to enhance the user experience by removing or bypassing unnecessary service requests and instead fetching data from the local temporary storage.  This cache may or may not live through multiple app sessions.

Persistence is the more permanent storage of data on the device, usually through a database layer or file management system.  

### Context

The distinction between caching and persistence is important, because quite oftenly we find ourselves in situations where we, as developers, implement a large database in order to persist objects through sessions, when in the end, a more lightweight approach such as a temporary cache would be more appropriate. 

Data can come in many types and forms:

> Large format data.  (I.e., images, video, audio)
> Simple, mostly static data.  Sometimes data is mostly static, i.e., it only gets updated once in a blue moon, but it is important that the device can fetch this data from a server rather than rely upon hard coded values.  
> Dynamic data - Data that is constantly changing state on both device and server.  Often the most complicated data to work with.
> Relational data - Data that consists of objects with specific relationships (1 to 1, 1 to Many) with other objects in the data.

Whether you want to cache or persist the data is highly dependent upon exactly what kind of data you are receiving.  The following sections will hopefully provide a general guideline on how to make your decision. 

### Values 

* There should always be a strategy for syncing with the server, especially with highly dynamic databases
* Cleanup of caches should be handled completely
* Persistence is complex, and it should be implemented and managed thoughtfully.
* Persistence should only be done when absolutely necessary. 


Caching and persistance are complex and generally context specific. For this reason, we have created a checklist of questions (and general guidelines) that run through common considerations that one should take into account when implementing a cachingor persistence layer in an application. 

### Caching Checklist

1. Data
    - [ ] Large vs. Small
       > The larger the data coming down from the server, the longer requests will take. Generally when optimizing for speed, it make sense to cache large data to ensure that it is available quickly. 
    - [ ] Static vs. Dynamic
       > The more dynamic a piece of data is the more likley it is that you need a more robust database to store it. Images and videos are an examples of data that are static (and generally pretty large). They probably don't need a database, but it generally makes sense to hold onto them in a lightweight caching layer if they are used repeatedly. 
    - [ ] How does it releate to other data?
       > If objects in the data are relational, it makes sense to store them in a relational database in order to provide easier lookups between related objects.  However, at the point of use, you should consider whether or not you need to cache the retrieved object in its entirety, or whether holding onto the ID is sufficient. 
2. Application
    - [ ] How often do you access specific data?
       > The more often you access certain data, the more likely you will want to hold onto it in a cache
    - [ ] Do you filter large sets of data?
       > Filtering is a complicated task. The more you filter data, the more likely you will want to use a more robust database which optimizes for filtering. 
    - [ ] How well does data represent the UI of the Application?
       > There should be considerations as to what form the data is that you want to cache. Sometimes caching the object as-it-is when retrieved from the server is not necessary in the context of your application's UI layer.  
    - [ ] At what points do you need to sync with information on the server?
       > This is one of the most difficult issues with caching. Syncing local and remote datasets should be handled completely, and there should be a thoughtfully constructed flow for handling failures with syncing. 
3. Server
    - [ ] How does the server handle updating information?
       > Staying up to date (if that is something your applications' data must do) can be done in different ways. This should be considered and expressed within the application caching layer.  
       > If available, consult with the developer in charge of managing your API to see if they have any strategies in place (or can be built) to inform the clients when the remote database has been updated (or not!).

### Resources

1.  Database layers:
  - [Core Data](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/CoreData/index.html?utm_source=iosstash.io)
  - [Realm](https://realm.io/)
  - [Core Data Dandy](https://github.com/fuzz-productions/CoreDataDandy)

2.  File management systems (Writing JSON to file):
  - [eCall-SDK](https://gitlab.fuzzhq.com/ios-project/eCall-SDK/blob/dev/eCall-SDK/eCall-SDK/Utilities/DataStore.swift)

