# **Move data between view Controllers**

#### *In Swift, there are several ways to move data between view controllers. Here are a few options:*

- **`Using a segue:`** A segue is a visual transition from one view controller to another. You can use a segue to pass data between the view controllers. Here's an example:

In your first view controller, create a variable to hold the data you want to pass:
```swift
var myData: String = "Hello World"
```
Then, create a segue from your first view controller to your second view controller in your storyboard. Give the segue an identifier (e.g. "mySegue").

In your first view controller, override the prepare(for:sender:) method and pass the data to the second view controller:

```swift
override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
    if segue.identifier == "mySegue" {
        if let destinationVC = segue.destination as? SecondViewController {
            destinationVC.receivedData = myData
        }
    }
}
```
In your second view controller, create a variable to receive the data:

```swift
var receivedData: String?
```
Now, when the segue is performed, the prepare(for:sender:) method is called and the data is passed to the second view controller.

---

- **`Using a delegate:`** A delegate is an object that acts on behalf of another object. You can use a delegate to pass data between view controllers. Here's an example:

In your first view controller, create a protocol to define the delegate methods:

```swift
protocol MyDelegate {
    func sendData(data: String)
}
```
Create a variable to hold the delegate:

```swift
var delegate: MyDelegate?
```
When you want to pass the data, call the delegate method:

```swift
delegate?.sendData(data: "Hello World")
```
In your second view controller, conform to the delegate protocol:

```swift
class SecondViewController: UIViewController, MyDelegate {
    // ...
    
    func sendData(data: String) {
        // Do something with the data
    }
}
```
Set the second view controller as the delegate of the first view controller:

```swift
let secondVC = SecondViewController()
secondVC.delegate = self
```

Now, when the data is passed, the delegate method is called in the second view controller.

---

- **`Using a singleton:`** A singleton is a class that has only one instance. You can use a singleton to store data that can be accessed from multiple view controllers. Here's an example:

Create a singleton class:

```swift
class DataManager {
    static let shared = DataManager()
    
    var myData: String = "Hello World"
}
```
In your first view controller, set the data:

```swift
DataManager.shared.myData = "Hello World"
```
In your second view controller, access the data:

```swift
let data = DataManager.shared.myData
```
Now, the data can be accessed from anywhere in your app.
