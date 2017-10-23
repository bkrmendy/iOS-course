#  View Controllerek, Table View

### Mitől tud a Table View még 1000 cella esetén is gyors lenni?
Mert csak annyi TableViewCell objektum van a memóriában, ahány tényleg látszik a képernyőn. (Plusz alatta és felette 1-2 a görgetés miatt.)

### Sorolj fel 3 rendszer View Controllert!
* UIImagePickerController - kép kiválasztása
* MFMailComposeViewController - e-mail írás
* MFMessageComposeViewController - üzenetírás
* CNContactPickerViewController - kapcsolat kiválasztása
* CNContactViewController - kapcsolat kiválasztása
* CNContactPicker - kapcsolat kiválasztása
* AVPlayerViewController - Videólejátszás

### Delegáció - delegate protokoll
Egy objektum (delegáló) bizonyos feladatokat átruház egy másik objektumra (delegált)

Implementáció: 👌🏼
1. A delegáltnak meg kell valósítania egy protokollt  (pl. UIApplicationDelegate)
2. A delegáló egy referenciát tárol a delegáltra (kompozíció), ezen keresztül hívja meg a delegált metódusokat
* Flexibilis, a protokollt bármilyen osztály megvalósíthatja, gyakori minta Cocoa Touch-ban

### Mire való a UITableViewDataSource és ki az?
Egy protocol, amelyet implementáló ViewController szolgáltatja adott Table View celláit kitöltő információt (általában egy tömb/lista).

### Mi az a Container View Controller? Sorolj fel 3 beépített típust!
Olyan view controller, ami nem egy view--hierarchiát hanem egy vagy több view controllert tartalmaz

Például:
* Split View Controller
* Navigation View Controller
* Tab Bar Controller

