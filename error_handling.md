# Error Handling

### Values

- All errors should be funneled through one Error structure within the application.
- When errors are handled, they should be handled completely and in only one location.
- Errors should be handled in the same way consistently throughout an application.

---

<details><summary>Context</summary><p>

There are three overarching types of errors: 

- *silent* - The error is minor or expected and does not significantly effect the user experience. 
- *surfaceable* - The error significantly affects the user experience and therefore should be surfaced to the user.
- *critical* - The error puts the application is in a dangerous state and should crash. 

Several operations are rife with opportunities for errors. For example, a standard URL request has multiple failure points. 

![Standard URLRequest Errors Image](https://github.com/fuzz-productions/iOSPlaybook/blob/master/opportunities_for_error.png)

</p></details>

---

<details><summary>Recommendations</summary><p>

Error handling is highly contextual, and therefore no set protocol for error handling across projects is currently set. However, here are some thoughts on the matter. 

- Error Structure

  *Having a singlular place to funnel every error an application throws should be a feature in every application.* 
  
  - *Option Set* - Using an option set can be beneficial to track errors that are coming back from chained calls (especially to multiple API's). Option sets can help track exactly where an error failed. 
  - *Protocol Extensions for Views* - having views that present errors conform to an ErrorPresenter protocol that handles errors allows views to present errors in the same fashion consistently throughout the application. 

- Request Structure
  
  - *State Tracking* - Using enums to track state for requests can allow for views to adapt for errors from a more central location. More on this strucure [here.](http://khanlou.com/2017/03/that-one-optional-property/)

</p></details>

---
