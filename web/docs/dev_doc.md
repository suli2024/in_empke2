# Fejlesztői dokumentáció

## A fejlesztéshez használt eszközök

Az alkalmazás egy Node.js projektként fejlesztett webes felület. 

Fejlesztői szervernek a BrowserSync-t használtuk, a VSCode kódszerkesztő mellett.

## Könyvtárszerkezet

A web könyvtáron belül az src tartalmazza a forráskódot, itt futtatható. Az alkalmazáshoz egyetlen HTML és egy JavaSCript fájl tartozik.
A style.css jelenleg nincs használatban.

## Stílus

A stílus meghatározásához Bootstrap 5.3.3 keretrendszert használunk.

Párbeszédablakként a Bootstrap beépített modális ablakát használjuk. Ugyanazt az ablakot használjuk hozzáadáshoz és szerkesztés funkciókhoz is.

## JavaScript

A weblap egyes részeit id segítségével kötjük az app.js fájlban egy változóhoz. 

Az url változó tartalmazza a Backend elérési útját. A addMode változó egy logikai változó. Hozzáadás esetén értéke true, szerekesztés esetén false.

Két eseménykezelőt használunk. Az egyik a hozzáadásgombra kattintva indul el, a másik a modális ablak mentés gombjára kattintva.

### A getEmployees függvény

Lekéri a dolgozókat a Backend-től és elindítja a renderelést.


### A renderTbody függvény

A renderTbody függvény jeleníti meg a dolgozókat a webes felületen. A megjelenítéshez table elemet használunk.

A renderTbody paraméterként fogadja a mejelenítendő listát:

```javascript
renderTbody(empList)
```

### A clearFields függvény

A clearFields függvény törli a modális ablak bevitelimezőit.

### Az addEmployee függvény

Az addEmployee függvény a Backend számára elküldi az új dolgozó adatatit POST metódussal. A dolgozó adatait paraméterként fogadja.

```javascript
addEmployee(emp)
```

### A deleteEmployee függvény

A deleteEmployee függvény DELETE metódussal elküldi a törlendő dolgozó azonosítóját. Az id a URL-ben kerül átküldésre, például:

```url
/api/employees/3
```

A deleteEmployee függvény paraméterként várja a törlendő dolgozó azonosítóját:

```javascript
deleteEmployee(id)
```

### Az editEmployee függvény

Az editEmployee függvény beállítja a modális ablak tartalmát szerkesztéshez.

### Az updateEmployee függvény

Az updateEmployee függvény elküli a Bacend szervernek a módoítást, PUT metódussal. A módosítandó dolgozó azonosítóját az URL-ben küljdük, például:

```url
/api/employees/45
```

Az updateEmployee függvény paraméterként várja a dolgozó módosított adatait:

```javascript
updateEmployee(emp)
```
