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
```
##Programmatically creating UIView, UISlider, UISwitch Using Swift

###UIView
```swift
var DynamicView=UIView(frame: CGRectMake(100, 200, 100, 100))
DynamicView.backgroundColor=UIColor.greenColor()
DynamicView.layer.cornerRadius=25
DynamicView.layer.borderWidth=2
self.view.addSubview(DynamicView)
```
###UISlider
```swift
var sliderDemo = UISlider(frame:CGRectMake(20, 260, 280, 20))
sliderDemo.minimumValue = 0
sliderDemo.maximumValue = 100
sliderDemo.continuous = true
sliderDemo.tintColor = UIColor.redColor()
sliderDemo.value = 50
sliderDemo.addTarget(self, action: "sliderValueDidChange:", forControlEvents: .ValueChanged)
self.view.addSubview(sliderDemo)

func sliderValueDidChange(sender:UISlider!)
{
println("value--\(sender.value)")
}
```
###UISwitch
```swift
var switchDemo=UISwitch(frame:CGRectMake(150, 300, 0, 0));
switchDemo.on = true
switchDemo.setOn(true, animated: false);
switchDemo.addTarget(self, action: "switchValueDidChange:", forControlEvents: .ValueChanged);
self.view.addSubview(switchDemo);

func switchValueDidChange(sender:UISwitch!)
{
if (sender.on == true){
println(“on”)
}
else{
println(“off”)
}
}
```
from :http://www.apptuitions.com/programmatically-creating-uiview-uislider-uiswitch-using-swift/

##Passing Data through View Controllers with Swift without Using Storyboard
 
 ```swift
 class UberWebviewController : UIViewController {

    var dataFromAPI : [Any]

    init(data someData : [Any]) {
        self.dataFromAPI = someData
        super.init()
    }

    required init(coder aDecoder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }

}


let viewController = UberWebviewController(data: whateverYourDataIs)
self.navigationController?.presentViewController(viewController, animated: true, completion: nil)

 ```
 from : http://stackoverflow.com/questions/27047904/passing-data-through-view-controllers-with-swift-without-using-storyboard
 
 http://stackoverflow.com/questions/31813942/swift-programmatically-navigate-to-viewcontroller-and-pass-data


##Programmatically creating UIButton,UILabel,UITextField Using Swift
###UIButton
```swift
let dunamicButton = UIButton.buttonWithType(UIButtonType.System) as UIButton
dunamicButton.backgroundColor = UIColor.greenColor()
dunamicButton.setTitle("Button", forState: UIControlState.Normal)
dunamicButton.frame = CGRectMake(100, 100, 100, 50)
dunamicButton.addTarget(self, action: "buttonTouched:", forControlEvents: UIControlEvents.TouchUpInside)
self.view.addSubview(dunamicButton)

func buttonTouched(sender:UIButton!)
{
println("It Works!!!")
}
```
link: http://stackoverflow.com/questions/24030348/how-to-create-a-button-programmatically
http://stackoverflow.com/questions/24102191/make-a-uibutton-programatically-in-swift

###UILabel

```swift
var dynamicLabel: UILabel = UILabel()
dynamicLabel.frame = CGRectMake(50, 150, 200, 21)
dynamicLabel.backgroundColor = UIColor.orangeColor()
dynamicLabel.textColor = UIColor.blackColor()
dynamicLabel.textAlignment = NSTextAlignment.Center
dynamicLabel.text = "test label"
self.view.addSubview(dynamicLabel)
```

###UITextField

```swift
var dynamicTxtField: UITextField = UITextField()
dynamicTxtField.frame = CGRectMake(50, 70, 200, 30)
dynamicTxtField.backgroundColor = UIColor.lightGrayColor()
self.view.addSubview(dynamicTxtField)
```
from:http://www.apptuitions.com/programmatically-creating-uibuttonuilabeluitextfield-using-swift/

##Programmatically creating UIStepper and UISegmentedControl Using Swift

###UIStepper
```swift
var customStepper = UIStepper (frame:CGRectMake(110, 250, 0, 0))
customStepper.wraps = true
customStepper.autorepeat = true
customStepper.maximumValue = 10
customStepper.addTarget(self, action: "stepperValueChanged:", forControlEvents: .ValueChanged)
self.view.addSubview(customStepper)

func stepperValueChanged(sender:UIStepper!)
{
println("It Works, Value is --&gt;\(Int(sender.value).description)")
}
```

###UISegmentedControl
```swift
var customSegmentedControl = UISegmentedControl (items: ["one","two","three"])
customSegmentedControl.frame = CGRectMake(60, 250,200, 30)
customSegmentedControl.selectedSegmentIndex = 1
customSegmentedControl.tintColor = UIColor.redColor()
customSegmentedControl.addTarget(self, action: "segmentedValueChanged:", forControlEvents: .ValueChanged)
self.view.addSubview(customSegmentedControl)

func segmentedValueChanged(sender:UISegmentedControl!)
{
println("It Works, Value is --&gt;\(sender.selectedSegmentIndex)")
}
```
from: http://www.apptuitions.com/programmatically-creating-uistepper-and-uisegmentedcontrol-using-swift/

###UIImageview Programmatically in swift
```swift
var imageViewObject :UIImageView
imageViewObject = UIImageView(frame:CGRectMake(0, 0, 100, 100));
imageViewObject.image = UIImage(named:"imageName.png")
self.view.addSubview(imageViewObject)

imageViewObject.contentMode = UIViewContentMode.ScaleToFill //imageViewObject.contentMode = UIViewContentMode.ScaleAspectFit || imageViewObject.contentMode = UIViewContentMode.ScaleAspectFill
```
