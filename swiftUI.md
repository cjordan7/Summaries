

# Summary of SwiftUI

*** 
## Views

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
### Section
* To create section in tables: `Section {}`
* Use `Section(header: Text("Set header")) {}` to set the header
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

# 
### TextField
* Use `TextField("Text", text: $variable)`
  * The `$` is used as a two way binding with the variable `variable`.Each time someone
    taps something in the text field, it will update the variable.
  * Notice that `variable` must be a `@State`
  * Use `.keyboardType(.numberPad)` for type of keyboard. Use either `.numberPad`,
    `.decimalPad`, ...
  * Example:
  ```
  struct ContentView: View {
    @State private var testVar = ""

    var body: some View {
        Form {
            TextField("EnterSomething", text: $testVar)
            Text("Hello World")
        }
    }
  }
  ```

# 
### ForEach
* Construct is `ForEach(0..<10) {n in Text("ForEach \(n)")}` or is simply 
* Construct is `ForEach(0..<10) {Text("ForEach \($0)")}` because `ForEach` is a closure.

# 
### Picker
* Use `Picker("Title", selection: $binding) {}`
  * where `@State private var binding = 0`
  * Use `.pickerStyle(SegmentedPickerStyle())` for segmented style
# 
### Stack
* Use `VStack {}` to stack horizontal elements
* Use `HStack {}` to stack vertical elements
* Use `ZStack {}` to stack elements on top of each other
  * 

*** 
## Logic

# 
### property wrapper
* In *Swift*, if we want to change properties of a *struct* in a function, we have to
  add *mutating* in front of the function. Though, *SwiftUI* doesn't let us use it
  for *some View*
  * To be able to do it, we have to use a **property wrapper** called **@State**
  * It allows *SwiftUI* to store the propriety and change it.
  * *Apple* recommends to add *private* for each of those properties
    * Example `@State private var test = 0`
