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

imageViewObject.contentMode = UIViewContentMode.ScaleToFill 
//imageViewObject.contentMode = UIViewContentMode.ScaleAspectFit 
//imageViewObject.contentMode = UIViewContentMode.ScaleAspectFill
```
###Adding UITextField on UIView Programmatically Swift

```swift
var textFiled = UITextField(frame: CGRectMake(20.0, 30.0, 100.0, 33.0))
        textFiled.backgroundColor = UIColor.redColor()
        textFiled.borderStyle = UITextBorderStyle.Line
        self.view.addSubview(textFiled)
```
link: http://stackoverflow.com/questions/24710041/adding-uitextfield-on-uiview-programmatically-swift

##How do I create a new Swift project without using Storyboards?

link: http://stackoverflow.com/questions/24046898/how-do-i-create-a-new-swift-project-without-using-storyboards


###Adding UISearchBar Programmatically to UITableView
link: http://stackoverflow.com/questions/6947858/adding-uisearchbar-programmatically-to-uitableview

###create scrollview programmatically in swift without outlet

link :http://stackoverflow.com/questions/28156911/create-scrollview-programmatically-in-swift-without-outlet


##Creating a UICollectionView programmatically
```swift
class TwoViewController: UIViewController,UICollectionViewDataSource,UICollectionViewDelegateFlowLayout,UICollectionViewDelegate {

    override func viewDidLoad() {
        super.viewDidLoad()

        var flowLayout:UICollectionViewFlowLayout = UICollectionViewFlowLayout();

        var __collectionView:UICollectionView? = UICollectionView(frame: CGRectMake(10, 10, 300, 400), collectionViewLayout: flowLayout);
        __collectionView?.registerClass(UICollectionViewCell.self, forCellWithReuseIdentifier: "collectionCell");
        __collectionView?.delegate = self;
        __collectionView?.dataSource = self;
        __collectionView?.backgroundColor = UIColor.cyanColor();

        self.view.addSubview(__collectionView!);
    }

    func collectionView(collectionView: UICollectionView, numberOfItemsInSection section: Int) -> Int
    {
        return 20;
    }

    func collectionView(collectionView: UICollectionView, cellForItemAtIndexPath indexPath: NSIndexPath) -> UICollectionViewCell
    {
        var cell:UICollectionViewCell=collectionView.dequeueReusableCellWithReuseIdentifier("collectionCell", forIndexPath: indexPath) as UICollectionViewCell;

        cell.backgroundColor = UIColor.greenColor();
        return cell;
    }

    func collectionView(collectionView: UICollectionView, layout collectionViewLayout: UICollectionViewLayout, sizeForItemAtIndexPath indexPath: NSIndexPath) -> CGSize
    {
        return CGSizeMake(50, 50);
    }

    func collectionView(collectionView: UICollectionView, layout collectionViewLayout: UICollectionViewLayout, insetForSectionAtIndex section: Int) -> UIEdgeInsets
    {
        return UIEdgeInsetsMake(5, 5, 5, 5); //top,left,bottom,right
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
    }
}
```

link: http://stackoverflow.com/questions/17856055/creating-a-uicollectionview-programmatically
      http://randexdev.com/2014/07/uicollectionview/

###Creating a navigationController programatically (Swift)
```swift
self.window = UIWindow(frame: UIScreen.mainScreen().bounds)
var nav1 = UINavigationController()
var mainView = ViewController(nibName: nil, bundle: nil) //ViewController = Name of your controller
nav1.viewControllers = [mainView]
self.window!.rootViewController = nav1
self.window?.makeKeyAndVisible()
```
link:
http://stackoverflow.com/questions/28793331/creating-a-navigationcontroller-programatically-swift
http://stackoverflow.com/questions/22981610/programatically-creating-uinavigationcontroller-in-ios
###Adding progress icon programmatically to a new UIView
```swift
 override func loadView() {
        super.loadView()

        var baseView = UIView()
        baseView.backgroundColor = UIColor(red: 13/255, green: 44/255, blue: 75/255, alpha: 1)
        self.view = baseView

        var progressIcon = UIActivityIndicatorView()
        progressIcon.setTranslatesAutoresizingMaskIntoConstraints(false)
        progressIcon.activityIndicatorViewStyle = UIActivityIndicatorViewStyle.WhiteLarge
        view.addSubview(progressIcon)
        progressIcon.startAnimating()

        var constraints = [NSLayoutConstraint]()
        constraints.append(NSLayoutConstraint(
            item: progressIcon,
            attribute: .CenterX,
            relatedBy: .Equal,
            toItem: view,
            attribute: .CenterX,
            multiplier: 1,
            constant: 0)
        )
        constraints.append(NSLayoutConstraint(
            item: progressIcon,
            attribute: .CenterY,
            relatedBy: .Equal,
            toItem: view,
            attribute: .CenterY,
            multiplier: 1,
            constant: 0)
        )

        view.addConstraints(constraints)

    }
```
link: https://coderwall.com/p/6onn0g/adding-progress-icon-programmatically-to-a-new-uiview

###UITextView
```swift
var textview = UITextView(frame:CGRectMake(10,100,200,100))
textview.layer.borderWidth = 1
textview.layer.borderColor = UIColor.grayColor().CGColor
self.view.addSubview(textview)
//textview.editable = false 
```
###UIProgressView
```swift
var progressView = UIProgressView(progressViewStyle:UIProgressViewStyle.Default)
progressView.center = self.view.center
progressView.progress = 0.5
self.view.addSubview(progressView)
progressView.setProgress(0.8,animated:true)
progressView.progressTintColor = UIColor.greenColor()
progressView.trackTintColor = UIColor.blueColor()
```
#Swift auto layout programmatically and dynamic

####Swift auto layout programmatically and dynamic
link: http://stackoverflow.com/questions/29758455/swift-auto-layout-programmatically-and-dynamic

####how to set size UIView in auto layout programmatically swift?
link:http://stackoverflow.com/questions/30421206/how-to-set-size-uiview-in-auto-layout-programmatically-swift

####Display iPad and landscape views using Swift Autolayout and Size Classes Programmatically
link: http://www.digistarters.com/swift-autolayout-and-size-classes-programmatically/

###UIAlertView
```swift
import UIKit
class ViewController:UIViewController{
        override func viewDidLoad(){
                super.viewDidLoad()
                var alertView = UIAlertView()
                alertView.title = "messageTitle"
                alertView.message = "are you true to delete this item?"
                alertView.addButtonWithTitle("Cannel")
                alertView.addButtonWithTitle("Ok")
                alertView.cannelButtonIndex = 0
                alertView.delegate = self
                alertView.show()
        }
        
        func alertView(alertView:UIAlertView,clickedButtonAtIndex buttonIndex:Int){
                if(buttonIndex==alertView.cannelButtonIndex){
                        printIn("you clicked cannel button")
                }else{
                        printInt("you clicked Ok button")
                }
        }
}
```
###UIActionSheet
```swift
import UIKit

class ViewController:UIViewController,UIActionSheetDelegate{
        override func viewDidLoad(){
                super.viewDidLoad()
                var actionSheet = UIActionSheet()
                // actionSheet.title = "the title"
                actionSheet.addButtonWithTitle("cannel")
                actionSheet.addButtonWithTitle("action 1")
                actionSheet.addButtonWithTitle("action 2")
                actionSheet.cannelButtonIndex = 0
                actionSheet.delegate = self
                actionSheet.showInView(self.view)
        }
        
        func actionsheet(actionSheet:UIActionSheet!,clickedButtonAtIndex buttonIndex:Int){
                printInt("you clicked:"+actionSheet.buttonTitleAtIndex(buttonIndex))
        }
}
```
###UIScrollView
```swift
override func viewDidLoad(){
        super.viewDidLoad()
        var scrollView = UIScrollView()
        scrollView.frame = self.view.bounds
        var imageView = UIImageView(image:UIImage(name:"imgName"))
        scrollView.contentSize = imageView.bounds.size
        scrollView.addSubview(imageView)
        self.view.addSubview(scrollView)
        
        // zoom
        scrollView.minimumZoomScale = 0.1
        scrollView.maximunZoomScale = 3
        scrollView.delegate = self
}

//UIscrollViewDelegate
func viewForZoomingInScrollView(scrollView:UIScrollView!) -> UIView!{
        for subview:AnyObject in scrollView.subviews{
                if subview.isKindOfClass(UIImageView){
                        return subview as UIView
                }
        }
        return nil
}

```
###Delegates in swift
link: http://stackoverflow.com/questions/24099230/delegates-in-swift

###Learn Swift from Objective-C : Protocols and Delegation
link: http://codewithchris.com/learn-swift-from-objective-c-part3/
