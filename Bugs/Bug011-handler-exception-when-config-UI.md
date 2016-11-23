**Bug011: Exception when config UI**

_Issue:_
- Getting warning message when config UI: "This application is modifying the autolayout engine from a background thread, which can lead to engine corruption and weird crashes". Warning message came from `All exception` break point

_Solution:_
- put the config UI part in 
```swift
DispatchQueue.main.async {
    // UI code here
}
```

_Reference:_ 
- http://stackoverflow.com/questions/31951704/this-application-is-modifying-the-autolayout-engine-from-a-background-thread-wh

_Reason:_
- UI config code wasn't on main thread - which it should always be 
