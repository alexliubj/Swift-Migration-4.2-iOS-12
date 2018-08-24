There are usually two ways to migrate your project from an older version of swift into the latest version.
First of all, you should download and install the latest Xcode either from AppStore or Apple Developer center.
Secondly, you have an option of either from manual mode or let Xcode do it for you.

![ ](https://github.com/alexliubj/Swift-Migration-4.2/blob/master/sc01.jpg)

Change it from your project setting -> `Swift Language Version`, from the dropdown, select the latest version of Swift, like 4.2. Then compile/build your code, fix each warning/error one by one with some hint for Xcode like the following.

![ ](https://github.com/alexliubj/Swift-Migration-4.2/blob/master/sc02.jpg)

![ ](https://github.com/alexliubj/Swift-Migration-4.2/blob/master/sc03.jpg)

Moreover, XCode should also be able to migrate all your old version swift code into new version but somehow, we always have third party libraries or some other dependencies in the project. From my personal experience it never worked for me for a single time when projects are more complicated or with a huge code base. You may still have to go back to the manual mode again.

![ ](https://github.com/alexliubj/Swift-Migration-4.2/blob/master/sc04.jpg)

I've listed all migration issues I met when I was migrating from Swift 4 to 4.2 below. Please feel free to add anything I'm missing with your Pull Requests and for sure there would be a lot. With this document I hope it will help user with their migrations go smoothly and it would also be a good reference to when reviewing legacy code.


## UIKit
#Swift4/UIKit

### UITableViewCell
| Swift 4 | Swift 4.2 |
| --- | --- |
| UITableViewCellStyle | UITableViewCell.CellStyle |

### UIEvent

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIEventSubtype | UIEvent.EventSubtype |

### UITableView

| Swift 4 | Swift 4.2 |
| --- | --- |
| UITableViewScrollPosition | UITableView.ScrollPosition |
| UITableViewAutomaticDimension | UITableView.automaticDimension |
| UITableViewCellEditingStyle | UITableViewCell.EditingStyle |
| UITableViewRowAnimation | UITableView.RowAnimation |
| UITableViewStyle | UITableView.Style |
| UITableViewCellAccessoryType |  UITableViewCell.AccessoryType |

### UIControl

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIControlEvents | UIControl.Event |

### UIWindow

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIWindowLevelAlert | UIWindow.Level.alert  |
| UIKeyboardFrameEndUserInfoKey | UIResponder.keyboardFrameEndUserInfoKey |
| UIKeyboardFrameBeginUserInfoKey | UIResponder.keyboardFrameBeginUserInfoKey|
| UIKeyboardAnimationDurationUserInfoKey| UIResponder.keyboardAnimationDurationUserInfoKey|
| UIKeyboardAnimationCurveUserInfoKey| UIResponder.keyboardAnimationCurveUserInfoKey|
| UIKeyboardIsLocalUserInfoKey| UIResponder.keyboardIsLocalUserInfoKey|
| UIWindowDidBecomeVisible| UIWindow.didBecomeVisibleNotification|
| UIWindowDidBecomeHidden| UIWindow.didBecomeHiddenNotification|
| UIWindowDidBecomeKey| UIWindow.didBecomeKeyNotification|
| UIWindowDidResignKey| UIWindow.didResignKeyNotification|
| UIKeyboardWillShow| UIResponder.keyboardWillShowNotification|
| UIKeyboardDidShow| UIResponder.keyboardDidShowNotification|
| UIKeyboardWillHide| UIResponder.keyboardWillHideNotification|
| UIKeyboardDidHide| UIResponder.keyboardDidHideNotification|

### UIViewController

| Swift 4 | Swift 4.2 |
| --- | --- |
| open func addChildViewController(_ childController: UIViewController) | open func addChild(_ childController: UIViewController) |
| open func willMove(toParentViewController parent: UIViewController?) | open func willMove(toParent parent: UIViewController?) |
| open func didMove(toParentViewController parent: UIViewController?) |     open func didMove(toParent parent: UIViewController?) |
| open func removeFromParentViewController() |  open func removeFromParent() |
  
### UIActivity

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIActivityType |  UIActivity.ActivityType |

### UIActivityIndicatorView

| Swift 4 | Swift 4.2 |
| --- | --- |
| activityIndicator.activityIndicatorViewStyle | activityIndicator.style |

### UIAlertController

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIAlertActionStyle | UIAlertAction.Style |
| UIAlertControllerStyle |  UIAlertController.Style |


### UIPageViewController

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIPageViewControllerNavigationDirection | UIPageViewController.NavigationDirection |
| UIPageViewControllerSpineLocation| UIPageViewController.SpineLocation |
| UIPageViewControllerNavigationOrientation| UIPageViewController.NavigationOrientation |
| UIPageViewControllerTransitionStyle| UIPageViewController.TransitionStyle |
| UIPageViewControllerOptionsKey| UIPageViewController.OptionsKey |

### UINavigationController

| Swift 4 | Swift 4.2 |
| --- | --- |
| UINavigationControllerOperation |  UINavigationController.Operation |

### UIGestureRecognizer

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIGestureRecognizerStatePossible | UIGestureRecognizer.State.possible  |
| UIGestureRecognizerStateBegan |  UIGestureRecognizer.State.began |
| UIGestureRecognizerStateChanged |  UIGestureRecognizer.State.changed |
| UIGestureRecognizerStateEnded | UIGestureRecognizer.State.ended  |
| UIGestureRecognizerStateCancelled | UIGestureRecognizer.State.cancelled  |
| UIGestureRecognizerStateFailed | UIGestureRecognizer.State.failed  |
| UIGestureRecognizerStateRecognized | UIGestureRecognizer.State.recognized  |

### NSLayoutFormat

| Swift 4 | Swift 4.2 |
| --- | --- |
| NSLayoutFormatOptions |  NSLayoutConstraint.FormatOptions |

### UIEdgeInsets

| Swift 4 | Swift 4.2 |
| --- | --- |
| public func UIEdgeInsetsMake(_ top: CGFloat, _ left: CGFloat, _ bottom: CGFloat, _ right: CGFloat) -> UIEdgeInsets | UIEdgeInsets(top: CGFloat, left: CGFloat, bottom: CGFloat, right: CGFloat) |
| public func UIEdgeInsetsInsetRect(_ rect: CGRect, _ insets: UIEdgeInsets) -> CGRect | public func inset(by insets: UIEdgeInsets) -> CGRect |

### UIFontDescriptor

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIFontDescriptorSymbolicTraits |  UIFontDescriptor.SymbolicTraits |


### UIImage
| Swift 4 | Swift 4.2 |
| --- | --- |
|UIKIT_EXTERN  NSData * __nullable `UIImagePNGRepresentation`(UIImage * __nonnull image);  |public func `pngData()` -> Data?|
|NSData * __nullable `UIImageJPEGRepresentation`(UIImage * __nonnull image, CGFloat compressionQuality);|public func `jpegData`(compressionQuality: CGFloat) -> Data?|

### UIApplication

| Swift 4 | Swift 4.2 |
| --- | --- |
| UIApplicationDidEnterBackground | UIApplication.didEnterBackgroundNotification |
| UIApplicationWillEnterForeground |UIApplication.willEnterForegroundNotification  |
| UIApplicationDidFinishLaunching |UIApplication.didFinishLaunchingNotification |
| UIApplicationDidBecomeActive | UIApplication.didBecomeActiveNotification|
| UIApplicationWillResignActive | UIApplication.willResignActiveNotification|
| UIApplicationDidReceiveMemoryWarning | UIApplication.didReceiveMemoryWarningNotification|
| UIApplicationWillTerminate | UIApplication.willTerminateNotification|
| UIApplicationSignificantTimeChange | UIApplication.significantTimeChangeNotification|
| UIApplicationWillChangeStatusBarOrientation | UIApplication.willChangeStatusBarOrientationNotification|
| UIApplicationDidChangeStatusBarOrientation |UIApplication.didChangeStatusBarOrientationNotification |
| UIApplicationDidChangeStatusBarFrame| UIApplication.didChangeStatusBarFrameNotification|
| UIApplicationBackgroundRefreshStatusDidChange| UIApplication.backgroundRefreshStatusDidChangeNotification|
| UIApplicationProtectedDataWillBecomeUnavailable| UIApplication.protectedDataWillBecomeUnavailableNotification|
| UIApplicationProtectedDataDidBecomeAvailable| UIApplication.protectedDataDidBecomeAvailableNotification|
| UIApplicationUserDidTakeScreenshot| UIApplication.userDidTakeScreenshotNotification|
| UIApplicationOpenSettingsURLString |  UIApplication.openSettingsURLString |
| UIApplicationLaunchOptionsKey | UIApplication.LaunchOptionsKey|
| UIInterfaceOrientationIsLandscape() | UIApplication.shared.statusBarOrientation.isLandscape |

### UIView
| Swift 4 | Swift 4.2 |
| --- | --- |
|func `bringSubview`(toFront view: UIView)|func `bringSubviewToFront`(_ view: UIView)|
| UIViewAnimationOptions | UIView.AnimationOptions()|

## Foundation

### NSAttributedString

| Swift 4 | Swift 4.2 |
| --- | --- |
|NSAttributedStringKey|NSAttributedString.Key|

## QuartzCore

### CAShapeLayer

| Swift 4 | Swift 4.2 |
| --- | --- |
|kCALineCapRound|CAShapeLayerLineCap.round|
|kCALineCapButt |CAShapeLayerLineCap.butt |
|kCALineCapSquare |CAShapeLayerLineCap.square |
|kCALineJoinMiter |CAShapeLayerLineJoin.miter |
|kCALineJoinRound | CAShapeLayerLineJoin.round|
|kCALineJoinBevel | CAShapeLayerLineJoin.bevel|
|kCAFillRuleNonZero | CAShapeLayerFillRule.nonZero|
|kCAFillRuleEvenOdd | CAShapeLayerFillRule.evenOdd|


Other resources: 
> https://swift.org/migration-guide-swift4.2/

> https://github.com/apple/swift-evolution

> https://developer.apple.com/videos/play/wwdc2018/202/

> https://github.com/apple/swift
