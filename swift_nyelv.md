# Swift nyelv
### Mit jelent az, hogy a Swift erősen és statikusan típusos?
Minden változónak meg kell jelölni a típusát deklarációkor (kivétel max az inferring) és a változók típusa nem változhat        a runtime alatt

### Mi az a type inference?
A compiler megpróbálja kitalálni a változó típusát ha nem lett megadva (pl `var str = “Hello”`)

### Fő működésbeli különbség konstans Struct és Class között?
```swift
//Class
let label = UILabel()
label = UILabel(frame: someFrame) //ERROR
label.text = "yo" //elmegy

//Struct
let constPoint = CGPoint(x: 10, y: 20)
constPoint.x = 20 //ERROR
```

### Mik azok a computed property-k?
Olyan property egy típuson belül, ami más értékekből van "összemixelve"

Példa:
```swift
var title: String //init() adja ez értékét
var author: String //init() adja ez értékét
var titleWithAuthor: String {
    get {
        return "\(title) by \(author)"
    }
}
```

### Milyen láthatósági osztályok léteznek Swiftben? Melyik a legnyitottabb, melyik a legkorlátozottabb?
`open`: framework-ön kívülről látható, kibővíthető, subclass-olható

`public`: kívülről látható, hozzáférhető

`internal`: framework-ön belül látható, egyébként nem

`fileprivate`: .swift file-on belül látható

`private`: csak a kódblokk-on belül látható vagy extension-ben

### Swift switch
Kimerítőnek kell lennie (minden eshetőségre történnie kell valaminek, azaz legtöbb esetben default case is kell)

Nincs fallthrough (nem kell a break a case végére, `fallthrough` és `break` utasítással el lehet érni hogy ez is működjön)

További feltétlelek vizsgálhatók `where`-rel

Példa:
```swift
let yetAnotherPoint = (1, -1)
switch yetAnotherPoint {
case let (x, y) where x == y:
    print("(\(x), \(y)) is on the line x == y")
case let (x, y) where x == -y:
    print("(\(x), \(y)) is on the line x == -y")
case let (x, y):
    print("(\(x), \(y)) is just some arbitrary point")
}
```

### Milyen módszereket ismersz opcionális típus kicsomagolására és használatára?
```swift
let optionalString = String?

guard let unWrappedString = optionalString else {
    return
}

if let unWrappedString = optionalString {
    //code here
}

var name = optionalString? //ha optionalString nil, name is nil
var otherName = optionalString! //ha optionalString nil, a program futásidőben crash-el
```

### Mi a kétfázisú inicializáció, és hogyan működik?
Az osztály az `init()` függvényben először inicializálja a saját adattagjait, és csak utána az ősosztályét a `super.init()`-el
