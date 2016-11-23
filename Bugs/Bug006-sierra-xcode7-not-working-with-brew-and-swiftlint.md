**Bug-006: Sierra + Xcode 7 + Brew + Swiftlint fucked up**

_Issue:_
- Cannot install swiftlint via brew on sierra with xcode 7.3.1 default

_Solution:_
- Set xcode 8 by default, using `brew install --HEAD swiftlint` to install

_More details:_
https://github.com/realm/SwiftLint/issues/815