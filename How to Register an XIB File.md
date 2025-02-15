```swift
import UIKit
class ViewController: UIViewController {
    
    var toBar: TopBar?
    
    @IBOutlet weak var SubView: UIView!  //This is the IBOutLet in the VC where we want to have our XIB View
    
    override func viewDidLoad() {
        super.viewDidLoad()
        topBarFunction()
    }
}

extension ViewController {
    func topBarFunction() {
        if let refrenceForViewTop = Bundle.main.loadNibNamed("TopBar", owner: self, options: nil)?[0] as? TopBar {
            SubView.addSubview(refrenceForViewTop)
            refrenceForViewTop.frame.size.height = SubView.frame.size.height
            refrenceForViewTop.frame.size.width = SubView.frame.size.width
            topBar = refrenceForViewTop
            topBar?.title.text = "Home"
            
        }
    }
}
```
