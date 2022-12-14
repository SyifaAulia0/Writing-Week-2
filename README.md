# Writing-Week-2
## Properties and Method
- Properties adalah ciri/nilai yang berkaitan dengan object 
- Method adalah sebuah fungsi
### Type Data 
type data terbagi menjadi dua : 
- primitiv : string, number, boolean
- non primitiv : array, object
#### string
```js
//string
let hewan = "kAnCIl"
console.log(hewan) //output : kAnCIL

console.log(typeof hewan) //output : string

// properties
console.log(hewan.length); //output : 6 
```
- toUppercase : untuk membuat huruf besar semua
```js
//method
console.log(hewan.toUpperCase()) //output : KANCIL 
```
- toLowerCase : untuk membuat huruf kecil semua
```js
console.log(hewan.toLowerCase()) //output : kancil
```
- charAt : untuk mengembalikan nilai dari string
```js
console.log(hewan.charAt(1)) //output : A
```
- includes : untuk melakukan pencarian. Jika ditemukan mengembalikan nilai true, jika tidak maka akan mengembalikan nilai false
```js
console.log(hewan.includes("s")) //output : true
```
- split 
```js
let kalimat = "dengan menggunakan split(), kita dapat memisahkan sebuah string menjadi data array"
console.log("BEFORE", kalimat)
console.log("AFTER", kalimat.split(" ")); 
//output : BEFORE dengan menggunakan split(), kita dapat memisahkan sebuah string menjadi data array
//output : AFTER (11) ['dengan', 'menggunakan', 'split', 'kita', 'dapat', 'memisahkan', 'sebuah', 'string', 'menjadi', 'data', 'array']
```
- reverse : mengubah kata/kalimat menjadi terbalik
```js
console.log("hallo".reverse()) //output : alloh
```
#### Number
```js
//number
console.log(Number("123")); // 123 in Number
```
- Number.Nan : untuk mengecek apakah itu sebuah number atau bukan
```js
console.log(isNaN(2131)) // false
console.log(isNaN("dawdf")) // true
```
- toString : mengubah angka menjadi sebuah string
```js
let angka = 20 //output : undefined
angka.toString() //output : 20
```
- toFixed : mengambil beberapa angka dibelakang koma, dan berubah menjadi string
```js
let angka = 3.12345
console.log(angka.toFixed(1)) // output : 3.1
```
- math. Abs : membuat minus jadi plus
```js
// properties
console.log(Math.PI)

// method
console.log(Math.abs(-5)) // output : 5
```
- math.pow : pangkat
```js
console.log(Math.pow(3, 2)) //output : 9
```
- math.round : membulatkan angka
```js
console.log(Math.round(5.6)) // output : 6
```
- math.floor : membulatkan kebawah
```js
console.log(Math.floor(5.6)) // output : 5
```
- math.ceil : membulatkan keatas
```js
console.log(Math.ceil(5.2)) // output : 6
```
- math.random : 
```js
console.log(Math.random()) // output : 0.123342
```
#### date
```js
console.log(Date()) // output : 'Tue Sep 27 2022 20:31:20 GMT+0700 (Indochina Time)'
console.log(date.getFullYear()); // output : 2022
```
## DOM (Document Object Model)
- DOM (Document Object Model): jembatan supaya Bahasa pemrograman dapat berinteraksi dengan dokumen html. 
- Dengan DOM, javascript dapat memanipulasi html
- Dom bukan bagian dari JavaScript, melainkan bagian dari web API untuk membuat website.
- Dom dalam bentuk tree structure
![image](https://user-images.githubusercontent.com/114098894/193461394-e2c78305-d2a8-4f3e-ac0b-117ddf854130.png)

- Ada 2 item, ketika mengakses dom :
  1. element : Cuma html element 
  2. node : setiap bagian terkecil di html (text, comment)
### traversing
- Element2 menggunakan dom :
  - Ke bawah : getElementById, getElementsByClassName, getElementByTagName, querySelector family(querySelector, querySelectorAll), children
  ```html
  //index.html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1 id="title">Hallo</h1>

    <ul class="list">
      <li class="item">satu</li>
      <li class="item">dua</li>
      <li class="item">tiga</li>
    </ul>
  <script src="./script.js"></script>
  </body>
  </html>
  ```
  
  ```js
  //script.js //getElementById
  let title = document.getElementById("title")
  console.log(title) //output : <h1 id="title">Hallo</h1>
  ```
  ```js
  //getElementsByClassName
  let items = document.getElementsByClassName("item")
  console.log(items[2]); //output : <li class="item">tiga</li>
  
  let list = document.getElementsByClassName("list")
  console.log(list[0]) //output : <li class="item">satu</li>
  
  //children
  console.log(list[0].children) //output : HTMLCollection(3)0: li.item1: li.item2: li.itemlength: 3[[Prototype]]: HTMLCollection
  ```
  ```js
  //getElementsByTagName
  let itemByTag = document.getElementsByTagName("li")
  console.log(itemByTag[1]) //output : <li class="item">dua</li>
  console.log(itemByTag.item(1)) //output : <li class="item">dua</li>
  console.log(itemByTag.length) //output : 3
  ```
  ```js
  //querySelector
  let listQuery = document.querySelector(".list")
  console.log(listQuery); //output : <ul class="list">
  
  //querySelectorAll
  let itemQueryAll = document.querySelectorAll(".item")
  console.log(itemQueryAll) //output : NodeList(3)0: li.item1: li.item2: li.itemlength: 3[[Prototype]]: NodeList
  ```
  - Ke atas : parentElement, closest()
  ```js
  //parentElement
  console.log(itemQuery.parentElement); //output : <ul class="list">
  ```
  ```js
  //closest
  console.log(itemQuery.closest(".list")); //output : <ul class="list">
  ```
  - Ke samping : nextElementSibling, previousElementSibling
  ```js
  //previousElementSibling
  console.log(itemQuery.previousElementSiblingc); //output : undefined
  ```
  ```js
  //nextElementSibling
  console.log(itemQuery.nextElementSibling); //output : <li class="item">dua</li>
  ```
- HTML Collection bukan array, cara aksesnya mirip dgn array
- Property dan method dalam html collection: length, item(), namedItem()
- HTML collection mirip dengan node list, keduanya memiliki length, 
- Html collection : koleksi dlm bentuk dokumen element
- Node list : dokumen dlm bentuk nodes (element nodes, attribute nodes, text nodes)

## DOM-Manipulation	
- dapat memberikan konten di java script
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    
    
    <title>Document</title>
      </head>
  <body>
  
  <div id="app"></div>
  
  <script src="./script.js"></script>
  </body>
</html>
```
#### innerHTML
```js
//script.js
let app = document.getElementById("app")
app.innerHTML = "<h1>Hallo</h1>" 
```
- output

![Screenshot (2632)](https://user-images.githubusercontent.com/114098894/193524431-da78fac5-341a-48b1-8809-09f9d863b179.png)

#### innerText
```js
//script.js
let app = document.getElementById("app")
app.innerText = "<h1>apa kabs</h1>"
```
- output

![Screenshot (2633)](https://user-images.githubusercontent.com/114098894/193524724-a7b20c24-38b5-412d-bb3e-ba5f309123eb.png)

##### Document.createElement 
```js
//script.js
let p = document.createElement("p")
p.innerText = "ini adalah paragraf"
```
- output

![Screenshot (2636)](https://user-images.githubusercontent.com/114098894/193527217-79e9e228-87f3-465b-8d78-dd42cbf5eb09.png)

#### Append 
- untuk menyisipkan element di dalam element
```js
app.append(p)
```
- output 

![Screenshot (2638)](https://user-images.githubusercontent.com/114098894/193528482-b1bb549e-2691-41c9-aae1-6dcf4529a52b.png)

#### appendChild
- untuk menyisipkan dalam bentuk node 
```js
let p2 = document.createElement("p")
p2.innerText = "paragraf ke-2"
app.appendChild(p2)
```
- output 

![Screenshot (2639)](https://user-images.githubusercontent.com/114098894/193528916-dac85bb2-d51c-4c77-82bf-75dc69567f77.png)
- appendChild tidak dapat menerima sebuah string
```js
app.appendChild("appendChild") // output : error
```

#### end.remove 
- untuk menghapus element
### attributes 
```html
    <div class="container">
      <a href="google.com" class="link">Google</a>
    </div>
```
```js
console.log(link.attributes) // [] list attribute
```
#### getAttributes 
- untuk melihat isi 
```js
link.getAttribute("href")); //google.com
```
#### setAttributes
```js
link.setAttribute("id", "google")  // output : add attribute
```
### style
- style.color : memberi warna
```js
//script.js
link.style.color = "black"
```
- style.border : memberi boder
```js
//script.js
link.style.border = "1px solid black"
```
- style.padding : memberi padding
```js
//script.js
link.style.padding = "5px 20px"
```
- style.backgroundColour : memberi background colour
```js
//script.js
link.style.backgroundColor = "aqua"
```
- output 

![Screenshot (2640)](https://user-images.githubusercontent.com/114098894/193532245-d0fcacd9-e533-453a-9e78-12432b52d27d.png)

## DOM-Event
### Event 
- Event : kejadian/interaksi yang terjadi pada website
- event : click, submit, focus, blur, hover, change, scroll
- 3 cara memberikan event :
  -	HTML attribute
    ```html
    //index.html
     <h1 onclick="alert('selamat datang')">Hallo</h1> 
    ```
  -	Event property
    ```js
    //script.js
    let paragraf = document.getElementById("paragraf")
    paragraf.onclick = function () {
    alert("ini dari paragraf")
    } // paragraf.onclick = tampilkanAlert
    ```
  -	AddEventListener()
    ```js
    //script.js
    let button = document.getElementById("btn")
    button.addEventListener("click", function (event) {
    console.log(event.target)
    alert("ini dari button")
    })
    ```
- User experience itu bersifat dua arah: selain menampilkan element HTML, halaman web juga harus bisa menangkap interaksi user

