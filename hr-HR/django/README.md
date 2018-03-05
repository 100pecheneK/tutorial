# Što je Django?

Django (*Džan-go*) je web aplikacija koja je besplatna i otvorenog je koda. Web framework je skup komponenti koje ti pomažu razvijati web stranice brže i lakše.

Kada stvaraš web stranicu, uvijek ćeš trebati slične komponente: autentikacija korisnika (prijava, odjava), način upravljanja svoje stranice, formulari, uploadanje datoteka itd.

Srećom, davno su drugi ljudi primjetili da se većina web programera susreće sa sličnim problemima kad stvaraju novu stranicu, pa su se udružili i stvorili razne frameworke (tipa Django) koji ti daju gotove komponente na korištenje.

Frameworksi postoje da bi te spasili od potrebe izmišljanja "tople vode" i da ti smanje potrebu pisanja previše koda kada radiš novu stranicu.

## Zašto ti treba framework?

Za razumijevanje za što zapravo služi Django, moramo pobliže pogledati poslužitelje. Prva stvar koju poslužitelji trebaju znati je da ti želiš da ti oni posluže web stranicu.

Zamisli npr. poštanski sandučić (port) kojeg nadzireš za nadolazeća pisma (zahtjeve). To radi web poslužitelj. Web poslužitelj pročita pismo i pošalje odgovor sa web stranicom. Ali, ako želiš poslati nešto, moraš imati sadržaj. Upravo je Django tu da ti pomogne stvoriti sadržaj.

## Što se događa kad netko zatraži web stranicu s tvog poslužitelja?

Čim zahtjev dođe na web poslužitelj, zahtjev se prosljeđuje Djangu koji zatim pokušava odgonetnuti što je zapravo zatraženo. Ono najprije uzme stranicu web adrese i pokuša odgonetnuti što treba učiniti. Taj dio radi Djangov **urlresolver** (imaj na umu da se adresa web stranice naziva još i URL - Uniform Resource Locator - stoga *urlresolver* razrješava url stranice). Nije baš najpametniji - ima listu obrazaca s kojom uspoređuje adrese. Django provjerava obrasce od vrha prema dnu i ako nešto odgovara, tad Django proslijedi zahtjev pridruženoj funkciji (koja se naziva *view* - *pogled*).

Zamisli poštara sa pismom. On hoda niz ulicu i uspoređuje svaki kućni broj sa brojem na pismu. Ako su isti, ostavi tamo pismo. Upravo na ovaj način radi urlresolver!

U *view* funkciji događaju se sve zanimljive stvari: možemo potražiti neke informacije u bazi podataka. Možda je korisnik zatražio da mu promijenimo podatke? Poput pisma u kojem piše:"Molim promjeniti opis mog posla.". *View* će provjeriti je li ti dozvoljena ta radnja, zatim će za tebe promjeniti opis posla i vratiti poruku:"Gotovo!". Tada *view* stvara odgovor i Django ga potom šalje korisnikovom web pregledniku.

Of course, the description above is a little bit simplified, but you don't need to know all the technical things yet. Having a general idea is enough.

So instead of diving too much into details, we will simply start creating something with Django and we will learn all the important parts along the way!