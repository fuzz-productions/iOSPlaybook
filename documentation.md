
# Documentation 

### Values

Documentation is imperative. Given that we are an agency, our code is consumed by many developers inside and outside of Fuzz. Documentation should be updated and written in a manner that considers what a new programmer on the project would deem useful. 

You may still need [persuasion.](http://ericasadun.com/2016/11/03/swift-holy-war-comments-are-not-an-anti-pattern/)

--- 

<details><summary>Context</summary><p>

There are two types of documentation, which we describe as 'What' and 'Why'. 

- *What*: explains what a piece of code does

- *Why*: explains why a piece of code exists

</p></details>

---

<details><summary>Guidelines</summary><p>
 
- *What*
    - *Complexity* - steps for convoluted operations should be explained.
    
- *Why*
    - *Bugs* - bugs fixes are generally counterintuitive when read without context. Commented bug fixes are organizational knowledge. 
    - *Workarounds* - counterintuitive workarounds to difficult problems must be documented. 
    - *Context* - some code only makes sense in the specific context in which it is implemented.  For instance, delegate patterns often fall victim to a lack of contextual knowledge necessary to make an informed decision about the code and should be documented.
    
- *What* and *Why*
    - *Types and Functions* - some types and functions are very intuitive, and good naming helps. Even so, functionality and reason to exist should be documented.  
    
</p></details>
    
 ---
 
 <details><summary>Rule of Thumb</summary><p>

- Your code should be documented. You shouldn't trust future you's ability to understand what current you is thinking.
- Documentation is more than just providing Apple-like documentation on functions.  It is providing clear, contextual knowledge about code when and where necessary to aid other developers understanding.  
- A simple library that is often used to centralize documentation in a remote repo is [Jazzy](https://github.com/realm/jazzy)

</p></details>

---
