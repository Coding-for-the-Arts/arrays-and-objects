# Arrays und Objects

Du kennst bereits die [Datentypen](https://javascript.info/types) *Strings* (Zeichenketten), *Numbers* und *Booleans* (`true` und `false`).

*Arrays* und *Objekte* fassen mehrere Werte zusammen. Sie können **extrem nützlich** sein, z.B. um bei grösseren Datenmengen den Überblick zu behalten. 

## Arrays

- Ein Array ist eine Liste von Werten, z.B. `[3, "a", -1]`
- Die Werte stehen zwischen eckigen Klammern und sind mit Kommas getrennt.
- Mit der Funktion `push()` kannst du einen Wert an die Liste anfügen.
- Du kannst einen Array «leer» initialisieren und dann erst Werte einfügen.

```
let myArray = []

for (let a = 0; a < 10; a += 1) {
  myArray.push(a * 10)
}

// ergibt: [0, 10, 20, 30, 40, 50, 60, 70, 80, 90]
```

### Reihenfolge: Index
 
- Werte in einem  Array sind aufsteigend nummeriert, beginnend bei Null. Das wird *Index* genannt.
- Ein einzelner Wert in einem Array kann mit seinem *Index*  direkt ausgegeben werden.
- Dazu wird der Index in eckige Klammern hinter den Array geschrieben: `myArray[2]`

```
let myFruit = ["apples", "bananas", "oranges", "mangos"]
 
 console.log(myFruit[0]) // "apples"
 console.log(myFruit[1]) // "bananas"
```

Auf diese Art kannst du auch einen bestimmten Wert im Array ändern.

```
let myVegetables = ["broccoli", "spinach", "onions"]

myVegetables[1] = "cabbage"

console.log(myVegetables) // ["broccoli", "cabbage", "onions"]
```

### Länge eines Arrays

`myArray.length` ergibt die «Länge» eines Arrays (die Anzahl seiner Werte).

```
let myHerbs = ["oregano", "basil", "thyme"]

console.log(myHerbs.length) // 3
``` 

### Array Iteration

Mit einer *For-Schleife* kannst du durch die Elemente eines Arrays gehen.

```
for (let i = 0; i < myFruit.length; i += 1) {
  console.log(myFruit[i])
}
```

Es gibt auch einen Loop, der jenem von Python gleicht:

```
for (let item of myArray) {
  console.log(item)
}
```

**Vorsicht**: in JavaScript gibt es `for … of` und `for … in` – und es ist nicht das Gleiche!

+++

## Objekte

- Ein Objekt ist eine *Datensammlung*: wie ein Array kann ein Objekt mehrere Werte enthalten.
- Geschrieben werden Objekte mit geschweiften Klammern.
- Im **Unterschied zu einem Array** haben die Werte in einem Objekt einen *Namen*.
- Diese Namen werden auch als *Eigenschaften* eines Objekts bezeichnet.

```
let myDessert = { 
  type: "ice cream",
  flavour: "fior di latte",
  servings: 3
}
```

- Mit diesen *Eigenschaften/Namen* kriegst du einzelne Werte eines Objekts: `myDessert.type` ist `"ice cream"`.
- Dies wird *dot notation* genannt.

### Leere Initialisierung

- Wie Arrays kannst du auch Objekte «leer» initialisieren, d.h. nur mit geschweiften Klammern.
- Indem du ebenfalls die Punkt-Schreibweise benutzt, kannst du einem Objekt zusätzliche Namen/Wert-Paare geben: `myDessert.topping = "cherry"`

```
let myFridge = {}

myFridge.top = "eggs"
myFridge.middle = ["cheese", "yoghurt", "butter"]
myFridge.bottom = ["vegetables", "kimchi"]
myFridge.temperature = 4.5
```

+++

## Beispiel für die Verwendung von Array und Object

Mit Arrays und Objekten kannst du z.B. Positionsdaten speichern.

```
let shapes = []

function setup() {
  createCanvas(400, 400)
  
  // Zwei Objekte in den Array «pushen».
  shapes.push({x: random() * width, y: random() * height})
  shapes.push({x: random() * width, y: random() * height})
  // Dies könntest du auch mit einem Loop machen.
}

function draw() {

  // Loop durch den Array
  for (let i = 0; i < shapes.length; i += 1) {
    // Varible mit einzelnem Element aus dem Array 
    let currentShape = shapes[i]
    
    // Einen Kreis zeichnen
    ellipse(currentShape.x, currentShape.y, 10)
    
    // Werte im Objekt ändern
    currentShape.x += 1
    currentShape.y += 1
  }
  
}
```

- In diesem Beispiel werden zwei Kreise zufällig platziert.
- Dann werden Sie mit jedem neuen Frame um je eine Einheit nach rechts und nach oben geschoben.
- Nach kurzer Zeit verlassen sie den sichtbaren Bereich des Canvas.

**Challenge:** Kannst du mit *if/else* eine Bedingung schreiben, die dafür sorgt, dass die Kreise «abprallen» wenn sie den Rand des Canvas erreichen?