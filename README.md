# extensions-kit [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

[![Platforms](https://img.shields.io/badge/platforms-iOS%20%7C%20macOS%20%7C%20tvOS%20%7C%20watchOS-yellow.svg)]()
[![Language](https://img.shields.io/badge/language-Swift-orange.svg)]()
[![Coverage](https://img.shields.io/badge/coverage-32%2C65%25-red.svg)]()
[![Documentation](https://img.shields.io/badge/docs-100%25-magenta.svg)]()
[![CocoaPod](https://img.shields.io/badge/pod-1.7.0-lightblue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg)]()

**Last Update: 19/December/2018.**

![](logo-extensions_kit.png)

### If you like the project, please give it a star ⭐ It will show the creator your appreciation and help others to discover the repo.

# ✍️ About

📦 Collection of Swift extensions(+ custom types) for various use cases. The kit contains **`175`** extensions + **`22`** custom types.

# 🏗 Installation
## CocoaPods
`extensions-kit` is availabe via `CocoaPods`

```
pod 'extensions-kit', '~> 1.7.0' 
```
## Manual
You can always use `copy-paste` the sources method 😄. Or you can compile the framework and include it with your project.

# 🍱 Categories
List of categories for convenient navigation. The `numbers` represent total number of extensions for a given category + custom types. Each extension file may contain a number of extensions, grouped by a category.

- [AppKit - 1](#appkit)
- [AVFoundation - 1](#avfoundation) 
- [Core Animation - 1](#core-animation)
- [Core Graphics - 16](#core-graphics)
- [Core Image - 1](#core-image)
- [Foundation - 95](#foundation)
- [UIKit - 54](#uikit)
- [SpriteKit - 11](#spritekit)
- [SceneKit - 1](#scenekit)
- [Grand Central Dispatch - 5](#grapnd-central-dispatch)
- [WebKit - 1](#webkit)
- [PhotoKit - 1](#photokit)


# 📚 List of Extensions
All the extensions are split into separete `groups` each of which represents a separete `SDK framework`. 

## AppKit

## NSBezierPath
- [NSBezierPath+cgPath](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/AppKit/NSBezierPath%2BcgPath.swift) - adds missing `cgPath` property that converts `self` (port of similar functionality from `iOS`)

## AVFoundation
#### [AVCaptureDevice+ToggleFlash](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/AVFoundation/AVCaptureDevice%2BToggleFlash.swift)
Adds support for easy flashlight management:

```swift
AVCaptureDevice.toggleFlashlight(with: .max)
```

## Core Animation

### CAAnimation
#### [CAAnimation+PatternReplicator](/extensions-kit/Extensions/CoreAnimation/CAAnimation/CAAnimation%2BPatternReplicator.swift)
Creates a pattern-based, wavy animation for the specified image, layer size and other properties:

```swift
CAAnimation.patternReplocator(with: UIImage("image"), size: CGSize(width: 600, height: 600), targetLayer: drawerView.layer)
```

## Core Graphics

### CGSize 
#### [CGSize+Operators](/extensions-kit/Extensions/CoreGraphics/CGSize/CGSize%2BOperators.swift)
Various mathematical operators such as `+`, `-`, `*`, `/` for convenience:

```swift
CGSize(width: 10, height: 20) + CGSize(width: 25.4, height: 23.6)
CGSize(width: 10, height: 20) - CGSize(width: 25.4, height: 23.6)
CGSize(width: 10, height: 20) * CGSize(width: 25.4, height: 23.6)
CGSize(width: 10, height: 20) / CGSize(width: 25.4, height: 23.6)
```

### CGPoint
#### [CGPoint+Operators](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreGraphics/CGPoint/CGPoint%2BOperators.swift)
Various mathematical operators such as `+`, `-`, `*`, `/`, `lerp` etc.:

```swift
var origin: CGPoint = .zero
let addPoint = origin + CGPoint(x: 10, y: 3)
origin += CGPoint(x: 12, y: 5)
let subPoint = origin - CGPoint(x: 12, y: 5)
        
let interpolatedPoint = CGPoint.lerp(start: pointOne, end: pointTwo, t: 2)
```

#### [CGPoint+Utils](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreGraphics/CGPoint/CGPoint%2BUtils.swift) 
Missing mathematical utilities such as `normalized`, `lenght`, `distanceTo` and `angle`:

```swift
let point = CGPoint(x: 3, y: 5)
let _ = point.length()
let _ = point.angle
let _ = point.normalized()
let distanceBetweenTwoPoints = point.distanceTo(anotherPoint)
let _ = point.lengthSquared()
```

### CGRect

#### [CGRect+Scale](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreGraphics/CGRect/CGRect%2BScale.swift)
Scales `self` to the specified size:

```swift
let rect = CGRect(origin: .zero, size: CGSize(width: 100, height:
            200))
let newSize = rect.scaled(to: targetSize)
```

#### [CGRect+Corners](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreGraphics/CGRect/CGRect%2BCorners.swift)
Adds properties for `topLeft`, `topRight`, `bottomLeft` and `bottomRight` points:

```swift
let rect = CGRect(origin: .zero, size: CGSize(width: 100, height:
            200))
rect.topLeft
rect.topRight
rect.bottomLeft
rect.bottomRight
````

#### [CGRect+Mid](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreGraphics/CGRect/CGRect%2BMid.swift)
Adds property for `mid` point of `self`:

```swift
let rect = CGRect(origin: .zero, size: CGSize(width: 100, height:
            200))
rect.mid
```

#### [CGRect+AspectFit](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreGraphics/CGRect/CGRect%2BAspectFit.swift)
Adds `aspectFit(inRect: CGRect) -> CGRect` method that scales `self` to fit the specified `CGRect`:

```swift
let rect = CGRect(origin: .zero, size: CGSize(width: 100, height:
            200))
rect.aspectFit(inRect: targetRect)
```

### CGFloat
#### [CGFloat+Rounded](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreGraphics/CGFloat/CGFloat%2BRounded.swift)
Rounds `self` to the specified decimal places:

```swift
let val: CGFloat = 4.32
let roundedVal = val.rounded(toPlaces: 1) // roundedVal holds `4.3`
```

## CoreImage

### New Filters
- [HighlightFilter](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/CoreImage/Filters/HighlightFilter.swift) - filter is originally designed for highlighting 3D objects but can be used to add this effect to images and sprites

## Foundation

### Custom Structures
- [Variable](
https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/CustomStructures/Variable.swift) - lightweight bindable data type that allows to get on update notifications for a given value. Can be used with `MVVM` or any another architectural pattern to replace the need for 3rd party, heavyweight binding framework.

### Functions 
- [FunctionalComposition](/extensions-kit/Extensions/Foundation/Functions/FunctionalComposition.swift) - is a functions that implements `Functional Composition` concept which allows to combine multiple functions and chain them together, in order to transform data. Consider the following construction: (`doubleNumbers` ->> `squareNumbers` ->> `convertToStringArray`)(array) which returns a processed array by linearly composing the functions (rather that nesting the function calls). Also the extension includes the `reversed` operator that composes functions in reversed order.

### Data Structures
- [BuilderProtocol](/extensions-kit/Extensions/Foundation/DataStructures/Builder/BuilderProtocol.swift) - Allows `AnyObject` to be extended with chainable initialization methods by using Keypath feature. Please note that the extension works only since `Swift 4.0`
- [Lens](/extensions-kit/Extensions/Foundation/DataStructures/FunctionalLenses/Lens.swift) - `Lens` is an implementation of `Functional Lenses` concept that allows to safely modify immutable `structs` and provides fundamental tools to work with complex data structures (see `UnitTests`)
- [ObjectPool](/extensions-kit/Extensions/Foundation/DataStructures/ObjectPool/ObjectPool.swift) - thread-safe implementation of `ObjectPool` design pattern
- [Observer](/extensions-kit/Extensions/Foundation/DataStructures/Observer/) - thread-safe implementation of `Observer` design pattern (don't confuse with NotiifcationCenter - it's an implementation of `Publish-Subscribe` pattern)
- [MulticastDelegation](/extensions-kit//Extensions/Foundation/DataStructures/MulticastDelegation/MulticastDelegation.swift) - non thread-safe implementation of `MulticastDelegation` design pattern
- [Stack](/extensions-kit//Extensions/Foundation/DataStructures/Stack/Stack.swift) - is an implementation of `Stack` data structure
- [Queue](/extensions-kit//Extensions/Foundation/DataStructures/Queue/Queue.swift) - is an implementation of `Queue` data structure
- [ProrityQueue](/extensions-kit/Extensions/Foundation/DataStructures/PriorityQueue/PriorityQueue.swift) -  is an implementation of `Prority Queue` data structure based on `Heap` data structure
- [Dequeue](/extensions-kit//Extensions/Foundation/DataStructures/Dequeue/Dequeue.swift) - is an implementation of `Dequeue` data structure 
- [LinkedList](/extensions-kit//Extensions/Foundation/DataStructures/LinkedList/LinkedList.swift) - is an implementation of `Linked List` data structure 
- [DoublyLinkedList](/extensions-kit//Extensions/Foundation/DataStructures/DoublyLinkedList/DoublyLinkedList.swift) - is an implementation of `Doubly Linked List` data structure
- [Heap](/extensions-kit//Extensions/Foundation/DataStructures/Heap/Heap.swift) - is an implementation of `Heap` data structure

### Extensions

### Array
- [Array+Filtering](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Array/Array%2BFiltering.swift) - contains a number of methods for filtering in a `functional-style`, has `skip`, `all` and `any` filters
- [Array+Contains](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Array/Array%2BContains.swift) - checks if self contains the specified elements
- [Array+Difference](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Array/Array%2BDifference.swift) - computes differences between self and the input arrays
- [Array+Intersection](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Array/Array%2BIntersection.swift) - computes intersection of self and the input values
- [Array+Union](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Array/Array%2BUnion.swift) - unions self and the input arrays
- [Array+Remove](/extensions-kit/Extensions/Foundation/Array/Array%2BRemove.swift) - a set of methods that remove `Element` form an array by mutating it
- [Array+InsertionSort](/extensions-kit/Extensions/Foundation/Array/Array%2BIntersection.swift) - adds support for `Insertion Sort` algorithm
- [Array+MergeSort](/extensions-kit/Extensions/Foundation/Array/Array%2BMergeSort.swift) - adds support for `Merget Sort` algorithm
- [Array+QuickSortHoareScheme](/extensions-kit/Extensions/Foundation/Array/Array%2BQuickSortHoareScheme.swift) - adds support for `Quick Sort` algorithms using `Hoare's` partitioning scheme 
- [Array+QuickSortLomutoScheme](/extensions-kit/Extensions/Foundation/Array/Array%2BQuickSortLomutoScheme.swift) - adds support for `Quick Sort` algorithm using `Lomuto's` partitioning scheme 
- [Array+BubbleSort](/extensions-kit/Extensions/Foundation/Array/Array%2BBubbleSort.swift) - adds support for `Bubble Sort` algorithm
- [Array+ShellSort](/extensions-kit/Extensions/Foundation/Array/Array%2BShellSort.swift) - adds support for `Shell Sort` algorithm
- [Array+RadixSort](/extensions-kit/Extensions/Foundation/Array/Array%2BRadixSort.swift) - adds support for `Radix Sort` algoritm

### Bool
- [Bool+Int](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Bool/Bool%2BInt.swift) - adds a property that returns `Int` representation of `self`
- [Bool+Random](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Bool/Bool%2BRandom.swift) - adds a random property for `self`

### ClosedRange
- [ClosedRange+Random](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/ClosedRange/ClosedRange%2BRandom.swift) - adds a property that generates a random `Int` with respect to `self`

### Collection 
- [Collection+ParallelIteration](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Collection/Collection%2BParallelIteration.swift) - adds `parallelForEach` method 
- [Collection+RandomItem](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Collection/Collection%2BRandomItem.swift) - adds a property that returns a random element from `self`
- [Collection+Sum&Average](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Collection/Collection%2BSum%26Average.swift) - adds two properties for `sum` and `average` with the corresponding functionality
- [Collection+SafeSubscript](/extensions-kit/Extensions/Foundation/Collection/Collection%2BSafeSubscript.swift) - safely checks whether the collection is able to retreive an element for the given Index, otherwise it will return nil

### RandomAccessCollection
- [RandomAccessCollection+BinarySearch](/extensions-kit/Extensions/Foundation/RandomAccessCollection/RandomAccessCollection%2BBinarySearch.swift) - implementation of `Binary Search` algorithm 

### Dictionary
- [Dictionary+GetOrAddValue](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Dictionary/Dictionary%2BGetOrAddValue.swift) - parses `self` as `JSON` to `Data` or `String`
- [Dictionary+JSON](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Dictionary/Dictionary%2BJSON.swift) - checks for a value for a given key or creates a new key/value pair if none was found
- [Dictionary+ConvenienceWrappers](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Dictionary/Dictionary%2BConvenienceWrappers.swift) - adds wrappers around common operations such as `has(key: )->Bool` and `each(: (Key, Value)->())`
- [Dictionary+Difference](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Dictionary/Dictionary%2BDifference.swift) - computes differences between self and the input dictionaries 
- [Dictionary+Intersection](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Dictionary/Dictionary%2BIntersection.swift) - computes intersection of self and the input Dictionaries
- [Dictionary+Map](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Dictionary/Dictionary%2BMap.swift) - custom mapping function
- [Dictionary+Union](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Dictionary/Dictionary%2BUnion.swift) - unions self and the input dictionaries

### Double
- [Double+Rounded](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Double/Double%2BRounded.swift) - rounds `self` to decimal places value
- [Double+CurrencyShorcuts](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Double/Double%2BCurrencyShortcuts.swift) - adds several commonly used currency shortcuts as properties

### Date
- [Date+FirstLast](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Date/Date%2BFirstLast.swift) - adds a number of properties that allow to quickly access: `first day of a week`, `start of a day`, `end of a day` and a `number of days in a month`
- [Date+PreviousNext](/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Date/Date%2BPreviousNext.swift) - adds properties that allow to get access to the `previous` and `next` days

### Float 
- [Float+Rounded](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Float/Float%2BRounded.swift) - rounds `self` to decimal places value

### Int
- [Int+Clamp](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Int/Int%2BClamp.swift) - clamps `self` into a range that can be described using `ClosedRange` or two separate properties
- [Int+Digits](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Int/Int%2BDigits.swift) - adds `digitCount` property that contains the number of digits for `self`
- [Int+EvenOdd](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/Foundation/Int/Int%2BEvenOdd.swift) - checks whether `self` is even or if it's odd
- [Int+Factorial](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/Foundation/Int/Int%2BFactorial.swift) - computes *factorial* of `self`
- [Int+Power](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/Foundation/Int/Int%2BPower.swift) - operator that performs `exponentiation` matematical operation, where left number is the *base* and the right one is the *exponent*
- [Int+Random](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/Foundation/Int/Int%2BRandom.swift) - generates pseudo-random number in a range that can be specified as `ClosedRange` or two separate `Int` properties
- [Int+Roman](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/Foundation/Int/Int%2BRoman.swift) - converts `self` into *Roman* number (as `String`)
- [Int+DecimalToBinary](/extensions-kit/Extensions/Foundation/Int/Int%2BDecimalToBinary.swift) - allows to convert `decimal` number to `binary` format and vice versa 

### OptionSet
- [OptionSet+Operations](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/OptionSet/OptionSet%2BOperations.swift) - adds support for in-place `insert` and `remove` operations

### MutableCollection 
- [MutableCollection+Shuffle](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/Foundation/MutableCollection/MutableCollection%2BShuffle.swift) - in-place shuffling of `self`

### Sequence  
- [Sequence+Shuffle](/extensions-kit/Extensions/Foundation/Sequence/Sequence%2BShuffle.swift) - shuffles the elements of `self`
- [Sequence+Count](/extensions-kit/Extensions/Foundation/Sequence/Sequence%2BCount.swift) - counts the number of occurrences of a logical expression
- [Sequence+DuplicatesRemoved](
https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/Sequence/Sequence%2BDuplicatesRemoved.swift) - removes the duplicate elements and returns the new Sequence without duplicates if any

### String
- [String+Subscript](/extensions-kit/Extensions/Foundation/String/String%2BSubscript.swift) - adds conformances to `CoutableClosedRange`, `CountableRange`, `PartialRangeThrough` and `PartialRangeFrom` protocols support in a form of subscripts
- [String+Digits](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/String/String%2BDigits.swift) - combines decimal digits into a single `String` property
- [String+FormattedDate](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/String/String%2BFormattedDate.swift) - creates a `Date` instance from `self` based in the specified format
- [String+IndexOf](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/String/String%2BIndexOf.swift) - finds the first occurence for a given `String`
- [String+Base64](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/String/String%2BBase64.swift) - encodes/decodes `self` to `Base64` encoding
- [String+Validation](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/Foundation/String/String%2BValidation.swift) - contains a number of extensions for validating `String` based on the following: `isAlphanumeric`, `hasLetters`, `hasNumbers`, `isEmail`, `isAlphabetic`

## UIKit

### Badge
- [Badge](/extensions-kit/Extensions/UIKit/Badge/Badge.swift) - a custom type, wrapper 
badge app icon `API` that simplifies development

### UIScreen
- [UIScreen+InterfaceOrientation](/extensions-kit/Extensions/UIKit/UIScreen/UIScreen%2BInterfaceOrientation.swift) - interace orientation for the current `UIScreen`

### UIApplication
- [UIApplication+SafeAreas](/extensions-kit/Extensions/UIKit/UIApplication/UIApplication%2BSafeAreas.swift) - contains extensions that allow to get numerical representations of `top` and `bottom` safe areas

### NSLayoutConstraint
- [NSLayoutConstraint+Animation](/extensions-kit/Extensions/UIKit/NSLayoutConstraint/NSLayoutConstraint%2BAnimation.swift) - allows a constraint to be animated when `animated` flag is a set to `true` (default is `false`)
- [NSLayoutConstraint+Activation](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/UIKit/NSLayoutConstraint%2BActivation/NSLayoutConstraint%2BActivation.swift) - adds convenience methods for *setting* and *activating* layout priorities

### UIView
- [UIView+CACorners](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/UIKit/UIView/UIView%2BCACorners.swift) - convenience extension for setting and getting round corners
- [UIView+BezierRoundedCorners](/extensions-kit/Extensions/UIKit/UIView/UIView%2BBezierRoundedCorners.swift) - yet another extension for rounding corners
- [UIView+HuggingPriority](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/UIKit/UIView/UIView%2BHuggingPriority.swift) - convenience wrappers that simplify inerfaces for *setContentHuggingPriority* and *setContentCompressionResistancePriority* methods
- [UIView+Screenshot](/extensions-kit/Extensions/UIKit/UIView/UIView%2BScreenshot.swift) - allows to take a screenshot of self
- [UIView+Constraints](/extensions-kit/Extensions/UIKit/UIView/UIView%2BConstraints.swift) - adds convenience auto-layout methods that allow to `pin`, `add`, get `height` & `width` and to get all the constrains for a particular `UIView`
- [UIView+LayoutAnimation](/extensions-kit/Extensions/UIKit/UIView/UIView%2BLayoutAnimation.swift) - adds animation extensions that operate on layout constraints

### UIColor
- [UIColor+ColorComponents](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/UIKit/UIColor/UIColor%2BColorComponents.swift) - adds support for missing color components properties such as `rgba`, `hsba` and `grayscale`

### UICollectionView
- [UICollectionView+CustomCellRegistration](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UICollectionView/UICollectionView%2BCustomCellRegistration.swift) - registers custom `UICollectionViewCell` for a `UICollectionView` instance. `UICollectionViewCell` needs to be located in current Bundle
- [UICollectionView+ScrollingUtils](/extensions-kit/Extensions/UIKit/UICollectionView/UICollectionView%2BScrollingUtils.swift) - adds methods that allow to programmatically scroll to the `top`, `bottom` or to the specified `index path` of a table view
- [UICollectionView+Safety](/extensions-kit/Extensions/UIKit/UICollectionView/UICollectionView%2BSafety.swift) - adds validation utils 
- [UICollectionView+Operations](/extensions-kit/Extensions/UIKit/UICollectionView/UICollectionView%2BOperations.swift) - convenience `reload`, `delete` and `insert` operations for collections of item indices

### UITableView
- [UITableView+FooterHeaderUtils](/extensions-kit/Extensions/UIKit/UITableView/UITableView%2BFooterHeaderUtils.swift) - the extension adds convenience helpers for working with `Footer` and `Header` views
- [UITableView+ScrollingUtils](/extensions-kit/Extensions/UIKit/UITableView/UITableView%2BScrollingUtils.swift) -  adds methods that allow to programmatically scroll to the `top`, `bottom` or to the specified `index path` of a table view
- [UITableView+Safety](/extensions-kit/Extensions/UIKit/UITableView/UITableView%2BSafety.swift) - adds validation utils 

### UIImage
- [UIImage+ImageFromUIView](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UIImage/UIImage%2BImageFromUIView.swift) - renders `UIView` to `UIImage`
- [UIImage+LandscapeCameraOrientationFix](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UIImage/UIImage%2BLandscapeCameraOrientationFix.swift) - fixes image orientation for cases when the image was captured using `AVFoundation` in *landscape interface orientation*
- [UIImage+RawOrientation](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UIImage/UIImage%2BRawOrientation.swift) - raw image orientation (from `UIImageOrientation` to `Int32`) 
- [UIImage+Resize](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UIImage/UIImage%2BResize.swift) - class-level extension that allows to resize input image based on expected image *width* or/and *height*
- [UIImage+SolidColor](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UIImage/UIImage%2BSolidColor.swift) - create a `UIImage` from the *color data* and *size*
- [UIImage+Inverted](https://github.com/jVirus/extensions-kit/blob/master/extensions-kit/Extensions/UIKit/UIImage/UIImage%2BInverted.swift) - adds a property that returns an *inverted* copy of `self`

### UIImageView
- [UIImageView+DownloadFromURL](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UIImageView/UIImageView%2BDownloadFromURL.swift) - adds a convenience method for downloading and parsing `UIImage` with the specified `URL`
- [UIImageView+Masking](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/UIKit/UIImageView/UIImageView%2BMasking.swift) - masks a given `UIImage` with the target image size

### UIViewController
- [UIViewController+ChildViewControllers](/extensions-kit/Extensions/UIKit/UIViewController/UIViewController%2BChildViewControllers.swift) - addds convenience methods for `adding` and `removing` child view controllers
- [UIViewController+Storyboard](/extensions-kit/Extensions/UIKit/UIViewController/UIViewController%2BStoryboard.swift) - instantiates a `UIViewController` instance from a `Storyboard` using the `UIViewController's` name as a reference name of the `Storyboard` file. Used in cases when `Coordinator` or `Flow` design patterns need to be implemented

## SpriteKit
- [SKTimingFunction](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/SpriteKit/SKTimingFunction.swift) - adds **36(!)** different timing functions 

### SKEmitterNode
- [SKEmitterNode+AdvanceSimulation](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/SpriteKit/SKEmitterNode/SKEmitterNode%2BAdvanceSimulation.swift) - safely advance the particle simulation for a given `TimeInterval`

### SKSpriteNode
- [SKSpriteNode+GIF](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/SpriteKit/SKSpriteNode/SKSpriteNode%2BGIF.swift) - adds support for uploading and playing `GIFs` from local files

### SKScene
- [SKScene+SerialSpriteLoading](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/SpriteKit/SKScene/SKScene%2BSerialSpriteLoading.swift) - uploads a set of scene graph nodes with a specific pattern, useful when a scene contains a lot of nodes, but just a specific subset needs to be processed or accessed
- [SKScene+ReferenceNodeFix](/extensions-kit/Extensions/SpriteKit/SKScene/SKScene%2BReferenceNodeFix.swift) - a small fix that resolves the default behavior for nodes that were referenced from differnet .sks files. The thing is that they do not launch their animations by default, so this small `hack` fixes this issue

### SKTexture
- [SKTexture+LinearGradient](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/SpriteKit/SKTexture/SKTexture%2BLinearGradient.swift) - adds a convenience initializer that generates a `gradient texture` for the specified *size*, *start* and *end* colors

### SKTextureAtlas
- [SKTextureAtlas+FramesLoader](https://github.com/jVirus/ios-extensions/blob/master/extensions-kit/Extensions/SpriteKit/SKTextureAtlas/SKTextureAtlas%2BFramesLoader.swift) - uploads an animation sequence from a texture atlas and returns an array of textures that can be futher used

## SceneKit
- [SCNVector3+Operators](/extensions-kit/Extensions/SceneKit/SCNVector3%2BOperators.swift) - adds support for various mathematical operators for `SCNVector3` type

## Grand Central Dispatch

### Extensions
- [DispatchQueue+DispatchOnce](/extensions-kit/Extensions/Grand%20Central%20Dispatch/DispatchQueue%2BDispatchOnce.swift) - adds support for `class` method that executes block of code only once a.k.a. `DispatchOnce` before `Swift 3.0`

### Custom Types
- [Atomic](/extensions-kit/Extensions/Grand%20Central%20Dispatch/Atomics/Atomic.swift) - guarantees that a valid value will be returned when accessing such property by using multiple threads
- [Mutex](/extensions-kit/Extensions/Grand%20Central%20Dispatch/Locks/Mutex.swift) - used to proptect shared resources. A mutex is owned by the task that takes it. In a given region of code only one thread is active
- [ReadWriteLock](/extensions-kit/Extensions/Grand%20Central%20Dispatch/Locks/ReadWriteLock.swift) - a synchronization primitive that solves one of the readers–writers problems
- [UnfairLock](/extensions-kit/Extensions/Grand%20Central%20Dispatch/Locks/UnfairLock.swift) - a lock which causes a thread trying to acquire it to simply wait in a loop ("spin") while repeatedly checking if the lock is available

## WebKit

### WKWebView
- [WKWebView+Load](/extensions-kit/Extensions/WebKit/WKWebView/WKWebView%2BLoad.swift) - adds support for navigating to the requested `URL` using `String`

## PhotoKit

### PHAsset
- [PHAsset+URL](/extensions-kit/Extensions/PhotoKit/PHAsset/PHAsset%2BURL.swift) - provides possibility to get `URL` for image and video media types

# 🙋‍♀️🙋‍♂️Contributing 
- There is just one main rule for contributors - **please include your extensions in separete files**. It's important since such extension can be more easily referenced and reused.
- The other `soft` rule is - please include `unit tests` with your extensions. 

# 👨‍💻 Author 
[Astemir Eleev](https://github.com/jVirus)

# 🔖 Licence
The project is available under [MIT licence](https://github.com/jVirus/extensions-kit/blob/master/LICENSE)
