

# Summary of SwiftUI

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
