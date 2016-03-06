MKHSegmentedControl
==================

Android style segmented control written in swift.  
Fully customisable.  

Demo
----

![alt tag](https://raw.githubusercontent.com/yemeksepeti/YSSegmentedControl/master/demo.gif)

Install
-------

##### Manual

Copy & paste `MKHSegmentedControl.swift` in your project

##### Cocoapods

``` ruby
use_frameworks!
pod 'YSSegmentedControl'
```

Usage
-----

Create `MKHSegmentedControl` with frame and titles.  
You can either use delegation or callback initilization

##### With callback

``` swift
    let segmented = MKHSegmentedControl(
        frame: CGRect(
            x: 0,
            y: 64,
            width: view.frame.size.width,
            height: 44),
        titles: [
            "First",
            "Second",
            "Third"
        ],
        action: {
            control, index in
            println ("segmented did pressed \(index)")
        })

```

##### With delegation

``` swift
    let segmented = MKHSegmentedControl(
        frame: CGRect(
            x: 0,
            y: 64,
            width: view.frame.size.width,
            height: 44),
        titles: [
            "First",
            "Second",
            "Third"
        ])
```

Setup the delegate and you are ready to go !

``` swift
	segmented.delegate = self
```

### MKHSegmentedControlDelegate

``` swift
@objc protocol MKHSegmentedControlDelegate {
    optional func segmentedControlWillPressItemAtIndex (segmentedControl: YSSegmentedControl, index: Int)
    optional func segmentedControlDidPressedItemAtIndex (segmentedControl: YSSegmentedControl, index: Int)
}

```

### MKHSegmentedControlAppearance

``` swift
	struct MKHSegmentedControlAppearance {
	    
	    var backgroundColor: UIColor
	    var selectedBackgroundColor: UIColor
	    
	    var textColor: UIColor
	    var fontUp: UIFont
	    var fontDown: UIFont

	    
	    var selectedTextColor: UIColor
	    var selectedFont: UIFont
	    
	    var bottomLineColor: UIColor
	    var selectorColor: UIColor
	    
	    var bottomLineHeight: CGFloat
	    var selectorHeight: CGFloat
	}
```

The default appearance is

``` swift
   appearance = MKHSegmentedControlAppearance(
       
       backgroundColor: UIColor.clearColor(),
       selectedBackgroundColor: UIColor.clearColor(),
       
       textColor: UIColor.grayColor(),
       fontUp: UIFont.systemFontOfSize(15),
       fontDown: UIFont.systemFontOfSize(15),
       
       selectedTextColor: UIColor.blackColor(),
       selectedFont: UIFont.systemFontOfSize(15),
       
       bottomLineColor: UIColor.blackColor(),
       selectorColor: UIColor.blackColor(),
       
       bottomLineHeight: 0.5,
       selectorHeight: 2)
```

You can change appearance by

``` swift
	segmented.appearance = MKHSegmentedControl (...)

	// or

	segmented.appearance.titleColor = ...
```
