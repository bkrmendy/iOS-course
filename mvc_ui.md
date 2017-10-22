#  MVC és UI alapok

### Mi az az ARC?
*A*utomatic *R*eference *C*ounting

A fordító elemzi a forráskódot és beilleszti a memóriakezeléssel kapcsolatos utasításokat (kb. `delete`)

### Mikor kell weak reference-et használni?
Ha el akarjuk kerülni a körkörös referenciákat (pl Player-Weapon példa), és ha "a gyerek továbbélhet a szülő nélkül".

A fordító nem veszi figyelembe a weak ref-et referenciaszámláláskor.

### Miben különbözik az unowned referencia a weak reference-től?
Az unowned referenciák nem optional értékek, mindig kell, hogy értékük legyen, különben crash.

Csak addig létezhet unowned objektum, amíg a szülő is életben van.

### Mikor rajzol a ViewController?
Soha, a View rajzol

### Mi kezeli le az adott View-hoz tartozó eseményeket?
Az adott View ViewController-e (vagy a root ViewController).

### Mi a különbség a XIB és a NIB file között?
A XIB XML alapú file, szerkeszthető Xcode-ban, a StoryBoard is XIB-é "fordul".

A NIB XIB-ből generált bináris file, amiből futásidő alatt áll elő objektum (class példánya is lehet XIB/NIB-ben leírva).

### Mi az az `@IBOutlet ` és az `@IBAction`?
`@IBOutlet`: Interface Builder-ben definiált objektumra mutat egy adott osztályból.

Pl: `@IBOutlet weak var label: UILabel!`

`@IBaction`: A grafikus editorban létrehozott objektumok által generált események lekezelését végző függvény.

Pl: `@IBAction func buttonClick(sender: UIButton) {}`

### Hogyan lehet megjeleníteni a beépített billentyűzetet?
`textField.becomeFirstResponder()`

### Milyen spec. követelmények vannak az MVC Modelljével szemben?
Függetlennek kell lennie a View / ViewController logikájától.

(???)
