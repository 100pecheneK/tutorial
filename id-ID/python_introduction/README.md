{% set warning_icon = '<span class="glyphicon glyphicon-exclamation-sign" style="color: red;" aria-hidden="true" data-toggle="tooltip" title="An error is expected when you run this command!" ></span>' %}

# Pengantar Python

> Bagian dari bab ini didasarkan pada tutorial oleh Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).

Mari kita tulis beberapa kode!

## Python prompt

> Bagi pembaca di rumah: bagian ini tercakup dalam [Dasar-Dasar Python: Integer, String, Daftar, Variabel dan Kesalahan](https://www.youtube.com/watch?v=MO63L4s-20U) video.

Untuk memulai python, kita perlu membuka *Comand line atau Jendela perintah* pada komputer anda. Anda seharusnya sudah tahu bagaimana melakukan itu - Anda mempelajarinya di bagian [Intro to Command Line](../intro_to_command_line/README.md).

Ketika kamu sudah siap, Silakan ikuti instruksi dibawah ini.

Kita ingin membuka konsol Python, Jadi silakan ketik `python` untuk Windows atau `python3` pada Mac OS/Linux dan tekan `Enter`.

{% filename %} baris perintah {% endfilename %}

    $ python3 Python 3.4.3 (...) Type "help", "copyright", "credits" or "license" for more information. >>>
    

## Perintah Python Pertama!

Setelah menjalankan perintah Python, prompt akan berubah menjadi `>>>`. Bagi kita sekarang adalah kita harus menggunakan perintah pada bahasa Python saja. Kmau gak perlu mengetik pada perintah `>>>` - Python akan melakukannya untukmu.

Jika kamu ingin keluar dari konsol Python, Cukup dengan mengetik perintah `exit()` atau pakai shortcut `Ctrl + Z` untuk Windows dan `Ctrl + D` untuk Mac/Linux. Kemudian kamu tidak akan melihat lagi `>>>`.

Untuk saat ini, kami tidak ingin untuk keluar dari konsol Python. Kami ingin belajar lebih banyak tentang hal itu. Mari kita mulai dengan mengetik beberapa matematika, seperti `2 + 3` dan memukul `masuk`.

{% filename %}command-line{% endfilename %}

```python
>>> 2 + 3
5
```

Bagus! Lihat bagaimana balasan muncul keluar? Python tahu matematika! Anda bisa mencoba perintah lain seperti:

- `4 * 5`
- `5 - 1`
- `40 / 2
`

Untuk melakukan perhitungan eksponensial, katakan 2 pada power 3, kita ketik: {% filename %}baris perintah{% endfilename %}

```python
>>> 2 ** 3
8
```

Bersenang-senang dengan ini sebentar dan kemudian kembali kesini. :)

Seperti yang Anda lihat, Python adalah kalkulator yang hebat. Jika Anda bertanya-tanya apa lagi yang bisa Anda lakukan…

## Kata

Bagaimana dengan namamu? Ketik nama depan Anda dalam tanda kutip seperti ini:

{% filename %} baris perintah {% endfilename %}

```python
>>> "Ola" * 
'OlaOlaOla'
```

Anda sekarang telah membuat string pertama Anda! Ini adalah urutan karakter yang bisa diolah oleh komputer. String harus selalu dimulai dan diakhiri dengan karakter yang sama. Ini mungkin tunggal (`'`) atau double (`"`) mengutip (tidak ada bedanya!) Kutipan memberi tahu Python bahwa apa yang ada di dalamnya adalah string.

String bisa dirangkai. Coba ini:

{% filename %}baris perintah{% endfilename %}

```python
>>> "Hi there " + "Ola"
'Hi there Ola'
```

Anda juga bisa mengalikan string dengan angka:

{% filename %} baris perintah {% endfilename %}

```python
>>> "Ola" * 3
'OlaOlaOla'
```

Jika Anda perlu menempatkan tanda kutip di dalam string Anda, Anda memiliki dua cara untuk melakukannya.

Menggunakan tanda kutip ganda:

{% filename %}baris perintah{% endfilename %}

```python
>>> 'Runnin\' menuruni bukit'
"Runnin' menuruni bukit"
```

atau keluar dari apostrof dengan garis miring terbalik (``):

{% filename %}baris perintah{% endfilename %}

```python
>>> 'Runnin\' menuruni bukit'
"Runnin' menuruni bukit"
```

Bagus, ya? Untuk melihat nama Anda dalam huruf besar, cukup ketik:

{% filename %} baris perintah {% endfilename %}

```python
>>> "Ola".upper()
'OLA'
```

Anda hanya menggunakan **method**`upper` pada string anda! Method (`upper`) adalah urutan instruksi yang Python harus melakukan pada objek tertentu ( ` " Ola " `) setelah anda menyebutnya.

Jika Anda ingin tahu jumlah huruf yang terkandung dalam nama Anda, ada **function** untuk itu juga!

{% filename %}baris perintah{% endfilename %}

```python
>>> len ("Ola")
3
```

Entah mengapa kadang-kadang Anda memanggil fungsi dengan `.` di akhir string (seperti `"Ola".upper()`) dan terkadang Anda pertama kali memanggil fungsi dan menempatkan string dalam kurung? Nah, dalam beberapa kasus, fungsi termasuk objek, seperti `upper()`, yang hanya bisa dilakukan pada string. Dalam hal ini, kita sebut fungsi sebuah **metode**. Di lain waktu, fungsi tidak termasuk dalam sesuatu yang spesifik dan dapat digunakan pada berbagai jenis objek, seperti `len()`. Itu sebabnya kami memberi `"Ola"` sebagai parameter pada fungsi `len`.

### Ringkasan

OK, cukup banyak senar. Sejauh ini Anda telah belajar tentang:

- **prompt** - perintah mengetik (kode) ke prompt Python menghasilkan jawaban dengan Python
- **nomor dan string** - dengan nomor Python digunakan untuk matematika dan string untuk objek teks
- **operators** – like `+` and `*`, combine values to produce a new one
- **fungsi** - seperti `atas()` dan `len()`, lakukan tindakan pada objek.

Ini adalah dasar dari setiap bahasa pemrograman yang Anda pelajari. Siap untuk sesuatu yang lebih sulit? Kami yakin Anda!

## Kesalahan

Mari kita coba sesuatu yang baru. Bisakah kita mendapatkan panjang sejumlah cara yang sama kita bisa mengetahui panjang nama kami? Ketik di `len(304023)` dan tekan `Masukkan`:

{% filename %}{{ warning_icon }}{% endfilename %} baris perintah

```python
& gt; & gt; & gt; len (304023) Traceback (panggilan terakhir terakhir):
   File " <stdin> ", baris 1, di <module> 
TypeError: objek tipe 'int' tidak memiliki len ()
```

Kami punya kesalahan pertama kami! Ikon {{ warning_icon }} adalah cara kami memberi Anda kepala up yang Anda akan menjalankan kode tidak bekerja seperti yang diharapkan. Membuat kesalahan (bahkan disengaja yang) yang merupakan bagian penting dari belajar!

Dikatakan bahwa objek dari jenis "int" (bilangan bulat, bilangan bulat) memiliki panjang tidak. Jadi apa yang dapat kita lakukan sekarang? Mungkin kita dapat menulis nomor kami sebagai string? String memiliki panjang, kanan?

{% filename %}command-line{% endfilename %}

```python
& gt; & gt; & gt; len (str (304023)) 6
```

Itu berhasil! Kami menggunakan fungsi `str` dalam fungsi `len`. `Str()` mengkonversi segala sesuatu ke string.

- Fungsi `int` mengubah semuanya menjadi **bilangan bulat**
- Fungsi `int` mengubah hal-hal menjadi **bilangan bulat**

> Penting: kita bisa mengonversi bilangan menjadi teks, tapi kita tidak bisa mengubah teks menjadi angka - apa yang akan `int ('halo')` jadi?

## Variabel

Konsep penting dalam pemrograman adalah variabel. Variabel adalah tidak lebih dari sebuah nama untuk sesuatu sehingga Anda dapat menggunakannya nanti. Programmer menggunakan variabel ini untuk menyimpan data, membuat kode mereka lebih mudah dibaca dan sehingga mereka tidak perlu tetap mengingat apa hal-hal yang.

Katakanlah kita ingin membuat sebuah variabel baru yang disebut `nama`:

{% filename %}baris perintah{% endfilename %}

```python
>>> nama = "Ola"
```

Kita ketik nama sama Ola.

Seperti yang Anda perhatikan, program Anda tidak kembali sesuatu seperti itu lakukan sebelumnya. Jadi bagaimana kita tahu bahwa variabel benar-benar ada? Cukup masukkan `nama` dan tekan `Masukkan`:

{% filename %}baris perintah{% endfilename %}

```python
>>> name
'Ola'
```

Hura! Variabel pertama Anda! :) Anda selalu dapat mengubah apa yang ia merujuk kepada:

{% filename %}baris perintah{% endfilename %}

```python
>>> name = "Sonja"
>>> name
'Sonja'
```

Anda dapat menggunakannya dalam fungsi juga:

{% filename %} baris perintah {% endfilename %}

```python
>>> len(name)
5
```

Awesome, right? Of course, variables can be anything – numbers too! Try this:

{% filename %}baris perintah{% endfilename %}

```python
>>> a = 4
>>> b = 6
>>> a * b
24
```

Tapi bagaimana jika kita menggunakan nama yang salah? Dapatkah kamu menebak apa yang akan terjadi? Mari kita coba!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> kota = "Tokyo"
>>> ctiy
Traceback (panggilan terakhir):
   File "<stdin>", baris 1, di <module>
NameError: nama 'ctiy' tidak didefinisikan
```

Kesalahan! Seperti yang Anda lihat, Python memiliki berbagai jenis kesalahan dan satu ini disebut **NameError**. Python akan memberikan kesalahan ini jika Anda mencoba menggunakan sebuah variabel yang belum didefinisikan belum. Jika Anda mengalami kesalahan ini kemudian, memeriksa kode Anda untuk melihat jika Anda telah salah ketik nama.

Bermain dengan ini untuk sementara waktu dan lihat apa yang dapat Anda lakukan!

## Fungsi cetak

Coba ini:

{% filename %}command-line{% endfilename %}

```python
>>> name = 'Maria'
>>> name
'Maria'
>>> print(name)
Maria
```

Ketika Anda cukup mengetikkan `nama`, Python interpreter merespon dengan *representasi* string variabel 'nama', yang huruf M-a-r-i-a, dikelilingi oleh tanda kutip tunggal, ''. Ketika Anda mengatakan `print(name)`, Python akan "cetak" isi dari variabel ke layar, tanpa tanda kutip, yang merupakan lebih rapi.

Seperti yang kita akan lihat nanti, `print()` ini juga berguna ketika kita ingin mencetak sesuatu dari di dalam fungsi, atau ketika kita ingin mencetak hal pada beberapa baris.

## Daftar

Beside strings and integers, Python has all sorts of different types of objects. Now we're going to introduce one called **list**. Lists are exactly what you think they are: objects which are lists of other objects. :)

Go ahead and create a list:

{% filename %}baris perintah{% endfilename %}

```python
>>> []
[]
```

Yes, this list is empty. Not very useful, right? Let's create a list of lottery numbers. We don't want to repeat ourselves all the time, so we will put it in a variable, too:

{% filename %}baris perintah{% endfilename %}

```python
>>> undian = [3, 42, 12, 19, 30, 59]
```

Baiklah, kita punya daftar! Apa yang bisa kita lakukan dengan itu? Mari kita lihat berapa jumlah undian yang ada dalam daftar. Apakah Anda tahu fungsi mana yang harus Anda gunakan untuk itu? Anda sudah tahu ini!

{% filename %}baris perintah{% endfilename %}

```python
>>> len(lottery)
6
```

Ya! `Len()` dapat memberikan sejumlah objek dalam daftar. Handy, kanan? Mungkin kita akan semacam itu sekarang:

{% filename %}baris perintah{% endfilename %}

```python
>>> lottery.sort()
```

Ini tidak kembali apa-apa, ini hanya mengubah urutan di mana nomor muncul dalam daftar. Mari kita mencetak lagi dan melihat apa yang terjadi:

{% filename %}command-line{% endfilename %}

```python
>>> cetak (undian)
[3, 12, 19, 30, 42, 59]
```

Seperti yang Anda lihat, angka-angka dalam daftar diurutkan sekarang dari nilai terendah ke tertinggi. Congrats!

Mungkin kita ingin terbalik urutan itu? Mari kita lakukan!

{% filename %}baris perintah{% endfilename %}

```python
>>> lottery.reverse ()
>>> cetak (undian)
[59, 42, 30, 19, 12, 3]
```

Jika Anda ingin menambahkan sesuatu ke daftar Anda, Anda dapat melakukan ini dengan mengetik perintah ini:

{% filename %}baris perintah{% endfilename %}

```python
>>> lottery.append (199)
>>> cetak (undian)
[59, 42, 30, 19, 12, 3, 199]
```

Jika Anda ingin menampilkan hanya nomor pertama, Anda dapat melakukan ini dengan menggunakan **indeks**. Sebuah indeks adalah angka yang mengatakan di mana dalam daftar sebuah item terjadi. Programmer lebih memilih untuk mulai menghitung 0, jadi obyek pertama dalam daftar Anda di indeks 0, berikutnya adalah 1, dan sebagainya. Try this:

{% filename %}command-line{% endfilename %}

```python
>>> cetak (undian[0])
59
>>> cetak (undian [1])
42
```

Seperti yang Anda lihat, Anda dapat mengakses objek yang berbeda dalam daftar Anda dengan menggunakan daftar nama dan indeks objek dalam kurung.

Untuk menghapus sesuatu dari daftar Anda Anda akan perlu menggunakan **indeks** seperti yang kita pelajari di atas dan metode `pop()`. Mari kita coba contoh dan memperkuat apa yang kita pelajari sebelumnya; kami akan menghapus nomor pertama dari daftar kami.

{% filename %}command-line{% endfilename %}

```python
>>> cetak (undian)
[59, 42, 30, 19, 12, 3, 199]
>>> cetak (undian[0])
59
>>> lottery.pop(0)
59
>>> cetak(undian)
[42, 30, 19, 12, 3, 199]
```

That worked like a charm!

For extra fun, try some other indexes: 6, 7, 1000, -1, -6 or -1000. See if you can predict the result before trying the command. Do the results make sense?

You can find a list of all available list methods in this chapter of the Python documentation: https://docs.python.org/3/tutorial/datastructures.html

## Kamus

> Bagi pembaca di rumah: bagian ini tercakup dalam [Python Basics: Dictionaries](https://www.youtube.com/watch?v=ZX1CVvZLE6c) video.

A dictionary is similar to a list, but you access values by looking up a key instead of a numeric index. A key can be any string or number. The syntax to define an empty dictionary is:

{% filename %}command-line{% endfilename %}

```python
>>> {}
{}
```

This shows that you just created an empty dictionary. Hurray!

Now, try writing the following command (try substituting your own information, too):

{% filename %}command-line{% endfilename %}

```python
>>> peserta = {'nama': 'Ola', 'country': 'Poland', 'favorite_numbers': [7, 42, 92]}
```

With this command, you just created a variable named `participant` with three key–value pairs:

- Kunci `nama` menunjuk ke nilai `'Ola'` (a `string` objek),
- `negara` menunjuk ke `'Polandia'` (string `lainnya`),
- dan `favorite_numbers` menunjuk ke `[7, 42, 92]` (a `daftar` dengan tiga nomor di dalamnya).

You can check the content of individual keys with this syntax:

{% filename %}command-line{% endfilename %}

```python
>>> print(participant['name'])
Ola
```

See, it's similar to a list. But you don't need to remember the index – just the name.

What happens if we ask Python the value of a key that doesn't exist? Can you guess? Let's try it and see!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> peserta['usia']
Traceback (panggilan terakhir):
  File "<stdin>", baris 1, di <module>
KeyError: 'usia'
```

Look, another error! This one is a **KeyError**. Python is helpful and tells you that the key `'age'` doesn't exist in this dictionary.

When should you use a dictionary or a list? Well, that's a good point to ponder. Just have a solution in mind before looking at the answer in the next line.

- Apakah Anda hanya butuh urutan barang yang dipesan? Pergi untuk daftar.
- Apakah Anda perlu mengaitkan nilai dengan kunci, sehingga Anda dapat melihatnya secara efisien (dengan kunci) nanti? Gunakan kamus.

Dictionaries, like lists, are *mutable*, meaning that they can be changed after they are created. You can add new key–value pairs to a dictionary after it is created, like this:

{% filename %}baris perintah{% endfilename %}

```python
>>> participant['favorite_language'] = 'Python'
```

Like lists, using the `len()` method on the dictionaries returns the number of key–value pairs in the dictionary. Go ahead and type in this command:

{% filename %}command-line{% endfilename %}

```python
>>> len(participant)
4
```

I hope it makes sense up to now. :) Ready for some more fun with dictionaries? Read on for some amazing things.

You can use the `pop()` method to delete an item in the dictionary. Say, if you want to delete the entry corresponding to the key `'favorite_numbers'`, just type in the following command:

{% filename %}command-line{% endfilename %}

```python
>>> participant.pop('favorite_numbers')
[7, 42, 92]
>>> participant
{'country': 'Poland', 'favorite_language': 'Python', 'name': 'Ola'}
```

As you can see from the output, the key–value pair corresponding to the 'favorite_numbers' key has been deleted.

As well as this, you can also change a value associated with an already-created key in the dictionary. Type this:

{% filename %}command-line{% endfilename %}

```python
>>> participant['country'] = 'Germany'
>>> participant
{'country': 'Germany', 'favorite_language': 'Python', 'name': 'Ola'}
```

As you can see, the value of the key `'country'` has been altered from `'Poland'` to `'Germany'`. :) Exciting? Hurrah! You just learned another amazing thing.

### Ikhtisar

Awesome! You know a lot about programming now. In this last part you learned about:

- **error** - Anda sekarang tahu bagaimana membaca dan memahami kesalahan yang muncul jika Python tidak mengerti perintah yang Anda berikan
- **variabel** - nama untuk objek yang memungkinkan kode Anda lebih mudah dan membuat kode Anda lebih mudah dibaca
- **daftar** - daftar objek yang tersimpan dalam urutan tertentu
- **kamus** - objek yang disimpan sebagai pasangan kunci-nilai

Excited for the next part? :)

## Bandingkan hal-hal

> Bagi pembaca di rumah: bagian ini tercakup dalam [Dasar-dasar Python: Perbandingan](https://www.youtube.com/watch?v=7bzxqIKYgf4) video.

A big part of programming involves comparing things. What's the easiest thing to compare? Numbers, of course. Let's see how that works:

{% filename %}command-line{% endfilename %}

```python
>>> 5 > 2
True
>>> 3 < 1
False
>>> 5 > 2 * 2
True
>>> 1 == 1
True
>>> 5 != 2
True
```

We gave Python some numbers to compare. As you can see, not only can Python compare numbers, but it can also compare method results. Nice, huh?

Do you wonder why we put two equal signs `==` next to each other to compare if numbers are equal? We use a single `=` for assigning values to variables. You always, **always** need to put two of them – `==` – if you want to check if things are equal to each other. We can also state that things are unequal to each other. For that, we use the symbol `!=`, as shown in the example above.

Give Python two more tasks:

{% filename %}command-line{% endfilename %}

```python
>>> 6 >= 12 / 2
Benar
>>> 3 < = 2
Salah
```

We've seen `>` and `<`, but what do `>=` and `<=` mean? Read them like this:

- x `>` y berarti: x lebih besar dari y
- x `<` y berarti: x kurang dari y
- x `<=` y berarti: x kurang dari atau sama dengan y
- x `>=` y berarti: x lebih besar dari atau sama dengan y

Awesome! Wanna do one more? Try this:

{% filename %}command-line{% endfilename %}

```python
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
```

You can give Python as many numbers to compare as you want, and it will give you an answer! Pretty smart, right?

- **dan** - jika Anda menggunakan operator `dan`, kedua perbandingan harus benar agar keseluruhan perintah menjadi True
- **atau** - jika Anda menggunakan operator `atau`, hanya satu perbandingan yang harus Benar agar seluruh perintah menjadi Benar

Have you heard of the expression "comparing apples to oranges"? Let's try the Python equivalent:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> 1 > 'django'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: '>' not supported between instances of 'int' and 'str'
```

Here you see that just like in the expression, Python is not able to compare a number (`int`) and a string (`str`). Instead, it shows a **TypeError** and tells us the two types can't be compared together.

## Boolean

Incidentally, you just learned about a new type of object in Python. It's called **Boolean**.

There are only two Boolean objects:

- Benar
- Salah

But for Python to understand this, you need to always write it as 'True' (first letter uppercase, with the rest of the letters lowercased). **true, TRUE, and tRUE won't work – only True is correct.** (The same applies to 'False' as well, of course.)

Booleans can be variables, too! See here:

{% filename %}baris perintah{% endfilename %}

```python
>>> a = benar
>>> a
Benar
```

You can also do it this way:

{% filename %}command-line{% endfilename %}

```python
>>> a = 2 > 5
>>> a
False
```

Practice and have fun with Booleans by trying to run the following commands:

- `Benar dan Benar`
- `Salah dan benar`
- `Benar atau 1 == 1`
- `1 != 2`

Congrats! Booleans are one of the coolest features in programming, and you just learned how to use them!

# Simpan itu!

> Untuk pembaca di rumah: bagian ini tercakup dalam [Dasar-dasar Python: Menyimpan file dan "Jika" pernyataan](https://www.youtube.com/watch?v=dOAg6QVAxyk) video.

So far we've been writing all our python code in the interpreter, which limits us to entering one line of code at a time. Normal programs are saved in files and executed by our programming language **interpreter** or **compiler**. So far we've been running our programs one line at a time in the Python **interpreter**. We're going to need more than one line of code for the next few tasks, so we'll quickly need to:

- Keluar dari juru bahasa Python
- Buka editor pilihan kami
- Simpan beberapa kode ke file python baru
- Menjalankannya!

To exit from the Python interpreter that we've been using, simply type the `exit()` function

{% filename %}command-line{% endfilename %}

```python
>>> exit()
$
```

This will put you back into the command prompt.

Earlier, we picked out a code editor from the [code editor](../code_editor/README.md) section. We'll need to open the editor now and write some code into a new file:

{% filename %}editor{% endfilename %}

```python
print('Hello, Django girls!')
```

Obviously, you're a pretty seasoned Python developer now, so feel free to write some code that you've learned today.

Now we need to save the file and give it a descriptive name. Let's call the file **python_intro.py** and save it to your desktop. We can name the file anything we want, but the important part here is to make sure the file ends in **.py**. The **.py** extension tells our operating system that this is a **Python executable file** and Python can run it.

> **Catatan** Anda harus memperhatikan salah satu hal yang paling keren tentang editor kode: warna! Di konsol Python, semuanya warnanya sama; Sekarang Anda harus melihat bahwa fungsi `print` adalah warna yang berbeda dari string. Ini disebut "penyorotan sintaks", dan ini adalah fitur yang sangat berguna saat mengkodekan. Warna benda akan memberi petunjuk, seperti string yang tidak ditutup atau salah ketik pada nama kata kunci (seperti ` def ` dalam sebuah fungsi, yang akan kita lihat di bawah). Inilah salah satu alasan kita menggunakan kode editor. :)

With the file saved, it's time to run it! Using the skills you've learned in the command line section, use the terminal to **change directories** to the desktop.

<!--sec data-title="Change directory: OS X" data-id="python_OSX"
data-collapse=true ces-->

On a Mac, the command will look something like this:

{% filename %}garis komando{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Linux" data-id="python_linux"
data-collapse=true ces-->

On Linux, it will be like this (the word "Desktop" might be translated to your local language):

{% filename %}garis komando{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Command Prompt" data-id="python_windows" data-collapse=true ces-->

On Windows Command Prompt, it will be like this:

{% filename %}baris perintah{% endfilename %}

    > cd %HomePath%\Deskop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Powershell" data-id="python_windowsPSH" data-collapse=true ces-->

And on Windows Powershell, it will be like this:

{% filename %}command-line{% endfilename %}

    > cd $Home\Desktop
    

<!--endsec-->

If you get stuck, just ask for help.

Now use Python to execute the code in the file like this:

{% filename %}baris-perintah{% endfilename %}

    $ python3 python_intro.py Halo, Django girls!
    

Note: on Windows 'python3' is not recognized as a command. Instead, use 'python' to execute the file:

{% filename %}command-line{% endfilename %}

```python
> python python_intro.py
```

Alright! You just ran your first Python program that was saved to a file. Feel awesome?

You can now move on to an essential tool in programming:

## Jika ... elif ... lain

Lots of things in code should be executed only when given conditions are met. That's why Python has something called **if statements**.

Replace the code in your **python_intro.py** file with this:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
```

If we were to save and run this, we'd see an error like this:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

    $ python3 python_intro.py
    File "python_intro.py", line 2
             ^
    SyntaxError: unexpected EOF while parsing
    

Python expects us to give further instructions to it which are executed if the condition `3 > 2` turns out to be true (or `True` for that matter). Let’s try to make Python print “It works!”. Change your code in your **python_intro.py** file to this:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
    print('It works!')
```

Notice how we've indented the next line of code by 4 spaces? We need to do this so Python knows what code to run if the result is true. You can do one space, but nearly all Python programmers do 4 to make things look neat. A single `tab` will also count as 4 spaces.

Save it and give it another run:

{% filename %}command-line{% endfilename %}

```python
$ python3 python_intro.py
It works!
```

Note: Remember that on Windows, 'python3' is not recognized as a command. From now on, replace 'python3' with 'python' to execute the file.

### Bagaimana jika sebuah kondisi tidak benar?

In previous examples, code was executed only when the conditions were True. But Python also has `elif` and `else` statements:

{% filename %}python_intro.py{% endfilename %}

```python
if 5 > 2:
    print('5 is indeed greater than 2')
else:
    print('5 is not greater than 2')
```

When this is run it will print out:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    5 memang lebih besar dari 2
    

If 2 were a greater number than 5, then the second command would be executed. Let's see how `elif` works:

{% filename %}python_intro.py{% endfilename %}

```python
name = 'Sonja'
if name == 'Ola':
    print('Hey Ola!')
elif name == 'Sonja':
    print('Hey Sonja!')
else:
    print('Hey anonymous!')
```

and executed:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hei Sonja!
    

See what happened there? `elif` lets you add extra conditions that run if the previous conditions fail.

You can add as many `elif` statements as you like after your initial `if` statement. For example:

{% filename %}python_intro.py{% endfilename %}

```python
volume = 57
if volume < 20:
    print("It's kinda quiet.")
elif 20 <= volume < 40:
    print("It's nice for background music")
elif 40 <= volume < 60:
    print("Perfect, I can hear all the details")
elif 60 <= volume < 80:
    print("Nice for parties")
elif 80 <= volume < 100:
    print("A bit loud!")
else:
    print("My ears are hurting! :(")
```

Python runs through each test in sequence and prints:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py Sempurna, saya bisa mendengar semua detailnya
    

## Komentar

Comments are lines beginning with `#`. You can write whatever you want after the `#` and Python will ignore it. Comments can make your code easier for other people to understand.

Let's see how that looks:

{% filename %}python_intro.py{% endfilename %}

```python
# Change the volume if it's too loud or too quiet
if volume < 20 or volume > 80:
    volume = 50
    print("That's better!")
```

You don't need to write a comment for every line of code, but they are useful for explaining why your code is doing something, or providing a summary when it's doing something complex.

### Ikhtisar

In the last few exercises you learned about:

- **comparing things** – in Python you can compare things by using `>`, `>=`, `==`, `<=`, `<` and the `and`, `or` operators
- **Boolean** - jenis objek yang hanya bisa memiliki satu dari dua nilai: `Benar` atau`Salah`
- ** Simpan file** - menyimpan kode dalam file sehingga Anda bisa menjalankan program yang lebih besar.
- **jika…elif…lain** - pernyataan yang memungkinkan Anda untuk mengeksekusi kode hanya bila kondisi tertentu terpenuhi.
- **perintah** - baris yang tidak akan dijalankan Python yang memungkinkan Anda mendokumentasikan kode Anda

Time for the last part of this chapter!

## Fungsi anda sendiri

> Bagi pembaca di rumah: bagian ini tercakup dalam video [Python Basics: Functions](https://www.youtube.com/watch?v=5owr-6suOl0) video.

Remember functions like `len()` that you can execute in Python? Well, good news – you will learn how to write your own functions now!

A function is a sequence of instructions that Python should execute. Each function in Python starts with the keyword `def`, is given a name, and can have some parameters. Let's give it a go. Replace the code in **python_intro.py** with the following:

{% filename %}python_intro.py{% endfilename %}

```python
def hi():
    print('Hi there!')
    print('How are you?')

hi()
```

Okay, our first function is ready!

You may wonder why we've written the name of the function at the bottom of the file. This is because Python reads the file and executes it from top to bottom. So in order to use our function, we have to re-write it at the bottom.

Let's run this now and see what happens:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi there!
    How are you?
    

Note: if it didn't work, don't panic! The output will help you to figure why:

- Jika Anda mendapatkan `kesalahan nama`, itu mungkin berarti Anda mengetikkan sesuatu yang salah, jadi Anda harus memeriksa bahwa Anda menggunakan nama yang sama saat membuat fungsi dengan `def hi():` dan kapan memanggilnya dengan `hi()`.
- Jika Anda mendapatkan `IndentationError`, periksalah bahwa kedua baris `cetak` memiliki spasi yang sama di awal baris: python menginginkan semua kode di dalam fungsi disesuaikan dengan rapi.
- Jika tidak ada output sama sekali, periksa apakah yang terakhir `hi()` *tidak* indentasi - jika memang demikian, baris itu juga akan menjadi bagian dari fungsi, dan itu akan tidak pernah lari.

Let's build our first function with parameters. We will use the previous example – a function that says 'hi' to the person running it – with a name:

{% filename %}python_intro.py{% endfilename %}

```python
def hi (nama):
```

As you can see, we now gave our function a parameter that we called `name`:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    if name == 'Ola':
        print('Hi Ola!')
    elif name == 'Sonja':
        print('Hi Sonja!')
    else:
        print('Hi anonymous!')

hi()
```

Remember: The `print` function is indented four spaces within the `if` statement. This is because the function runs when the condition is met. Let's see how it works now:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

    $ python3 python_intro.py
    Traceback (most recent call last):
    File "python_intro.py", line 10, in <module>
      hi()
    TypeError: hi() missing 1 required positional argument: 'name'
    

Oops, an error. Luckily, Python gives us a pretty useful error message. It tells us that the function `hi()` (the one we defined) has one required argument (called `name`) and that we forgot to pass it when calling the function. Let's fix it at the bottom of the file:

{% filename %}python_intro.py{% endfilename %}

```python
hi("Ola")
```

And run it again:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Ola!
    

And if we change the name?

{% filename %}python_intro.py{% endfilename %}

```python
hi("Sonja")
```

And run it:

{% filename %} baris perintah {% endfilename %}

    $ python3 python_intro.py
    Hi Sonja!
    

Now, what do you think will happen if you write another name in there? (Not Ola or Sonja.) Give it a try and see if you're right. It should print out this:

{% filename %}command-line{% endfilename %}

    Hai anonim!
    

This is awesome, right? This way you don't have to repeat yourself every time you want to change the name of the person the function is supposed to greet. And that's exactly why we need functions – you never want to repeat your code!

Let's do something smarter – there are more names than two, and writing a condition for each would be hard, right?

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    print('Hi ' + name + '!')

hi("Rachel")
```

Let's call the code now:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Rachel!
    

Congratulations! You just learned how to write functions! :)

## Loops

> Bagi pembaca di rumah: bagian ini tercakup dalam [Dasar-dasar Python: Untuk video Loop](https://www.youtube.com/watch?v=aEA6Rc86HF0).

This is the last part already. That was quick, right? :)

Programmers don't like to repeat themselves. Programming is all about automating things, so we don't want to greet every person by their name manually, right? That's where loops come in handy.

Still remember lists? Let's do a list of girls:

{% filename %}python_intro.py{% endfilename %}

```python
girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
```

We want to greet all of them by their name. We have the `hi` function to do that, so let's use it in a loop:

{% filename %}python_intro.py{% endfilename %}

```python
untuk nama pada anak perempuan:
```

The `for` statement behaves similarly to the `if` statement; code below both of these need to be indented four spaces.

Here is the full code that will be in the file:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    print('Hi ' + name + '!')

girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
for name in girls:
    hi(name)
    print('Next girl')
```

And when we run it:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Rachel!
    Next girl
    Hi Monica!
    Next girl
    Hi Phoebe!
    Next girl
    Hi Ola!
    Next girl
    Hi You!
    Next girl
    

As you can see, everything you put inside a `for` statement with an indent will be repeated for every element of the list `girls`.

You can also use `for` on numbers using the `range` function:

{% filename %}python_intro.py{% endfilename %}

```python
untuk saya di kisaran (1, 6):
    cetak(i)
```

Which would print:

{% filename %}command-line{% endfilename %}

    1
    2
    3
    4
    5
    

`range` is a function that creates a list of numbers following one after the other (these numbers are provided by you as parameters).

Note that the second of these two numbers is not included in the list that is output by Python (meaning `range(1, 6)` counts from 1 to 5, but does not include the number 6). That is because "range" is half-open, and by that we mean it includes the first value, but not the last.

## Ikhtisar

That's it. **You totally rock!** This was a tricky chapter, so you should feel proud of yourself. We're definitely proud of you for making it this far!

For official and full python tutorial visit https://docs.python.org/3/tutorial/. This will give you a more thorough and complete study of the language. Cheers :)

You might want to briefly do something else – stretch, walk around for a bit, rest your eyes – before going on to the next chapter. :)

![Cupcake](images/cupcake.png)