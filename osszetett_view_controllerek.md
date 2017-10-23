#  Összetett View Controllerek, Navigáció

### Milyen View Controller típusokat ismersz? Mire valók?
Content View Controller: nézet-hierarchiát tárol

Container View Controller: Más View Controllereket tárol

### Mire jó az unwind segue? Hogyan hozható létre?
Egy korábbi segue visszacsatolása; Interface Builder-ből

### Milyen különbségek vannak a XIB és a Storyboard között?
*IB: egy view controller, SB: több View Controllert is tartalmazhat, egymással való viszonyaik definiálhatóak, table view cuccokat lehet állítgatni benne

### Tab Bar Controller property-jei
* selectedViewController
* viewControllers
* delegate
* customizableVIewControllers

### Milyen elemekből áll a Navigation Bar? Hogy lehet ezeket beállítani?
* vissza gomb - `navigationBar.backItem`
* title - `navigationBar.topItem.title` vagy `viewController.title`, ha be van ágyazva a ViewController NavigationControllerbe
* opcionális jobb felső sarok gomb

### Milyen adaptív segue-ket ismersz?
* Show
* Show detail
* Present Modally
* Present as Popover

### Melyik mire való?
Push, Modal, Popover (resp.)

### Hogy lehet Segue-t kódból végrehajtani?
`func performSegue(withIdentifier: sender:)`
### Hogy lehet kódból a cél VC-hez hozzáférni?
```swift
if let targetVC = segue.destination as? SomeViewController {
    //code
}

guard let targetVC = segue.destination as? SomeViewController else {
    //abort
}
```
### Mire való a navigation controller?
Verem-szerű navigációra (azaz csak lineárisan tudok fel-le mozogni a hierarhiában)

### Milyen megoldásokat ismersz View Controller megjelenítésére illetve visszalépésre Navigation Controller használata esetén?
Megjelenítés
```swift
navigationController.pushViewController(viewController: UIViewController>, animated: Bool)
```
Visszalépés
``` swift
navigationController.popViewController(animated: Bool) // egyet vissza a hierarchiaban
navigationController.popToViewController(viewController: UIViewController, animated: Bool) // egy adott ViewControllerhez vissza
navigationController.popToRootViewController(animated: Bool) // a roothoz vissza
```
### Mit jelent a modális megjelenítés?
Kb. felugró view controller, a jelenleg látható hierarchia fölé

### Milyen módszereket ismersz View Controller modális megjelenítésére, majd a visszalépésre?
Megjelenítés:
* Storyboard-ból beállítva
* `present(viewControllerToPresent, animated: true, completion: nil)`

Dismiss:
* `dismiss(animated: true, completion: nil)`
