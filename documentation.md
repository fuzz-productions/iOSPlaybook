
# Documentation 

### Values
Documentation is imperative. Given that we are an agency, our code is consumed by many developers inside and outside of Fuzz. Documentation should be updated and written in a manner that considers what a new programmer on the project would consider useful. 

You may still need [persuasion.](http://ericasadun.com/2016/11/03/swift-holy-war-comments-are-not-an-anti-pattern/)

--- 

### Context

There are two types of documentation, which we describe as 'What' and 'Why'. 

> What - explains what a piece of code does
>
> Why - explains why a piece of code exists

---

### Guidelines
 
- *What*
    - *Complexity* - steps for convoluted operations should be explained.
    
- *Why*
    - *Bugs* - bugs fixes are generally counterintuitive when read without context. Commented bug fixes are organizational knowledge. 
    - *Workarounds* - counterintuitive workarounds to difficult problems must be documented. 
    
- *What* and *Why*
    - *Types and Functions* - some types and functions are very intuitive, and good naming helps. Even so, functionality and reason to exist should be documented.  
    
 ---

### Rule of Thumb

> Your code should be documented. You shouldn't trust future you's ability to understand what current you is thinking.
