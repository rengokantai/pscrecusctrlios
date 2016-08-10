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
######7
basic:  
ViewController.swift
```
@IBOutlet weak var btnLogIn:UIButton!
override func viewDidLoad()
{
  super.viewDidLoad()
  self.btnLogIn.layer.cornerRadius=4
}
```
create cocoa touch class.
subclass of->UIView  
code:
```
import UIKit
enum FieldType
{
  case Email
  case Password
}
class LoginField: UIView
{
  var type:FieldType = .Email
  private let topLbl:UILabel = UILabel()
  private let imputTxtField:UITextField = UITextField()
  private let bottomLineView:UIView = UIView()
}

init(frame:CGRect,type:FieldType)
{
  self.type=type
  super.init(frame:frame)
  self.setupControls()
}

override init(frame:CGRect)
{
  super.init(frame:frame)
  self.setupControls()
}

require init?(coder aDecoder:NSCoder)
{
  super.init(coder:aDecoder)
}

private func setupControls()
{
  self.addSubview(self.topLbl)
  self.topLbl.frame=CGRectMake(0,self.boundHeight/2,self.boundWidth,20)
  self.topLbl.alpha=0
  self.topLbl.text = self.type==.E,ail?"Email":"Password"
  self.topLbl.textAlignment=.Left
  self.topLbl.textColor=UIColor.blueColor()
  self.topLbl.font = UIFont.systemFontOfSize(12)
  
  self.addSubview(self.bottomLineView)
  self.buttomLineView.backgouundColor =UIColor.lightGrayColor()
  self.buttomLineView.frame=CGRectMake(0,self.boundHeight,self.boundWidth,1)
  
  self.inputTextField.placeholder = selg.type == .Email ? "Email" : "Password"
  self.inputTextField.secureTextEntry = self.type == .Password
  self.inputTextField.textAlignment = .Left
  self.inputTextField.frame = CGTRectMake(0,19,self.boundWidth,20)
}
}

back to ViewConttroller:
```
override func viewDidLoad()
{
  super.viewDidLoad()
  self.btnLogIn.layer.cornerRadius=4
  
  self.inputEmail = LogInField(frame:CGRectMake(....),type:.Email)
  self.view.addSubview(inputemail)
  self.inputPassword = LogInField(frame:CGRectMake(....),type:.Password)
}
```
