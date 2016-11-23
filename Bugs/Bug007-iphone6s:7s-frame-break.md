**Bug-007: iPhone 6s subviews frame break**

_Issue:_
- Using storyboard with smaller size storyboard (5/6's sizes)
- Controller subviews has a weird transparent area

_Solution:_
- Using storyboard biggest size you can choose (6plus for now aka 5.5 inches)

_Reasons:_
- The views seems cannot show anything when it came across the border in storyboard
- Really don't know why exactly
