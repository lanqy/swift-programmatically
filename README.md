# swift-programmatically
swift programmatically without storyboard
##Add tabs programmatically in UITabBarController with swift
```swift
func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: NSDictionary?) -> Bool {
        // Override point for customization after application launch.
        self.window = UIWindow(frame: UIScreen.mainScreen().bounds)
        
        var nav1 = UINavigationController()
        var first = FirstViewController(nibName: nil, bundle: nil)
        nav1.viewControllers = [first]
        
        var second = SecondViewController(nibName: nil, bundle: nil)
        var nav2 = UINavigationController()
        nav2.viewControllers = [second]
        
        var tabs = UITabBarController()
        tabs.viewControllers = [nav1, nav2]
        
        self.window!.rootViewController = tabs;
        self.window?.makeKeyAndVisible();
        
        return true
    }
  swift```
