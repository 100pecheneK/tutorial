{% set warning_icon = '<span class="glyphicon glyphicon-exclamation-sign" style="color: red;" aria-hidden="true" data-toggle="tooltip" title="An error is expected when you run this command!" ></span>' %}

# Uvod u Python

> Dio ovoga poglavlja temelji se na tutorijalima Geek Girls Carrots-a (https://github.com/ggcarrots/django-carrots).

Idemo nešto kodirati!

## Pythonov prompt

> Za čitatelje kod kuće: ovaj je dio pokriven u [Python Basics: Integers, Strings, Lists, Variables and Errors](https://www.youtube.com/watch?v=MO63L4s-20U) videu.

Kako bismo se počeli igrati s Pythonom, moramo otvoriti *naredbeni redak*. To ne bi trebao biti problem - učili smo to u poglavlju [Uvod u naredbeni redak](../intro_to_command_line/README.md).

Kada si spremna, prati sljedeće upute.

Želimo otvoriti Python konzolu. Upiši `python` ako si na Windowsima, a `python3` na Mac OS/Linuxu i pritisni `enter`.

{% filename %}command-line{% endfilename %}

    $ python3
    Python 3.6.1 (...)
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    

## Tvoja prva Python naredba!

Nakon što smo pokrenuli naredbu Python, prompt se promijenio u `>>>`. Nama to znači da za sada smijemo koristiti samo naredbe jezika Python. Ne moraš utipkati `>>>` - Python će to činiti za tebe.

Ako u bilokojem trenutku poželiš izaći iz Pythonove konzole, samo utipkaj `exit()` ili iskoristi prečac `Ctrl + Z` na Windowsima, tj. `Ctrl + D` na Macu/Linuxu. Tada više nećeš vidjeti `>>>`.

Za sada ne želimo izaći iz Pythonove konzole, već želimo naučiti više o njoj. Započnimo tipkanjem malo matematike, npr. `2 + 3`, i pritiskanjem `enter`-a.

{% filename %}command-line{% endfilename %}

```python
>>> 2 + 3
5
```

Super! Vidiš kako je odgovor iskočio? Python zna matematiku! Možeš isprobati druge naredbe poput:

- `4 * 5`
- `5 - 1`
- `40 / 2`

Za izvođenje eksponencijalnog računa, recimo 2 na eksponent 3, pišemo: {% filename %}command-line{% endfilename %}

```python
>>> 2 ** 3
8
```

Prvo se malo zabavljaj s ovime, a onda se vrati ovdje. :)

Kao što vidiš, Python je odličan kalkulator. Ako se pitaš što još možeš raditi…

## Stringovi (znakovni nizovi)

Što kažeš na svoje ime? Upiši svoje ime ovako u navodne znakove:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola"
'Ola'
```

Sada je stvoren tvoj prvi string! String je slijed znakova koji računalo može obraditi. On uvijek mora započeti i završiti istim znakom. Taj znak može biti ili jednostruki (`'`) ili dvostruki (`"`) navodni znak (nema razlike!). Navodnici govore Pythonu da je ono između njih string.

Stringovi mogu biti nanizani zajedno. Isprobaj ovo:

{% filename %}command-line{% endfilename %}

```python
>>> "Hi there " + "Ola"
'Hi there Ola'
```

Također možeš množiti stringove brojem:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola" * 3
'OlaOlaOla'
```

Ako moraš staviti apostrof u svoj string, postoje dva načina na koja to možeš učiniti.

Koristeći dvostruke navodnike:

{% filename %}command-line{% endfilename %}

```python
>>> "Runnin' down the hill"
"Runnin' down the hill"
```

ili zanemarujući taj apostrof kosom crtom unazad (`"`):

{% filename %}command-line{% endfilename %}

```python
>>> 'Runnin\' down the hill'
"Runnin' down the hill"
```

Fora, zar ne? Da vidiš svoje ime napisano velikim slovima, jednostavno utipkaj:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola".upper()
'OLA'
```

Upravo si pozvala `upper` **metodu** na svom stringu! Metoda (poput `upper()`) je niz instrukcija koje Python mora izvesti nad danim objektom (`"Ola"`) kada ju pozoveš.

Ako želiš znati koliko slova ima tvoje ime, postoji **funkcija** i za to!

{% filename %}command-line{% endfilename %}

```python
>>> len("Ola")
3
```

Pitaš se zašto ponekad zoveš funkcije s `.` na kraju stringa (`"Ola".upper()`), a ponekad prvo pozoveš funkciju i staviš string u zagrade? Pa, u nekim slučajevima funkcije pripadaju objektima, poput `upper()` koja se može izvesti samo nad stringovima. U tom slučaju, funkcije nazivamo **metodama**. U drugim trenutcima funkcije ne pripadaju ničemu određenom te mogu biti korištene s različitim vrstama objekata kao, na primjer, `len()`. Zbog toga funkciji `len()` prosljeđujemo `"Ola"` kao parametar.

### Sažetak

OK, dosta stringova. Do sad je naučeno:

- **prompt** - tipkanje naredaba (koda) u Pythonov prompt rezultira odgovorima u Pythonu
- **brojevi i stringovi** - u Pythonu brojevi se koriste za matematiku, a stringovi za tekstualne objekte
- **operatori** - poput `+` i `*`, kombiniraju vrijednosti radi stvaranja nove
- **funkcije** - poput `upper()` i `len()`, izvode radnje na objektima.

Ovo su osnove svakog programskog jezika koji učiš. Spremna za nešto teže? Kladimo se da jesi!

## Greške

Idemo isprobati nešto novo. Možemo li dobiti duljinu broja na jednak način na koji smo mogli saznali duljinu našega imena? Utipkaj `len(304023)` i pritisni `enter`:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

Dobili smo našu prvu grešku! Ikona {{ warning_icon }} je naš način najavljivanja tebi da kod koji se spremaš pokrenuti neće raditi kako očekuješ. Pravljenje grešaka (čak i namjernih) bitan je dio učenja!

Piše da objekti tipa "int" (integers, cijeli brojevi) nemaju duljinu. I što sada? Možda možemo napisati naš broj kao string; stringovi imaju duljinu, zar ne?

{% filename %}command-line{% endfilename %}

```python
>>> len(str(304023))
6
```

Radi! Iskoristili smo `str()` funkciju unutar `len()` funkcije. `str()` pretvara sve u stringove.

- `str()` funkcija pretvara stvari u **stringove**
- `int()` funkcija pretvara stvari u **cijele brojeve (integers)**

> Bitno: brojeve možemo pretvoriti u tekst, no ne moramo nužno moći pretvoriti tekst u brojeve - što bi `int("hello")` uopće bilo?

## Varijable

Bitan koncept u programiranju su varijable. Varijabla nije ništa više nego ime za nešto pomoću kojega to nešto možeš poslije koristiti. Programeri koriste varijable za spremanje podataka, osiguranje čitljivosti koda te kako ne bi morali stalno pamtiti koja im vrijednost sljedeća treba.

Recimo da želimo stvoriti novu varijablu nazvanu `name`:

{% filename %}command-line{% endfilename %}

```python
>>> name = "Ola"
```

Utipkamo name jednako Ola.

Kao što si primijetila, tvoj program nije ništa vratio kao što je to prije činio. Kako onda znamo da varijabla zaista postoji? Jednostavno upiši `name` i pritisni `enter`:

{% filename %}command-line{% endfilename %}

```python
>>> name
'Ola'
```

Jupii! Tvoja prva varijabla! :) Uvijek možeš promijeniti na što se ona odnosi:

{% filename %}command-line{% endfilename %}

```python
>>> name = "Sonja"
>>> name
'Sonja'
```

Možeš ju također koristiti u funkcijama:

{% filename %}command-line{% endfilename %}

```python
>>> len(name)
5
```

Super, zar ne? Naravno, varijable mogu bili bilo što - pa i brojevi! Pokušaj ovo:

{% filename %}command-line{% endfilename %}

```python
>>> a = 4
>>> b = 6
>>> a * b
24
```

Ali što ako smo iskoristili krivo ime? Možeš li pogoditi što bi se dogodilo? Isprobajmo!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> city = "Tokyo"
>>> ctiy
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'ctiy' is not defined
```

Greška! Ko što vidiš, Python ima različite vrste grešaka, a ova se zove **NameError**. Python će ti javiti ovu grešku ako pokušaš koristiti varijablu koja još nije definirana. Ako se kasnije susretneš s ovom greškom, provjeri svoj kod da vidiš imaš li krivo napisanih imena.

Igraj se s ovime neko vrijeme i vidi što sve možeš raditi!

## Funkcija print

Isprobaj ovo:

{% filename %}command-line{% endfilename %}

```python
>>> name = 'Maria'
>>> name
'Maria'
>>> print(name)
Maria
```

Kada upišeš samo `name`, Pythonov prevoditelj odgovara sa stringovskom *reprezentacijom* varijable 'name', a ona je slova M-a-r-i-a omeđena jednostrukim navodnicima, '. Kada napišeš `print(name)`, Python ispiše ("printa") sadržaj varijable na zaslon, ali bez navodnika, što je urednije.

Kao što ćemo kasnije vidjeti, `print()` je također koristan kada želimo ispisati stvari iz funkcija ili kada želimo ispis u više linija.

## Liste

Osim stringova i cijelih brojeva, Python ima svakakve razne vrste objekata. Sada ćemo predstaviti jednu zvanu **lista**. Liste su točno ono što misliš da jesu: objekti koji su liste drugih objekata. :)

Hajde napravi listu:

{% filename %}command-line{% endfilename %}

```python
>>> []
[]
```

Da, ova je lista prazna. Nije baš korisno, zar ne? Idemo napraviti listu brojeva lota. Ne želimo se cijelo vrijeme ponavljati pa ćemo listu staviti u varijablu:

{% filename %}command-line{% endfilename %}

```python
>>> lottery = [3, 42, 12, 19, 30, 59]
```

Uredu, imamo listu! Što možemo raditi s njom? Idemo vidjeti koliko loto brojeva ima u listi. Imaš li ikakvu ideju koju bi funkciju trebalo iskoristiti za to? Znaš to već!

{% filename %}command-line{% endfilename %}

```python
>>> len(lottery)
6
```

Da! `len()` ti može dati broj objekata u listi. Korisno, zar ne? Možda ćemo ju sada sortirati:

{% filename %}command-line{% endfilename %}

```python
>>> lottery.sort()
```

Ovo ništa ne vraća, samo je promijenilo redoslijed u kojem se brojevi pojavljuju u listi. Idemo ju opet ispisati i vidjeti što se dogodilo:

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery)
[3, 12, 19, 30, 42, 59]
```

Kao što možeš vidjeti, brojevi u tvojoj listi sada su sortirani od najniže prema najvišoj vrijednosti. Čestitamo!

Možda želimo obrnuti taj redoslijed? Idemo to napraviti!

{% filename %}command-line{% endfilename %}

```python
>>> lottery.reverse()
>>> print(lottery)
[59, 42, 30, 19, 12, 3]
```

Ako želiš nešto dodati u svoju listu, možeš to upisivanjem iduće naredbe:

{% filename %}command-line{% endfilename %}

```python
>>> lottery.append(199)
>>> print(lottery)
[59, 42, 30, 19, 12, 3, 199]
```

Ako želiš prikazati samo prvi broj, možeš to učiniti korištenjem **indeksa**. Indeks je broj koji govori gdje se u listi nalazi neki objekt. Programeri radije započinju brojanje krenuvši od 0, tako da je prvi objekt u tvojoj listi na indeksu 0, sljedeći je na 1, itd. Isprobaj ovo:

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery[0])
59
>>> print(lottery[1])
42
```

Kao što možeš vidjeti, možeš pristupiti različitim objektima u svojoj listi korištenjem imena liste i indeksa traženog objekta unutar uglatih zagrada.

Za brisanje nečega iz svoje liste morat ćeš koristiti **indekse** o kojima smo gore naučili te `pop()` metodu. Idemo isprobati jedan primjer i učvrstiti prethodno stečeno znanje; brisat ćemo prvi broj iz naše liste.

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery)
[59, 42, 30, 19, 12, 3, 199]
>>> print(lottery[0])
59
>>> lottery.pop(0)
59
>>> print(lottery)
[42, 30, 19, 12, 3, 199]
```

That worked like a charm!

Za dodatnu zabavu, isprobajte neke druge indekse: 6, 7, 1000, -1, -6 ili -1000. Vidi možeš li predvidjeti rezultat prije isprobavanja naredbe. Imaju li ti rezultati smisla?

Popis svih metoda za liste koje su na raspolaganju možeš pronaći u ovom poglavlju Pythonove dokumentacije: https://docs.python.org/3/tutorial/datastructures.html

## Rječnici

> Za čitatelje kod kuće: ovaj je dio pokriven u [Python Basics: Dictionaries](https://www.youtube.com/watch?v=ZX1CVvZLE6c) videu.

Rječnik je sličan listi, ali vrijednosti dohvaćaš tražeći ključ umjesto numeričkog indeksa. Ključ može biti bilokoji string ili broj. Sintaksa za definiranje praznoga rječnika je:

{% filename %}command-line{% endfilename %}

```python
>>> {}
{}
```

To pokazuje da je upravo stvoren prazan rječnik. Hura!

Sada pokušaj napisati iduću naredbu (također pokušaj zamijeniti svojim informacijama):

{% filename %}command-line{% endfilename %}

```python
>>> participant = {'name': 'Ola', 'country': 'Poland', 'favorite_numbers': [7, 42, 92]}
```

Ovom naredbom stvorena je varijabla `participant` s tri para ključ-vrijednost:

- Ključ `name` pokazuje na vrijednost `'Ola'` (`string` objekt),
- `country` pokazuje na `'Poland'` (još jedan `string`),
- a `favorite_numbers` pokazuje na `[7, 42, 92]` (`lista` s tri broja).

Možeš provjeriti sadržaj individualnih ključeva idućom sintaksom:

{% filename %}command-line{% endfilename %}

```python
>>> print(participant['name'])
Ola
```

Vidiš, slično je listi. Ali ne moraš pamtiti indeks - samo ključ.

Što se dogodi ako pitamo Python vrijednost nepostojećega ključa? Možeš li pogoditi? Idemo probati i vidjeti!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> participant['age']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'age'
```

Vidi, još jedna greška! Ova je **KeyError** - Python je koristan i kaže ti da ključ `'age'` ne postoji u ovom rječniku.

Kada bi se trebao koristiti rječnik, a kada lista? To je dobro pitanje za promišljanje. Imaj nekakvo rješenje na umu prije nego što pogledaš odgovor u sljedećem retku.

- Trebaš li samo poredani niz stvari? Odaberi listu.
- Trebaš li povezati vrijednosti sa ključevima kako bi se poslije efikasno moglo pretraživati pomoću ključa? Odaberi rječnik.

Rječnici, poput list, su *promjenjivi*, što znači da ih se može promijeniti nakon što su stvoreni. Možeš dodati novi ključ-vrijednost par u rječnik poslije stvaranja, i to ovako:

{% filename %}command-line{% endfilename %}

```python
>>> participant['favorite_language'] = 'Python'
```

Kao kod listi, korištenje `len()` metode na rječnicima vraća broj ključ-vrijednost parova u rječniku. Hajde utipkaj iduću naredbu:

{% filename %}command-line{% endfilename %}

```python
>>> len(participant)
4
```

Nadam se da sve do sada ima smisla. :) Spremna za još malo zabave s rječnicima? Čitaj dalje za neke nevjerojatne stvari.

Možeš koristiti `pop()` metodu za brisanje stvari iz rječnika. Recimo da želiš pobrisati unos koji odgovara ključu `'favorite_numbers'`. Samo upišeš sljedeću naredbu:

{% filename %}command-line{% endfilename %}

```python
>>> participant.pop('favorite_numbers')
[7, 42, 92]
>>> participant
{'country': 'Poland', 'favorite_language': 'Python', 'name': 'Ola'}
```

Kao što možeš vidjeti iz ispisa, par ključ-vrijednost koji pripada 'favorite_numbers' ključu je pobrisan.

Osim toga, možeš i promijeniti vrijednost povezanu s već postojećim ključem u rječniku. Napiši ovo:

{% filename %}command-line{% endfilename %}

```python
>>> participant['country'] = 'Germany'
>>> participant
{'country': 'Germany', 'favorite_language': 'Python', 'name': 'Ola'}
```

Kao što vidiš, vrijednost ključa `'country'` je promijenjena iz `'Poland'` u `'Germany'` . :) Uzbudljivo? Hura! Upravo si naučila još jednu nevjerojatnu stvar.

### Sažetak

Odlično! Sada znaš mnogo o programiranju. U ovom je zadnjem dijelu naučeno:

- **greške** - sada znaš kako čitati i razumjeti greške koje se pojavljuju ako Python ne razumije dobivenu naredbu
- **varijable** - imena za objekte, omogućuju ti lakše kodiranje i da ti kod bude što čitljiviji
- **liste** - liste objekata spremljene u određenom redoslijedu
- **rječnici** - objekti spremljeni kao parovi ključ-vrijednost

Uzbuđena za nastavak? :)

## Uspoređivanje stvari

> Za čitatelje kod kuće: ovaj je dio pokriven u [Python Basics: Comparisons](https://www.youtube.com/watch?v=7bzxqIKYgf4) videu.

Velik dio programiranja uključuje uspoređivanje stvari. Što je najjednostavnije za usporediti? Brojevi, naravno. Idemo vidjeti kako to funkcionira:

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

Dali smo Pythonu neke brojeve za usporedbu. Kao što vidiš, Python ne samo da može usporediti brojeve, već može uspoređivati i rezultate metoda. Super, zar ne?

Pitaš li se zašto smo stavili dva znaka jednakosti `==` jedan pored drugog za usporedbu jednakosti brojeva? Koristimo jednostruki `=` za dodijeljivanje vrijednosti varijablama. Uvijek, **uvijek** moraš staviti dva znaka - `==` - ako želiš provjeriti jesu li dvije stvari jednake. Također možemo reći da su stvari različite. Za to koristimo simbol `!=` kao što je prikazano u gornjem primjeru.

Daj Pythonu još dva zadatka:

{% filename %}command-line{% endfilename %}

```python
>>> 6 >= 12 / 2
True
>>> 3 <= 2
False
```

Vidjeli smo `>` i `<`, ali što znače `>=` i `<=`? Čitaj ih ovako:

- x `>` y znači: x je veći od y
- x `<` y znači: x je manji od y
- x `<=` y znači: x je manji od ili jednak y
- x `>=` y znači: x je veći od ili jednak y

Odlično! Želiš li još jedan zadatak? Probaj ovo:

{% filename %}command-line{% endfilename %}

```python
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
```

Pythonu možeš dati koliko god brojeva želiš za usporedbu i on će ti dati odgovor! Poprilično pametno, zar ne?

- **and** – ako koristiš `and` operator, obje usporedbe moraju biti istinite (True) kako bi cijela naredba bila istinita
- **or** – ako koristiš `or` operator, samo jedna usporedba mora biti True kako bit cijela naredba bila True

Je li ti poznat izraz "uspoređivati kruške s jabukama"? Idemo isprobati Pythonov ekvivalent:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> 1 > 'django'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: '>' not supported between instances of 'int' and 'str'
```

Ovdje vidiš da, kao i u izrazu, Python ne može uspoređivati broj (`int`) i string (`str`). Umjesto toga pokazuje **TypeError** i govori nam da ta dva tipa ne mogu biti uspoređena.

## Boolean

Slučajno si upravo naučila o novom tipu objekta u Pythonu. Zove se **Boolean**.

Postoje samo dva Boolean objekta:

- True
- False

Ali kako bi Python to razumio, uvijek to moraš pisati kao 'True' (prvo slovo veliko, ostala mala). **true, TRUE, and tRUE neće raditi – samo je True ispravno.** (Naravno, isto se odnosi i na 'False'.)

Booleani također mogu biti varijable! Vidi ovo:

{% filename %}command-line{% endfilename %}

```python
>>> a = True
>>> a
True
```

To također možeš napraviti ovako:

{% filename %}command-line{% endfilename %}

```python
>>> a = 2 > 5
>>> a
False
```

Vježbaj i zabavi se s Booleanima tako da pokušaš izvesti iduće naredbe:

- `True and True`
- `False and True`
- `True or 1 == 1`
- `1 != 2`

Čestitamo! Booleani su jedna od najkul značajki programiranja, a ti si upravo naučila kako ih koristiti!

# Spremi ga!

> Za čitatelje kod kuće: ovaj je dio pokriven u [Python Basics: Saving files and "If" statement](https://www.youtube.com/watch?v=dOAg6QVAxyk) videu.

Do sada smo sav svoj Python kod pisali u prevoditelj, što nas ograničava na unošenje jedne po jedne linije koda. Normal programs are saved in files and executed by our programming language **interpreter** or **compiler**. So far we've been running our programs one line at a time in the Python **interpreter**. We're going to need more than one line of code for the next few tasks, so we'll quickly need to:

- Izađi iz Pythonovog prevoditelja
- Otvori naš izbor uređivača koda
- Spremi neki kod u novu Python datoteku
- Pokreni ga!

Da izađeš iz prevoditelja koji smo koristili, jednostavno upiši `exit()` funkciju

{% filename %}command-line{% endfilename %}

```python
>>> exit()
$
```

To će te vratiti u naredbeni redak.

Earlier, we picked out a code editor from the [code editor](../code_editor/README.md) section. We'll need to open the editor now and write some code into a new file:

{% filename %}editor{% endfilename %}

```python
print('Hello, Django girls!')
```

Obviously, you're a pretty seasoned Python developer now, so feel free to write some code that you've learned today.

Now we need to save the file and give it a descriptive name. Let's call the file **python_intro.py** and save it to your desktop. We can name the file anything we want, but the important part here is to make sure the file ends in **.py**. The **.py** extension tells our operating system that this is a **Python executable file** and Python can run it.

> **Note** You should notice one of the coolest thing about code editors: colors! In the Python console, everything was the same color; now you should see that the `print` function is a different color from the string. This is called "syntax highlighting", and it's a really useful feature when coding. The color of things will give you hints, such as unclosed strings or a typo in a keyword name (like the `def` in a function, which we'll see below). This is one of the reasons we use a code editor. :)

With the file saved, it's time to run it! Using the skills you've learned in the command line section, use the terminal to **change directories** to the desktop.

<!--sec data-title="Change directory: OS X" data-id="python_OSX"
data-collapse=true ces-->

Na Macu, naredba će izgledati ovako nekako:

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Linux" data-id="python_linux"
data-collapse=true ces-->

Na Linuxu, bit će ovako (riječ "Desktop" može biti prevedena na tvoj lokalni jezik):

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Command Prompt" data-id="python_windows" data-collapse=true ces-->

U Windowsovoj konzoli (Command Prompt, cmd), bit će ovako:

{% filename %}command-line{% endfilename %}

    > cd %HomePath%\Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Powershell" data-id="python_windowsPSH" data-collapse=true ces-->

A u Windowsovom Powershellu izgledat će ovako:

{% filename %}command-line{% endfilename %}

    > cd $Home\Desktop
    

<!--endsec-->

Ako zapneš, samo pitaj za pomoć.

Sada iskoristi Python za pokretanje koda u datoteci:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hello, Django girls!
    

Napomena: na Windowsima 'python3' nije prepoznato kao naredba. Umjesto toga, iskoristi 'python' za pokretanje datoteke:

{% filename %}command-line{% endfilename %}

```python
> python python_intro.py
```

Uredu! Upravo si pokrenula svoj prvi Python program koji je spremljen u datoteku. Osjećaš li se super?

Sada možeš krenuti dalje na osnovni alat u programiranju:

## If … elif … else

Lots of things in code should be executed only when given conditions are met. That's why Python has something called **if statements**.

Zamijeni kod u svojoj **python_intro.py** datoteci ovime:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
```

Da ovo spremimo i pokrenemo, vidjeli bismo ovakvu grešku:

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

### Što ako uvjet nije istinit?

In previous examples, code was executed only when the conditions were True. But Python also has `elif` and `else` statements:

{% filename %}python_intro.py{% endfilename %}

```python
if 5 > 2:
    print('5 is indeed greater than 2')
else:
    print('5 is not greater than 2')
```

Kada se to pokrene, ispisat će:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    5 is indeed greater than 2
    

Da je 2 broj veći od 5, onda bi se izvela druga naredba. Idemo vidjeti kako `elif` radi:

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

i pokrenut:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hey Sonja!
    

Vidiš što se dogodilo? `elif` ti dopušta dodavanje dodatnih uvjeta koji se izvedu ako prethodni ne prođu.

Možeš dodati koliko god `elif` izraza želiš poslije početnog `if` izraza. Na primjer:

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

    $ python3 python_intro.py
    Perfect, I can hear all the details
    

## Komentari

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

### Sažetak

In the last few exercises you learned about:

- **comparing things** – in Python you can compare things by using `>`, `>=`, `==`, `<=`, `<` and the `and`, `or` operators
- **Boolean** – a type of object that can only have one of two values: `True` or `False`
- **Saving files** – storing code in files so you can execute larger programs.
- **if … elif … else** – statements that allow you to execute code only when certain conditions are met.
- **comments** - lines that Python won't run which let you document your code

Time for the last part of this chapter!

## Tvoje vlastite funkcije!

> For readers at home: this part is covered in the [Python Basics: Functions](https://www.youtube.com/watch?v=5owr-6suOl0) video.

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

- If you get a `NameError`, that probably means you typed something wrong, so you should check that you used the same name when creating the function with `def hi():` and when calling it with `hi()`.
- If you get an `IndentationError`, check that both of the `print` lines have the same whitespace at the start of a line: python wants all the code inside the function to be neatly aligned.
- If there's no output at all, check that the last `hi()` *isn't* indented - if it is, that line will become part of the function too, and it will never get run.

Let's build our first function with parameters. We will use the previous example – a function that says 'hi' to the person running it – with a name:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
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

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Sonja!
    

Now, what do you think will happen if you write another name in there? (Not Ola or Sonja.) Give it a try and see if you're right. It should print out this:

{% filename %}command-line{% endfilename %}

    Hi anonymous!
    

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

## Petlje

> For readers at home: this part is covered in the [Python Basics: For Loop](https://www.youtube.com/watch?v=aEA6Rc86HF0) video.

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
for name in girls:
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
for i in range(1, 6):
    print(i)
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

## Sažetak

That's it. **You totally rock!** This was a tricky chapter, so you should feel proud of yourself. We're definitely proud of you for making it this far!

For official and full python tutorial visit https://docs.python.org/3/tutorial/. This will give you a more thorough and complete study of the language. Cheers :)

You might want to briefly do something else – stretch, walk around for a bit, rest your eyes – before going on to the next chapter. :)

![Cupcake](images/cupcake.png)