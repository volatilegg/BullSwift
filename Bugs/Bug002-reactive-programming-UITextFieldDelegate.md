**Bug-002: Reactive Programming + UITextFieldDelegate**

_Issue:_
- cannot calling `becomeFirstResponder` or `resignFirstResponder` in `UITextFieldDelegate` whenever apply rxswift or bond to that textField

_Solution:_
- Dirty way: run on main thread
  Using 
  `dispatch_async(dispatch_get_main_queue()) {
      textField.becomeFirstResponder()
  }`
  instead of: 
  `textField.becomeFirstResponder()`
- Cleaner way: observe the `endEditing` event
  RxSwift:
  `usernameOutlet.rx_controlEvent(.EditingDidEnd)
   .subscribeNext { [weak self] _ in
          self?.passwordOutlet.becomeFirstResponder()
   }
   .addDisposableTo(disposeBag)`
  Bond:
  _will do it later_

_Issue in rxswift repository:_ [RxSwift Issue](https://github.com/ReactiveX/RxSwift/issues/392)
