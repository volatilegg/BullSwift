**Bug010: Infinite loop when subclassing MKAnnotationView and calling init from init(withFrame: _) overloads**

_Issue:_
- Crashed bug in iOS 9.3 which related to MKMapAnnotationView init looping
- Calling self.init(withFrame: _) inside convenient init(withFrame: _) methods which cause the crash loop

_Solution:_
- Removed the whole method if unnecessary
- Change self.init > super.init 
- Change convenient init(withFrame: _) to init() only

_Reason:_
- Calling self.init inside init(), what could go wrong?
- The same code not crashes in iOS 10+, which need more digging 