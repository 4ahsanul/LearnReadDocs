## Official Documentation
[Kotlin Basic Syntax](https://kotlinlang.org/docs/basic-syntax.html#while-loop)

## Table of Contents
- [Package Definition And Imports](#package-definition-and-imports)
- [Program Entry Point](#program-entry-point)
- [Print To Standard Output](#print-to-standard-output)
- [Variables](#variables)
- [Creating Classes And Instances](#creating-classes-and-instances)
- [Comments](#comments)
- [Conditional Expressions](#conditional-expressions)
- [for loop](#for-loop)
- [while loop](#while-loop)
- [when expressions](#when-expressions)
- [Ranges](#ranges)
- [Collections](#collections)
- [Nullable Values And Null Checks](#nullable-values-and-null-checks)
- [Type Checks And Automatic Cast](#type-checks-and-automatic-cast)


# Package Definition And Imports
Package spesification haruslah diletakkan diatas dari source file, berikut adalah contoh dalam mendeklarasikan Package.
```kotlin
package my.demo
import kotlin.text.*
```
</br>

# Program Entry Point
Sebuah entry point dari Kotlin terdapat pada <span style="color: orange"> main function </span>, entry point ini akan digunakan untuk mengeksekusi kode program.
```kotlin
fun main() {
    println("Hellow Happy World!")
}
```
Bentuk lain dari <span style="color: orange"> main function </span> dapat menerima sejumlah variable dari __String arguments__.
```kotlin
fun main(args: Array<String>) {
    println(args.contentToString())
}
```
</br>


# Print To Standard Output
Dalam Kotlin untuk menampilkan sebuah output adalah dengan memanggil fungsi print atau println didalam <span style="color: orange"> main function </span>.
```kotlin
print("Kata")
println("Kalimat") // println akan menampilkan sebuah output dengan baris baru (line break)
```
</br>

# Function
__Function__ merupakan sebuah bagian dari program (sub modul/program) yang dibuat untuk menyelesaikan problem tertentu, berikut contoh sebuah __function__ untuk melakukan penjumlahan antara dua bilangan A dan B.
```kotlin
fun sum(a: Int, b: Int) {
    return a + b
}
```
Atau dapat juga __function body__ berisi sebuah _expression_ dan _return type_ akan dipilih secara otomatis oleh Kotlin itu sendiri.
```kotlin
fun sum(a: Int, b: Int) = a + b // Disini tidak memberikan type pada sum tapi Kotlin secara pintar sudah memberikan type yang sesuai secara otomatis
```
Atau juga dapat membuah sebuah __function__ yang memiliki return dengan value yang tidak berarti(?).
```kotlin
fun printSum(a: Int, b: Int): Unit { // Disini unit dapat dihilangkan
    println("Hasil dari $a ditambahkan dengan $b adalah ${a + b}")
}
```
Kemudian untuk memanggil __function__ diatas lakukan didalam <span style="color: orange"> main function </span>.
</br>

# Variables
__Read-only local variables__ didefinisikan dengan kata kunci <span style="color: red"> val </span>, dan dapat diberi nilai sekali saja yaitu saay melakukan deklarasi. Kebalikannya, __variables__ ynag dapat diubah nilainya didefinisikan dengan kata kunci <span style="color: green"> var </span>. Jadi <span style="color: red"> val </span> bersifat __imutable__ (tidak bisa diubah) sedangkan <span style="color: green"> var </span> bersifat __mutable__ (dapat diubah).
```kotlin
fun main() {
    val a: Int = 1 // Langsung diberi nilai
    val b = 2 // Int tidak dideklarasikan dan Kotlin secara otomatis memebrikan nilai Int
    val c: Int // Tidak langsung diberikan nilai
    c = 1 // Diberi nilai setelah c dideklarasikan
    println("a = $a, b = $b, c = $c")

    //Variables yang dapat diubah nilainya dengan kata kunci var
    var x = 5
    x += 10
    println("x = $x")
}
```
Dan __variables__ tidak selalu harus dideklarasikan didalam __entry point__, tetepai juga dapat dideklarasikan diatas dari __entry point__.
```kotlin
val PI = 3.14
var y = 0

fun incrementY() {
    y += 1
}

fun main() {
    println("y = $y; PI = $PI")
    incrementY()
    println("incrementY()")
    println("y = $y; PI = $PI")
}
```
</br>

# Creating Classes And Instances
Dalam mendefinisikan sebuah kelas adalah dengan menggunakan kata kunci <span style="color: aqua"> class </span>. __Properties__ dari sebuah kelas dapat diletakkan didalam __declaration__ atau __body__.
```kotlin
class Rectangle(var height: Double, var length: Double) {
    val perimeter = (height + length) * 2
}

//Default constructor dengan parameter didalam class declaration dapat tersedia secara otomatis
fun main () {
    val rectangle = Rectangle(5.0, 2.0)
    println("Parameter adalah ${rectangle.perimeter}")
}
```
__Inheritances__ diantara classes dapa dideklarasikan dengan __titik dua ( : )__. __Classes__ adalah final secara default, untuk membuat <span style="color: aqua"> class </span> dapat __inheritable__, tandai <span style="color: aqua"> class </span> tersebut dengan kata kunci <span style="color: teal"> open </span>.
```kotlin
open class Shape

class Rectangle(var height: Double, var length: Double): Shape() {
    var perimeter = (height + length) * 2
}
```
</br>

# Comments
Seperti bahasa pemrograman pada umumnya, Kotlin juga mendukung __single line (or end-of-line)__ dan __multi line (block)__ comments. __Single line comment__ ditandai dengan ( // ), sedangkan __multiple lines comments__ ditandai dengan ( /* dan */ )
```kotlin
// Ini adalah single line comment
Ini bukan comment
/*
Ini adalah multi lines comments
Ini juga masuk ke multi comments
Ini juga
*/
Bukan comment
```
</br>

# Conditional Expressions
Sama seperti bahasa pemrograman pada umumnya, Kotlin juga terdapat perkondisian.
```kotlin 
fun maxOf(a: Int, b: Int): Int {
    if(a > b) {
        return a
    } else {
        return b
    }
}
```
Dalam Kotlin, __if__ juga dapat digunakan sebagai __expression__.
```kotlin
fun maxOf(a: Int, b: Int) = if (a > b) a else b
```
```kotlin
fun main() {
    println("Max of 0 and 42 is ${maxOf(0, 42)}")
    println("Max of 43 and 0 is ${maxOf2(43, 0)}")
}
```
</br>

# for loop
Didalam Kotlin juga terdapat __looping__ untuk melakukan perulangan.
```kotlin
fun main() {
    val items = listOf("Apple", "Banana", "Kiwi")
    for (item in items) {
        println(item)
    }
```
Atau juga dapat seperti ini
```kotlin
fun main() {
    val items = listOf("Pineapple", "Melon", "Watermelon")
    for (index in items.indices) {
        println("Item at $index is ${items[index]}")
    }
}
```
Dengan ini hasil dari kode akan terus megulang isi dari list.
</br>

# while loop
Konsep while ini mirip dengan bahasa pemrograman pada umumnya, jika sudah familiar dengan bahasa C++ maka tidak asing lagi dengan __while__ ini, dimana __while__ akan terus mengulang hingga kondisi terpenuhi.
```kotlin
fun main() {
    val items = listOf("Apple", "Banana", "Kiwi")
    var index = 0
    while (index < items.size) {
        println("Items at $index is ${items[index]}")
        index ++
    }
}
```
</br>

# when expressions
```kotlin
fun describe(obj: Any): String = when (obj) {
    1 -> "One"
    "Hello" -> "Greeting"
    is Long -> "Long"
    !is String -> "Not a string"
    else -> "Unknown"
}

fun main() {
    println(describe(1))
    println(describe("Hello"))
    println(describe(1000L))
    println(describe(2))
    println(describe("other"))
}
```
Hampir sama seperti __while__ diatas, __when__ disini berarti kode akan tereksekusi jika suatu kondisi terpenuhi.
</br>

# Ranges
__Range__ adalah fungsi yang gunanya untuk menciptakan sebuah list yang terdiri dari angka. Berikut adalah contoh sebuah __range__ dalam melakukan pengecekan data dengan menggunakan operator __in__.
```kotlin
fun main() {
    val x = 10
    val y = 9
    if (x in 1..y+1) {
        println("Ada didalam range")
    }
}
```
Contoh lainnya seperti ini :
```kotlin
fun main() {
    val list = listOf("a", "b", "c")

    if (-1 !in 0..list.lastIndex) {
        println("-1 tidak ada didalam range")
    }
    if (list.size !in list.indices) {
        println("list size diluar dari valid list indices range, juga")
    }
}
```
Range juga dapat digunakan untuk melakukan __iteration__.
```kotlin
fun main() {
    for (x in 1..5) {
        print(x)
    }
}
```
Dan juga untuk melakukan __progression__.
```kotlin
for (x in 1..10 step 2) {
        print(x)
    }
    println()
    for (x in 9 downTo 0 step 3) {
        print(x)
    }
```
</br>

# Collections
__Collection__  merupakan wadah yang menampung value.
```kotlin
fun main() {
    val items = listOf("Apple", "Banana", "Kiwi") // Ini Collections nya ygy
    for (item in items) {
        println(item)
    }
}
```
Melakukan __check collection__ yang terdapat suatu objek menggunakan operator __in__.
```kotlin
fun main() {
    val items = setOf("Apple", "Banana", "Kiwi")
    when {
        "Orange" in items -> println("juicy")
        "Apple" in items -> println("Apple is fine too")
    }
}
```
Atau juga menggunakan __lambda expressions__ untuk __filter__ dan __map collections__.
```kotlin
fun main() {
    val fruits = listOf("banana", "avocado", "apple", "kiwifruit")
    fruits
        .filter { it.startsWith("a") }
        .sortedBy { it }
        .map { it.uppercase() }
        .forEach { println(it) }
}
```
</br>

# Nullable Values And Null Checks
Sebuah referensi harus secara eksplisit ditandai sebagai __nullable__ ketika nilai null memungkinkan. Nullable type diakhiri dengan __tanda tanya (?)__.
```kotlin
// Return null jika str tidak int
fun parseInt(str: String): Int? {
    //...
}
```
Menggunakan function untuk mengemabalikkan nilai __null__.
```kotlin
fun parseInt(str: String): Int? {
    return str.toIntOrNull()
}
```
```kotlin
fun printProduct(arg1: String, arg2: String) {
    val x = parseInt(arg1)
    val y = parseInt(arg2)

    // Menggunakan 'x * y' akan error karena terlalu banyak menampung null
    if (x != null && y != null) {
        // x dan y akan otomatis dimasukkan ke non-nullable setelah null check
        println(x * y)
    }
    else {
        println("'arg1' or 'arg2' bukan sebuah angka")
    }
}
```
Atau juga seperi ini
```kotlin
fun printProduct2(arg1: String, arg2: String) {
    val x = parseInt(arg1)
    val y = parseInt(arg2)

    // ...
    if (x == null) {
        println("Kesalahan format pada arg1: '$arg1'")
        return
    }
    if (y == null) {
        println("Kesalahan format pada arg2: '$arg2'")
        return
    }

    // x dan y akan secara otomatis menjadi non-nullable setelah null check
    println(x * y)
}
```
</br>

# Type Checks And Automatic Cast
__is__ operator melakukan check jika terdapat sebuah instance dari sebuah tipe. Jika sebuah immutable local variable atau property dicheck untuk tipe yang spesifik, maka tidak perlu dipanggil secara eksplisit.
```kotlin
fun getStringLength(obj: Any): Int? {
    if (obj is String) {
        // `obj` otomatis diberikan tipe 'String' pada cabang ini
        return obj.length
    }

    // `obj` masih menjadi tipe 'Any' diluar dari cabang diatas
    return null
}
```
Atau seperti ini
```kotlin
fun getStringLength(obj: Any): Int? {
    if (obj !is String) return null

    // `obj` secara otomatis diberikkan tipe 'String' pada cabang ini
    return obj.length
}
```
Atau bahkan seperti ini
```kotlin
fun getStringLength(obj: Any): Int? {
    // `obj` otomatis diberikan nilai 'String' disamping kanan dari '&&'
    if (obj is String && obj.length > 0) {
        return obj.length
    }

    return null
}
```
__Function__ diatas dapat dijalankan didalam <span style="color: orange"> main function </span>.
```kotlin
fun main() {
    fun printLength(obj: Any) {
        println("Getting the length of '$obj'. Result: ${getStringLength(obj) ?: "Error: The object is not a string"} ")
    }
    printLength("Incomprehensibilities")
    printLength(1000)
    printLength(listOf(Any()))
}
```