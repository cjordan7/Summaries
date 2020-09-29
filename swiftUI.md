

# Summary of SwiftUI

* Group {}
* Form {}

# 
### NavigationView
* NavigationView
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
