<p align="center">
  <h1 align="center">TransitionViewController</h1>
</p>

TransitionViewController is the protage of <a href="https://github.com/remirobert/RRCustomPageController">RRCustomPageController</a> for Swift language.
Check out the link for more details.

<hr>
<h1 align="center">How to use it</h1>

Firstly, you have to add the protocol **PageController** to your UIViewController class.

```Swift
@objc protocol PageController {
    var titlePageController: String? {get set}
    var imagePageController: UIImage? {get set}
}
```

<hr>

```Swift
func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
  self.window = UIWindow(frame: CGRectMake(0, 0, UIScreen.mainScreen().bounds.size.width,
                                                  UIScreen.mainScreen().bounds.size.height))
        
  var c1 = testViewController()
  c1.imagePageController = UIImage(named: "user3")

  var c2 = testViewController()
  c2.titlePageController = "Custom Transition"

  var c3 = testViewController()
  c3.imagePageController = UIImage(named: "like")
      
  let transitionController = TransitionViewController(controllersParam: [c1, c2, c3])
  transitionController.startController = 1
        
  self.window?.rootViewController = transitionController
  self.window?.makeKeyAndVisible()
  return true
}
```

<h1 align="center">Author</h1>
Rémi ROBERT, remi.robert@epitech.eu

<h1 align="center">License</h1>
TransitionViewController is available under the MIT license. See the LICENSE file for more info.

