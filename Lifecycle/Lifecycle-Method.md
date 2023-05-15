 # **Lifecycle method**

#### *In Swift, a lifecycle method is a method that is called at various points during the lifetime of an object, such as a view controller or a view. These methods allow you to perform certain actions or respond to certain events at specific times during the object's lifetime.*

    Here are some common lifecycle methods for view controllers in Swift:

1. `viewDidLoad()`: This method is called when the view controller's view is loaded into memory. You can use this method to perform any setup that needs to be done before the view is displayed, such as setting up UI elements or initializing data.

2. `viewWillAppear(_:)`: This method is called just before the view controller's view is about to be displayed on the screen. You can use this method to perform any last-minute setup or to update the UI based on changes that have occurred since the view was last displayed.

3. `viewDidAppear(_:)`: This method is called after the view controller's view has been displayed on the screen. You can use this method to perform any actions that should occur when the view is visible, such as starting animations or playing videos.

4. `viewWillDisappear(_:)`: This method is called just before the view controller's view is removed from the screen. You can use this method to perform any cleanup or to save any data that needs to be saved before the view disappears.

5. `viewDidDisappear(_:)`: This method is called after the view controller's view has been removed from the screen. You can use this method to perform any actions that should occur when the view is no longer visible, such as stopping animations or releasing resources.

###### *Other objects, such as views or table view cells, also have their own lifecycle methods that you can use to respond to events during their lifetime. These methods can be very useful for managing the behavior of your app and ensuring that everything works as expected.*
