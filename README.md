# SmoothPicker
[![Version](https://img.shields.io/cocoapods/v/SmoothPicker.svg?style=flat)](https://cocoapods.org/pods/SmoothPicker)
[![License](https://img.shields.io/cocoapods/l/SmoothPicker.svg?style=flat)](https://cocoapods.org/pods/SmoothPicker)
[![Platform](https://img.shields.io/cocoapods/p/SmoothPicker.svg?style=flat)](https://cocoapods.org/pods/SmoothPicker)

A Customized Component for creating a horizontal picker with custom styles 

<br />
![Alt Text](https://media.giphy.com/media/aM98ApTjIK5iprKXII/giphy.gif)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

## Installation

SmoothPicker is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'SmoothPicker'
```

## Author

ahmed.nasser2310@gmail.com, ahmed.nasser2310@gmail.com

## License

SmoothPicker is available under the MIT license. See the LICENSE file for more info.
# SmoothPicker

Createe the view either by storyboard or by frame 
<br />

```
class ViewController{
   @IBOutlet weak var pickerView: SmoothPickerView!
    
    var i = 0
    var views = [UIView]()
    override func viewDidLoad() {
        super.viewDidLoad()
        for _ in 1..<11 {
            let view = UIView(frame: CGRect(x: 0, y: 0, width: 50, height: 50))
            view.backgroundColor = #colorLiteral(red: 0.8039215803, green: 0.8039215803, blue: 0.8039215803, alpha: 1)
            views.append(view)
        }
    }
    func didSelectIndex(index: Int) {
        print("SelectedIndex \(index)")
    }   
    func numberOfItems() -> Int {
        return 10
    }
    
    func itemForIndex(index: Int) -> UIView {
        return views[index]
    }
    @IBAction func navigateNext(_ sender: Any) {
        pickerView.navigate(direction: .next)
    }
    @IBAction func navigatePervious(_ sender: Any) {
        pickerView.navigate(direction: .pervious)
    }
}
```

## Data Source
```
func numberOfItems() -> Int
func itemForIndex(index:Int) -> UIView // retrun the view per item just make sure it can calculate it's frame correctly 
```
## Delegate
```
func didSelectIndex(index:Int)
```
## Customization
```
public enum SelectionStyle {
    case scale
    case colored
}
SmoothPickerConfiguration.setSelectionStyle(selectionStyle: .scale) // scale is deafult default 
static func setColors(selectedColor:UIColor,dimmedColor:UIColor) // for colred selection style black and gray is default
```
## Authors

* **Ahmed Nasser** - [AvaVaas](https://github.com/AvaVaas)
