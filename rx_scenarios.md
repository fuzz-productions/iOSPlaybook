### Rx Scenarios


--Nick
- I want to convert the Element type in an Observable 
  - I have a TextField's text bound to Observable<String> but I want an Observable<Bool> to tell me if the input is valid
    ``` 
        textfield.rx.text
          .map { $0.count >= 5 }
          .bind(to: button.rx.enabled)
          .disposed(by: disposeBag)
    ```
   - I have a model but only want the `.firstName` value to put into a UILabel
         ``` 
        Observable<Profile>.just(...)
          .map { $0.firstName }
          .bind(to: firstNameLabel.rx.text)
          .disposed(by: disposeBag)
    ```
  ## Map
  
 - I have two Observables, I need to know the value of both to compute the proper response
   - as a user types in thier zipcode I want to validate their input informed by the country they live in
   ``` 
        textfield.rx.text
          .withLatestFrom(country) {  text, country in
            switch country{
              case .usa:
                  return text.length > 4
              case .britain:
                  return text.length > 8
              default:
                  return text.length > 6
          }
          .bind(to: button.rx.enabled)
          .disposed(by: disposeBag)
    ```
    This version of withLatestFrom uses a result selector that can fire each time `.text` is changed when country has had at least on value, the result selector acts like a mpa with 2 inputs
    
    ## WithLatestFrom
    
