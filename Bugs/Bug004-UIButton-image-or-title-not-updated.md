**Bug-004: UIButton image or title not updated**

_Issue:_
- using `button.imageView.image = chosenImage` not working

_Solution:_
- using `button.setImage` || `button.setTitle` instead of setting the value directly
