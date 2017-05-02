
# Caching and Persistence

### Values 
* Caching should only be done when absolutely necessary. 
* There should always be a strategy for syncing with the server
* Cleanup of caches should be handled completely
* Caching is complex, and it should be implemented and managed thoughtfully.

<details><summary>Caching Checklist</summary><p>

Caching is complex and generally context specific. For this reason, we have created a checklist of questions (and general guidelines) that run through common considerations that one should take into account when implementing a caching layer in an application. 

### Caching Checklist

1. Data
    - [ ] Large vs. Small
       > The larger the data coming down from the server, the longer requests will take. Generally when optimizing for speed, it make sense to cache large data to ensure that it is available quickly. 
    - [ ] Static vs. Dynamic
       > The more dynamic a piece of datum is the more likley it is that you need a more robust database to cache it. Images and videos are an examples of data that are static (and generally pretty large). They probably don't need a database, but it generally makes sense to hold onto them in a lightweight caching layer if they are used repeatedly. 
    - [ ] How does it releate to other data?
       > There should be considerations as to whether entire objects need to be cached. Sometimes just holding onto an id makes sense. 
2. Application
    - [ ] How often do you access specific data?
       > The more often you access certain data, the more likely you will want to hold onto it in a cache
    - [ ] Do you filter large sets of data?
       > Filtering is a complicated task. The more you filter data, the more likely you will want to use a more robust database which optimizes for filtering. 
    - [ ] How well does data represent the UI of the Application?
       > There should be considerations as to what form the data is that you want to cache. If an object coming back from a server is perfectly representative of what is displayed in the UI, 
    - [ ] At what points do you need to sync with information on the server?
       > This is one of the most difficult issues with caching. Syncing local and remote datasets should be handled completely, and there should be a thoughtfully constructed flow for handling failures with syncing. 
3. Server
    - [ ] How does the server handle updating information?
       > Staying up to date (if that is something your applications' data must do) can be done in different ways. This should be considered and expressed within the application caching layer. 
       
</p><details>
