**Bug-008: Fatal error when archiving optional Data**

_Issue:_
- Archiving an **Dictionary** [String: String?] to **Data** using `NSKeyedArchiver.archivedData(withRootObject: dictionary)` causes fatal error with message `terminating with uncaught exception ...`

_Solution:_
- Force type dictionary object to [String: Any] or [String: String] solve the problem

_Reason:_
- Wild guess: Optional type in the dictionary object cause the crash. Still investigating 
