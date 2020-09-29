

# Summary of SwiftUI

*** 
## UI Elements

# 
### Form
* Use `Form {}`
  * Example
  ```
  Form {
      Text("Hi, people")
  }
  ```

# 
### Group
* SwiftUI doesn't allow more than 10 elements for each *closure*
  * To avoid this problem, we use `Group {}`

# 
### NavigationView
* Use `NavigationView {}`
  * Use to add a navigation bar title

    `.navigationBarTitle(Text("Title"))`
  * Can customize with `displayMode`, using for example: `.large`, `.inline`, `.automatic`
      `.navigationBarTitle(Text("Title"), displayMode: .large)`
  
  * Example:

      ```
      NavigationView {
        Text("Hello, World!")
            .navigationBarTitle("Navigation")
      }
      ```

* We present new views using `NavigationLink`
  * Example

      ```
      NavigationView {
        NavigationLink(destination: Text("Another View")) {
            Text("Hi from another view!")
        }.navigationBarTitle("Navigation Link")
      }
    ```

# 
### Button
* Use `Button("Title") {actionOfButton()}`

*** 
## Logic

# 
### property wrapper
* In *Swift*, if we want to change properties of a *struct* in a function, we have to
  add *mutating* in front of the function. Though, *SwiftUI* doesn't let us use it
  for *some View*
  * To be able to do it, we have to use a **property wrapper** called **@State**
  * It allows *SwiftUI* to store the propriety and change it.
  * *Apple* recommends to add *private* for each of those property
    * Example `@State private var test = 0`
