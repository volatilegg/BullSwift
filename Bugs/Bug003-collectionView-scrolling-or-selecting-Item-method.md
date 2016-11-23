**Bug-003: CollectionView scrolling or selecting Item method not working**

_Issue:_
- `selectItemAtIndexPath` not working in `viewWillAppear`

_Solution:_
- using `self.view.layoutIfNeeded()` along on `viewWillAppear`
