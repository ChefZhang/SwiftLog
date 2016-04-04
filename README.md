# SwiftLog
swift中自定义log


在AppDelegate.swift
写上以下函数,就可以使用以下的log函数


```swift
func CZLog<T>(messsage : T, file : String = __FILE__, funcName : String = __FUNCTION__, lineNum : Int = __LINE__) {
    
    
    #if DEBUG
        
        
        let dateFormatter = NSDateFormatter()
        dateFormatter.locale = NSLocale(localeIdentifier: "en_US_POSIX") //24H
        dateFormatter.dateFormat = "y-MM-dd HH:mm:ss.SSS"

        
        let fileName = (file as NSString).lastPathComponent
        
        print("\(dateFormatter.stringFromDate(NSDate())) [Swift flag | -D DEBUG] [\(fileName): \(lineNum)] :  \(messsage)")
        
    #endif
}
```


![AppDelegate_swift.png](http://upload-images.jianshu.io/upload_images/328309-c049b2334859bf84.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![ViewController_swift.png](http://upload-images.jianshu.io/upload_images/328309-3be22ec96e6e64d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
