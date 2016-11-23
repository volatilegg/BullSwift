**Bug009: KVO exception - User Defined Runtime Attribites**

_Issue:_
- User get random crashed bug, which cannot catch on xcode
- The exception's only show up when you put the debugger for `All exception`

_Solution:_
- Put a debugger for `All Exception`
- Detect the smelly code line(s), wrap a `do/catch` block around it and you got the error
- Unselect all the `keyPath` that cause crashed
http://stackoverflow.com/questions/20180456/how-can-i-remove-user-defined-runtime-attributes-in-xcode-and-what-are-they
![l4jcc](https://cloud.githubusercontent.com/assets/3374348/20101322/2741b08e-a5ca-11e6-8c23-f176dafeab03.png)

_Reason:_
- some User Defined Runtime Attribites have been automatically added to your nib view, and system sometimes fails to compile them in to KVO -> cause the crashed
![screen shot 2016-11-08 at 15 27 24](https://cloud.githubusercontent.com/assets/3374348/20101071/fd152512-a5c8-11e6-9340-8913084c9a6a.png)
