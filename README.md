# Xcode10-Demo

At WWDC2018, Apple announced Xcode 10 with some great new features, this is a repository to demonstrate some of the features. 

This repository linked to the blog post explaining all features in details. Read 
https://medium.com/xcblog/wwdc18-xcode-10-in-action-f56e14c62d79

##USAGE

##### Paralllel Testing 

Once we have Xcode 10 installed. Clone this repo and execute XCUITest in parallel. 

             $ git clone https://github.com/Shashikant86/Xcode10-Demo
             $ cd Xcode10-Demo
             $ xcodebuild -project Xcode10-Demo.xcodeproj/ -scheme Xcode10-Demo -destination 'platform=iOS Simulator,OS=12.0,name=iPhone X' clean build test CODE_SIGN_IDENTITY="" CODE_SIGNING_REQUIRED=NO -parallel-testing-worker-count 2


Now tests will run in 2 different simulator clones 


### ISSUE

There is issue when tests run in 4 or more simulators. One of the test fails wit early exit error. To reproduce run this 

          $ xcodebuild -project Xcode10-Demo.xcodeproj/ -scheme Xcode10-Demo -destination 'platform=iOS Simulator,OS=12.0,name=iPhone X' clean build test CODE_SIGN_IDENTITY="" CODE_SIGNING_REQUIRED=NO -parallel-testing-worker-count 8
