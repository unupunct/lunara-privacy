---
title: Politica de confidentialitate
---

# Politica de confidențialitate — Lunara

**Ultima actualizare:** 14 august 2026
**Versiune aplicație:** 1.0.0

Lunara este o aplicație de monitorizare a ciclului menstrual care funcționează
**complet pe telefonul tău**.

> **Nu avem un server. Nu avem conturi. Nu deținem datele tale.**
>
> Nu îți putem vedea ciclul, notițele sau simptomele — nu pentru că promitem că
> nu ne uităm, ci pentru că datele nu ajung niciodată la noi. Nu există nimic de
> cerut, de piratat sau de citat în instanță.

> Lunara oferă informații de wellness. **Nu** este un dispozitiv medical, nu pune
> diagnostice și nu este o metodă contraceptivă.

---

## Ce s-a schimbat

O versiune anterioară a acestui document, nepublicată, descria un server de
sincronizare. **Acel server nu mai există și nu a fost niciodată folosit de o
versiune publicată a aplicației.** Aplicația se distribuie ca un singur fișier
APK, fără niciun serviciu în spate.

Menționăm asta pentru că e mai bine să citești aici ce s-a schimbat decât să te
întrebi de ce documentul arată altfel.

## 1. Ce date colectăm

**Niciunele.**

Aplicația nu are cont, nu cere email, nu cere parolă și nu trimite date către noi
sau către altcineva. Nu există analytics, nu există trackere, nu există SDK-uri
de publicitate, nu există raportare de erori.

Ce introduci tu se scrie într-o bază de date SQLite aflată în spațiul privat al
aplicației, pe telefonul tău:

| Categorie | Câmpuri |
|---|---|
| Profil | nume afișat (opțional), durata medie a ciclului și a menstruației |
| Ciclu | datele de început ale menstruațiilor |
| Check-in zilnic | flux, dispoziție, energie, libido, ore de somn, simptome, notițe |
| Partener | cheia de împerechere și preferințele tale de partajare |

**Nu accesăm:** contacte, locație, identificatori de publicitate, alte aplicații,
istoricul de navigare, microfonul.

**Camera** este folosită într-un singur loc: citirea codului QR de împerechere.
Nu se salvează și nu se transmite nicio imagine.

## 2. Împerecherea cu partenerul

Împerecherea se face cu trei coduri, pe care le trimiteți **voi**, prin aplicația
de mesagerie pe care o folosiți deja — WhatsApp, Signal, SMS — sau prin codul QR,
dacă sunteți în aceeași cameră.

1. Un telefon face un cod și îl trimite.
2. Celălalt răspunde cu un cod care spune cine este.
3. Primul telefon confirmă explicit. **Nimic nu se sincronizează până la această
   confirmare.**

Al doilea și al treilea cod sunt criptate cu cheia din primul, deci cineva care a
văzut codul într-un grup nu poate falsifica un răspuns și, mai important, nu poate
falsifica o confirmare.

Codurile nu trec pe la noi. Nu există niciun server implicat: sunt text, iar
canalul îl alegi tu.

**Limita, spusă direct:** oricine primește primul cod poate cere împerecherea.
Codul de verificare din șase caractere arată că ambele telefoane au aceeași cheie
— **nu** că nimeni altcineva nu o are. Trimite-l unei singure persoane. De aceea
există pasul de confirmare.

## 3. Sincronizarea

Cele două telefoane se sincronizează **direct între ele, doar când sunt pe același
Wi-Fi**. Datele trec de la un telefon la celălalt, criptate, fără să atingă
vreun server — nu există unul.

Când sunteți în locuri diferite, nu se sincronizează nimic automat. Nu este o
limitare pe care am ales-o din lene: două telefoane aflate în rețele diferite nu
se pot găsi unul pe altul, iar un telefon adormit nu poate primi nimic. Singura
soluție ar fi un intermediar care păstrează mesajul, adică exact serverul pe care
am decis să nu îl avem.

**Tu decizi ce se trimite**, separat pentru fiecare partener:

- **faza ciclului** — implicit activ
- **dispoziție și energie** — implicit **dezactivat**
- **simptome** — implicit **dezactivat**

Din 14 august 2026, dispoziția și energia sunt oprite implicit. Aplicația
partenerului arată faza și un sfat pe zi; dispoziția și energia nu apar acolo, iar
un lucru care nu se afișează nu are de ce să fie trimis.

**Notițele tale zilnice nu părăsesc telefonul**, indiferent de setări. Jurnalul
din „Notează" nu este inclus în ce se sincronizează. Libidoul nu se trimite
niciodată — nu există nicio setare care să îl activeze.

### Mesajele pentru partener

Există un singur text care ajunge pe celălalt telefon: cel scris anume în câmpul
**„Mesaj pentru partener"**. Funcționează în ambele direcții — și el îți poate
scrie.

Nu are un comutator, pentru că nu are nevoie de unul: singurul mod în care un
mesaj există este că l-ai scris în câmpul care spune că se trimite. Asta a fost o
decizie deliberată. Varianta evidentă — un comutator „trimite și nota asta" pe
jurnalul zilnic — ar fi transformat promisiunea de mai sus în „notițele nu pleacă,
*cu excepția* cazului în care un comutator este activ", iar o apăsare greșită ar
fi trimis o pagină de jurnal privat pe telefonul altcuiva, fără cale de retragere.

Un mesaj se poate retrage: golește câmpul și salvează. Retragerea călătorește ca
orice altă modificare, deci mesajul dispare și de la el la următoarea
sincronizare. Câte unul pe zi de fiecare parte, deci nu se strânge un istoric de
conversație pe niciun telefon.

Anularea împerecherii șterge cheia și, din 14 august 2026, **șterge și mesajele de
pe telefonul care anulează** — în ambele sensuri: și ce ai scris tu, și ce ai
primit. Conversația a existat pentru împerecherea aceea; când ea se termină, se
termină și conversația.

Pe celălalt telefon, copia lui rămâne până când anulează și el. Nu există server,
deci nu avem cum să ștergem ceva de pe un telefon care nu este al tău — la fel ca
orice mesaj trimis vreodată, prin orice aplicație.

## 4. Securitate

- Datele stau în spațiul privat al aplicației, protejat de sistemul de operare și
  de criptarea telefonului.
- **Blocare opțională a aplicației** cu amprentă, față sau codul telefonului.
- **Capturile de ecran și previzualizarea din comutatorul de aplicații sunt
  blocate**, ca datele să nu apară acolo unde altcineva se poate uita.
- **Copierea de rezervă în cloud este dezactivată** (`allowBackup=false`), deci
  datele nu ajung în Google Drive.
- Ce se transmite între telefoane este criptat cu NaCl secretbox
  (XSalsa20-Poly1305), cu o cheie care există doar pe cele două telefoane.
- Notificările sunt programate local și au text intenționat vag, pentru că apar
  pe ecranul blocat.

## 5. Drepturile tale (GDPR)

Pentru că nu deținem date despre tine, nu avem ce să-ți dăm, să corectăm sau să
ștergem — dar controlul îl ai complet, din aplicație:

- **Acces și portabilitate:** *Setări → Salvează pe telefon* creează un fișier
  JSON cu tot ce există pe telefon, iar *Importă dintr-un export* îl aduce înapoi.
- **Ștergere:** *Setări → Șterge toate datele* elimină definitiv totul.
  Dezinstalarea aplicației are același efect.
- **Rectificare:** poți edita orice, oricând.
- **Retragerea consimțământului:** oprește partajarea sau anulează împerecherea.

**Nu există copie de rezervă.** Dacă îți pierzi telefonul sau ștergi aplicația,
datele dispar. Acesta este prețul faptului că nimeni altcineva nu le are.
Exportă din când în când dacă vrei să le păstrezi.

## 6. Copii

Lunara nu este destinată persoanelor sub 16 ani.

## 7. Modificări

Dacă modificăm această politică, actualizăm data de la început și scriem explicit,
la începutul documentului, ce s-a schimbat în privința datelor care pleacă de pe
telefon.

## 8. Contact

**puskas.m@gmail.com**

Ține minte: nu putem accesa datele tale, deci nu te putem ajuta să le recuperezi
și nu îți putem spune ce conțin. Putem răspunde doar la întrebări despre
aplicație.
