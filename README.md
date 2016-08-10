#### pscrecusctrlios
######6
```
responder.motionBegan(UIEventSubtype.MotionShake,withEvent:UIEvent())
responder.touchesBegan(Set([UITouch()]),withEvent:UIEvent())
```
view:
```
import UIKit
let aView = UIView()
let anotherView = UIView()
aView.addSubview(anotherView)

let aViewController = UIViewController()
aViewController.view.addSubView(anotherView)

let swipe = UISwipeGestureRecognizer()
aView.addGestureRecognizer(swipe)
```
