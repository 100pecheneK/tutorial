# Tampilan Django - waktu untuk membuat!

Waktunya menyingkirkan bug yang kita buat di bab terakhir! :)

A * view </ 0> adalah tempat kita meletakkan "logika" aplikasi kita. Ini akan meminta informasi dari ` Model </ 0> Anda buat sebelumnya dan menyebarkannya ke <code> Template </ 0> . Kami akan membuat template di bab berikutnya. View hanyalah berupa fungsi Python tetapi lebih kompleks dibandingkan dengan yang telah kita buat pada bab <strong>Pengenalan Pada Python</strong>.</p>

<p>Penayangan ditempatkan di file <code> views.py </ 0> . Kami akan menambahkan <em> tampilan </ 1> ke file <code> blog / views.py </ 0> .</p>

<h2>blog / views.py</h2>

<p>OK, let's open up this file in our code editor and see what's in there:</p>

<p>{% filename%} blog / views.py {% endfilename%}</p>

<pre><code class="python">from django.shortcuts import render

# Create your views here.
`</pre> 

Belum banyak perintah di sini.

Ingat bahwa baris yang dimulai dengan ` # </ 0> adalah komentar - ini berarti bahwa baris tersebut tidak akan dijalankan oleh Python.</p>

<p>Mari buat <em> lihat </ 0> seperti yang disarankan oleh komentar. Tambahkan tampilan minimal berikut di bawah ini:</p>

<p>{% filename%} blog / views.py {% endfilename%}</p>

<pre><code class="python">def post_list(request):
    return render(request, 'blog/post_list.html', {})
`</pre> 

As you can see, we created a function (`def`) called `post_list` that takes `request` and will `return` the value it gets from calling another function `render` that will render (put together) our template `blog/post_list.html`.

Simpan filenya, pergi ke http://127.0.0.1:8000/ dan lihat apa yang kita punya.

Kesalahan lain Baca apa yang terjadi sekarang:

![Kesalahan](images/error.png)

Ini memperlihatkan bahwa server berjalan lagi, paling tidak, tapi masih kelihatan belum betul, betul? Jangan khawatir, itu hanyalah halaman error, tak ada yang perlu ditakutkan! Sama seperti pesan error di dalam konsol, hal tersebut sangat berguna. Anda dapat membaca *TemplateDoesNotExist*. Mari perbaiki bug ini dan membuat sebuah template pada bab berikutnya!

> Learn more about Django views by reading the official documentation: https://docs.djangoproject.com/en/2.0/topics/http/views/