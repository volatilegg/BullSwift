**Bug001 - hide/show keyboard with multiple text fields**

_Issue:_
- Dealing with multiple text fields and some become invisible when the keyboard shown

_Solution:_
- URL:
  [Apple documentation](https://developer.apple.com/library/content/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/KeyboardManagement/KeyboardManagement.html)
- Summary  
- [x] Put all text field into one scrollview and scroll to visible text field (`scrollRectToVisible`) when one is activated (detect at `textFieldDidBeginEditing`)
- [x]  scrollView.contentOffset(activeTextField.origin) will scroll to active field position

_Remember:_ 
- dispose keyboard notification at `viewWillDisapear` 
- avoid using contentInset for scrolllView
