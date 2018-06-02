> Bagian dari bagian ini didasarkan pada tutorial oleh Geek Girls Wortel (https://github.com/ggcarrots/django-carrots).
> 
> Bagian dari bagian ini didasarkan pada tutorial  Django-marcador </ 0> yang berlisensi di bawah Lisensi Internasional Creative Commons Attribution-ShareAlike 4.0. Hak cipta tutorial django-marcador oleh Markus Zapke-Gründemann et al.</p> </blockquote> 
> 
> ## Virtual Environment
> 
> Sebelum kita menginstal django kami akan mengajari anda untuk menginstall tool yang sangat penting yang akan menjaga lingkungan pengembangan anda teratur di komputer anda. Dimungkinkan untuk melewati bagian ini, tapi sangat dianjurkan untuk tidak melewatinya. Dimulai dengan setup sebaik mungkin akan menghindarkan anda dari banyak kesulitan di masa yang akan datang.
> 
> Karena itu, mari membuat sebuah **virtual environment** (juga disebut *virtualenv*). Virtualenv akan memisahkan setup Python/Django untuk tiap proyek. Ini artinya bahwa suatu perubahan yang anda buat pada sebuah website, tidak akan mempengaruhi website lain yang juga sedang anda kembangkan. Jelas bukan ?
> 
> Yang perlu anda kerjakan adalah menemukan sebuah direktory dimana anda ingin menciptakan `virtualenv`, yaitu home directory anda, ini sebagai misal. Pada Windows, mungkin terlihat seperti `C:\Users \ Name` (dimana`Nama` merupakan nama login anda).
> 
> > **CATATAN: ** Pada Windows, pastikan petunjuk ini tidak mengandung karakter beraksen atau karakter khusus; Jika nama pengguna anda mengandung karakter beraksen, gunakan petunjuk yang berbeda, misalnya, `C:\ jangogirls`.
> 
> Karena tutorial ini akan menggunakan sebuah direktory baru yaitu `djangogirls`, dari home direktory anda:
> 
> {% filename%} baris perintah {% endfilename%}
> 
>     $ mkdir djangogirls $ cd djangogirls
>     
> 
> Kita akan membuat sebuah virtualenv dengan nama `myenv`. Bentuk perintah umumnya seperti ini:
> 
> {% filename%} baris perintah {% endfilename%}
> 
>     $ python3 -m venv myvenv
>     
> 
> <!--sec data-title="Virtual environment: Windows" data-id="virtualenv_installation_windows"
data-collapse=true ces-->
> 
> Untuk membuat new ` virtualenv </ 0> , Anda perlu membuka command prompt dan menjalankan <code> python -m venv myvenv </ 0> . Ini akan terlihat seperti ini:</p>

<p>{% filename%} baris perintah {% endfilename%}</p>

<pre><code>C: \ Users \ Name \ djangogirls & gt; python -m venv myvenv
`</pre> 
> 
> Dimana ` myvenv </ 0> adalah nama <code> virtualenv </ 0> Anda . Anda boleh menggunakan nama yang lain, tapi harus menggunakan huruf kecil dan tanpa spasi, karakter khusus ataupun tanda petik. Ini juga ide bagus untuk menjaga agar nama tetap pendek - Anda akan sering merujuknya!</p>

<!--endsec-->


> 
> <!--sec data-title="Virtual environment: Linux and OS X" data-id="virtualenv_installation_linuxosx"
data-collapse=true ces-->

<p>Kita bisa menciptakan <code>virtualenv`pada Linux dan OS X dengan menjalankan 
> 
> `python3 -m venv myvenv`. Ini akan terlihat seperti ini:
> 
> {% filename%} baris perintah {% endfilename%}
> 
>     $ python3 -m venv myvenv
>     
> 
> `myvenv` adalah nama dari `virtualenv` anda. Anda dapat menggunakan nama lain akan tetapi tetap gunakan huruf kecil dan tanpa spasi. Ini juga merupakan ide yang baik untuk menjaga agar nama tetap singkat seperti yang akan anda rujuk secara banyak!
> 
> > ** CATATAN: </ 0> Pada beberapa versi Debian / Ubuntu Anda mungkin menerima error berikut:</p> 
> > 
> > {% filename%} baris perintah {% endfilename%}
> > 
> >     Lingkungan virtual tidak berhasil dibuat karena ensurepip tidak tersedia.  Pada sistem Debian / Ubuntu, Anda perlu menginstal paket python3-venv menggunakan perintah berikut.
> >        apt install python3-venv
> >     You may need to use sudo with that command.  Setelah menginstal paket python3-venv, buat ulang lingkungan virtual Anda.
> >     
> > 
> > Dalam kasus ini, ikuti petunjuk di atas dan pasang paket ` python3-venv </ 0> :
 {% filename%} command-line {% endfilename%}  </p>

<pre><code>$ sudo apt install python3-venv
`</pre> 
> > 
> > ** CATATAN: </ 0> Pada beberapa versi Debian / Ubuntu yang memulai lingkungan virtual seperti saat ini memberikan error berikut:</p> 
> > 
> > {% filename %}baris perintah{% endfilename %}
> > 
> >     Error: Command '['/home/eddie/Slask/tmp/venv/bin/python3', '-Im', 'ensurepip', '--upgrade', '--default-pip']' returned non-zero exit status 1
> >     
> > 
> > Untuk mengatasi hal ini, gunakan perintah `virtualenv`.
> > 
> > {% filename%} baris perintah {% endfilename%}
> > 
> >     $ sudo apt install python-virtualenv
> >     $ virtualenv --python=python3.6 myvenv
> >     
> > 
> > ** CATATAN: </ 0> Jika Anda mengalami error seperti</p> 
> > 
> > {% filename%} baris perintah {% endfilename%}
> > 
> >     E: Tidak dapat menemukan paket python3-venv
> >     
> > 
> > lalu jalankan:
> > 
> > {% filename%} baris perintah {% endfilename%}
> > 
> >     sudo apt install python3.6-venv
> >     </blockquote> 
> > 
> > <!--endsec-->
> > 
> > ## Bekerja Dengan Virtualenv
> > 
> > Perintah di atas akan meciptakan sebuah direktori dengan nama `myvenv` (atau nama apa saja yang anda pilih) yang berisi virtual environment kita (jelasnya berisi banyak file dan direktori).
> > 
> > <!--sec data-title="Working with virtualenv: Windows" data-id="virtualenv_windows"
data-collapse=true ces-->
> > 
> > Aktifkan virtual environment anda dengan menjalankan:
> > 
> > {% filename%} baris perintah {% endfilename%}
> > 
> >     C: \ Users \ Name \ djangogirls & gt; myvenv \ Scripts \ activate
> >     
> > 
> > > ** CATATAN: </ 0> pada Windows 10 Anda mungkin mendapatkan pesan kesalahan pada Windows PowerShell yang mengatakan bahwa ` eksekusi skrip dinonaktifkan pada sistem ini </ 1> . Dalam kasus ini, buka Windows PowerShell lainnya dengan opsi "Run as Administrator".  Kemudian coba ketikkan perintah berikut sebelum memulai lingkungan virtual Anda:</p>
  
  <p>{% filename%} baris perintah {% endfilename%}</p>

<pre><code>C: \ WINDOWS \ system32 & gt; Set-ExecutionPolicy -ExecutionPolicy     Perubahan Kebijakan Eksekusi RemoteSigned
 Kebijakan
     eksekusi membantu melindungi Anda dari skrip yang tidak Anda percaya. Mengubah kebijakan eksekusi mungkin akan memaparkan risiko keamanan yang dijelaskan di topik bantuan about_Execution_Policies di http://go.microsoft.com/fwlink/?LinkID=135170. Apakah Anda ingin mengubah kebijakan eksekusi? [Y] Ya   [A] Ya untuk Semua   [N] Tidak   [L] Tidak untuk Semua   [S] Suspend [?] Help (defaultnya adalah "N"): A
`</pre> </blockquote> 
> > > 
> > > <!--endsec-->
> > > 
> > > <!--sec data-title="Working with virtualenv: Linux and OS X" data-id="virtualenv_linuxosx"
data-collapse=true ces-->
> > > 
> > > Aktifkan virtual environment anda dengan menjalankan:
> > > 
> > > {% filename%} baris perintah {% endfilename%}
> > > 
> > >     $ source myvenv / bin / aktifkan
> > >     
> > > 
> > > Ingat untuk mengganti `myvenv` dengan nama pilihan anda `virtualenv` name!
> > > 
> > > > **CATATAN:** kadang-kadang `source` tidak tersedia. Kalau anda menghadapi masalah tersebut coba ini:
> > > > 
> > > > {% filename%} baris perintah {% endfilename%}
> > > > 
> > > >     $. myvenv / bin / aktifkan
> > > >     
> > > 
> > > <!--endsec-->
> > > 
> > > Anda akan tahu bahwa Anda memiliki ` virtualenv </ 0> dimulai saat Anda melihat bahwa prompt di konsol Anda diawali dengan <code> (myvenv) </ 0> .</p>

<p>Ketika anda bekerja dalam sebuah virtual environment, <code>python` akan otomatis mengacu pada versi yang benar sehingga anda dapat menggunakan perintah `python` bukannya `python3`.
> > > 
> > > Oke, kita telah memiliki semua dipendensi penting pada tempatnya. Pada akhirnya kita dapat mengintal django.
> > > 
> > > ## Menginstall Django
> > > 
> > > Sekarang setelah ` virtualenv </ 0> dimulai, Anda bisa menginstal Django.</p>

<p>Sebelum kita melakukan itu, kita harus memastikan bahwa kita memiliki versi terbaru <code> pip </ 0> , perangkat lunak yang kita gunakan untuk menginstal Django:</p>

<p>{% filename%} baris perintah {% endfilename%}</p>

<pre><code>(myvenv) ~$ python3 -m pip install --upgrade pip
`</pre> 
> > > 
> > > Kemudian jalankan ` pip install django ~ = 1.11.0 </ 0> (perhatikan bahwa kita menggunakan tilde diikuti dengan tanda yang sama: <code> ~ = </ 0> ) untuk menginstal Django.</p>

<p>{% filename%} baris perintah {% endfilename%}</p>

<pre><code>(myvenv) ~ $ pip install django ~ = 1.11.0 Mengumpulkan Django ~ = 1.11.0
   Men-download Django-1.11.3-py2.py3-none-any.whl (6.8MB) Menginstal paket yang dikumpulkan: Django Berhasil menginstal Django-1.11 .3
`</pre> <!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->
> > > 
> > > > Jika Anda mendapatkan pesan kesalahan saat memanggil pip pada platform Windows, periksa apakah pathname proyek Anda berisi spasi, aksen atau karakter khusus (misalnya, ` C: \ Users \ User Name \ djangogirls </ 0> ). Jika ya, mohon pertimbangkan untuk menggunakan tempat lain tanpa spasi, aksen atau karakter khusus (saran: <code> C: \ djangogirls </ 0> ). Buat virtualenv baru di direktori baru, lalu hapus yang lama dan coba perintah di atas lagi. (Memindahkan direktori virtualenv tidak akan berfungsi karena virtualenv menggunakan path absolut.)</p>
</blockquote>

<!--endsec-->


> > > > 
> > > > <!--sec data-title="Installing Django: Windows 8 and Windows 10" data-id="django_err_windows8and10"
data-collapse=true ces-->

<blockquote>
  <p>Baris perintah Anda mungkin membeku setelah Anda mencoba menginstal Django. Jika ini terjadi, alih-alih penggunaan perintah di atas:</p>
  
  <p>{% filename%} baris perintah {% endfilename%}</p>

<pre><code>C: \ Users \ Name \ djangogirls & gt; python -m pip install django ~ = 1.11.0
`</pre> </blockquote> 
> > > > 
> > > > <!--endsec-->
> > > > 
> > > > <!--sec data-title="Installing Django: Linux" data-id="django_err_linux"
data-collapse=true ces-->
> > > > 
> > > > > Jika anda mengalami error saat memanggil pip pada Ubuntu 12.04 silahkan jalankan code berikut `python -m pip install -U --force-reinstall pip` untuk memperbaiki instalasi pip pada cirtualenv.
> > > > 
> > > > <!--endsec-->
> > > > 
> > > > Itu dia! Akhirnya sekarang anda telah membuat aplikasi Django!