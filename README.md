# EventManager

[![CI Status](http://img.shields.io/travis/acct<blob>=<NULL>/EventManager.svg?style=flat)](https://travis-ci.org/acct<blob>=<NULL>/EventManager)
[![Version](https://img.shields.io/cocoapods/v/EventManager.svg?style=flat)](http://cocoapods.org/pods/EventManager)
[![License](https://img.shields.io/cocoapods/l/EventManager.svg?style=flat)](http://cocoapods.org/pods/EventManager)
[![Platform](https://img.shields.io/cocoapods/p/EventManager.svg?style=flat)](http://cocoapods.org/pods/EventManager)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

Inside AppDelegate.swift
```swfit
let Events = EventManager()
```
Then add the following inside your view controllers ViewDidLoad or any other init function
```swift
Events.listenTo(eventName: "synchronizeAccountDataEvent", action: self.synchronizeAccountData)
```
After you can push to the controller using this:
```swift
Events.trigger(eventName: "synchronizeAccountDataEvent")
```
Inside the listener function then:
```swift
    /// Photo uploaded
    func synchronizeAccountData (information:Any?)
    {
        if let mongoId = information as? String
        {
            print("Uploaded account id: " + mongoId)
        }
    }
```

## Requirements

## Installation

EventManager is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "EventManager"
```

## Author

Fortify Communications Inc, andrei@fortify.pro

## License

EventManager is available under the MIT license. See the LICENSE file for more info.
