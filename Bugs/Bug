Bug012: NSTimer handler

_Issue_:
Timer is invalidated when its scheduled function is in action. This would lead to some side effects when cleanup codes (codes run after timer is invalided) take no effect because they are preempted.

Example: 

```objective-c
NSInteger a = 0;
NSTimer* timer = [NSTimer scheduledTimerWithTimeInterval:1.0f repeats:false block:^(NSTimer * _Nonnull timer) {
    a = a +1;
    }];
[timer invalidate];
timer = nil;
a=0;
```
Result : a = 0 OR a = 1;


_Reasons_:

**Case 1**: If timer is stopped at 4.9s, it is very likely that the action block is completed already and cleanup codes will take effect. 
Reason: The action block has no chance to execute anymore. 
Result: a = 0;

**Case 2**: If timer is stopped at a really small interval after scheduled function runs, say 5.0000001s, there is chance that the cleanup codes will be interrupted.
Reason: The action block is in the middle of its execution and will eventually finish its run even if the timer is invalidated.
Hence, the cleanup codes may or may not be interrupted, depends on how the action block acts.
Result: a = 0 (if action block is finished BEFORE invalidation) OR a = 1 (if action block is finished AFTER invalidation).

_Remember_:

No specific solution is found yet. Best practice is to avoid putting complicated or non-threadsafe codes inside scheduled function.
