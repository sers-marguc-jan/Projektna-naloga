# Specifikacija spletne aplikacije: Preverjanje zasedenosti

**Skupina / člani:** Jan Marguč, Jaka Kresnik, Žiga Salaj, Aleks Ristovski 
**Verzija:** 1.0
**Status:** Osnutek

## 1. Opis problema

Ljudje pogosto obiščejo trgovine, frizerske salone, restavracije in druge objekte, ne da bi vedeli, kako zasedeni so. Zaradi tega lahko naletijo na gnečo in dolge čakalne dobe.

Spletna aplikacija bo omogočala preverjanje trenutne in predvidene zasedenosti objektov. Podatke bo pridobivala iz poročil obiskovalcev in, kjer bo mogoče, prostovoljno posredovanih lokacijskih podatkov. Cilj je zmanjšati čakanje in uporabnikom omogočiti boljše načrtovanje obiskov.

## 2. Ciljna skupina

- Kupci in obiskovalci
- Stranke frizerskih salonov
- Obiskovalci restavracij in kavarn
- Lastniki in upravljavci objektov

## 3. Funkcionalne zahteve

| ID | Funkcionalnost | Prioriteta |
|---|---|---|
| F01 | Prikaz seznama objektov | Obvezno |
| F02 | Registracija, prijava in odjava | Obvezno |
| F03 | Iskanje objektov po imenu in kategoriji | Obvezno |
| F04 | Prikaz ocenjene zasedenosti | Obvezno |
| F05 | Oddajanje poročil o zasedenosti | Obvezno |
| F06 | Prostovoljna uporaba lokacije | Obvezno |
| F07 | Prikaz časa zadnje posodobitve | Obvezno |
| F08 | Administracija objektov in poročil | Obvezno |
| F09 | Prikaz običajne zasedenosti po urah | Dodatno |
| F10 | Napoved zasedenosti v prihodnjih urah | Dodatno |

Zasedenost bo prikazana kot majhna, srednja ali velika gneča.

## 4. Uporabniške vloge

- **Obiskovalec:** pregleduje objekte in zasedenost.
- **Registrirani uporabnik:** oddaja poročila o zasedenosti.
- **Lastnik objekta:** ureja podatke svojega objekta, če bo ta funkcija izvedena.
- **Administrator:** upravlja objekte in poročila.

## 5. Podatki

Predvidene tabele podatkovne baze:

- `uporabniki`: ID, ime, e-pošta, zgoščeno geslo, vloga.
- `objekti`: ID, naziv, kategorija, naslov, lokacija, opis.
- `porocila`: ID, uporabnik, objekt, stopnja zasedenosti, komentar, čas.
- `priljubljeni_objekti`: ID, uporabnik, objekt.

En uporabnik lahko odda več poročil, vsak objekt pa ima lahko več poročil različnih uporabnikov.

Lokacija se bo uporabljala samo z dovoljenjem uporabnika.

## 6. Uporabniški scenariji

### S01: Preverjanje zasedenosti

1. Uporabnik odpre aplikacijo.
2. Poišče objekt po imenu ali kategoriji.
3. Izbere objekt.
4. Sistem prikaže ocenjeno zasedenost in čas zadnje posodobitve.

**Rezultat:** Uporabnik lahko izbere primernejši čas obiska.

### S02: Oddaja poročila

1. Prijavljeni uporabnik odpre izbrani objekt.
2. Izbere stopnjo gneče.
3. Po želji doda komentar.
4. Odda poročilo.
5. Sistem shrani podatke in posodobi oceno.

### S03: Uporaba lokacije

1. Uporabnik dovoli uporabo lokacije.
2. Sistem poišče bližnje objekte.
3. Prikaže razpoložljive podatke o njihovi zasedenosti.

Če uporabnik lokacije ne dovoli, lahko objekte še vedno išče ročno.

## 7. Obseg projekta

### 7.1 MVP

- Prikaz in iskanje objektov
- Registracija, prijava in odjava
- Prikaz ocenjene zasedenosti
- Oddajanje poročil
- Prikaz časa zadnje posodobitve
- Osnovna administracija
- Povezava s podatkovno bazo
- Preverjanje vnosov in pravic
- Prilagodljiv uporabniški vmesnik

### 7.2 Dodatne funkcionalnosti

- Napoved zasedenosti
- Grafi zasedenosti
- Zemljevid objektov
- Priljubljeni objekti
- Obvestila o manjši zasedenosti

### 7.3 Izven obsega

- Samostojna mobilna aplikacija
- Napredno umetnointeligenčno napovedovanje
- Sledenje posameznim osebam

## Dodatek A: Tehnične zahteve

Uporabili bomo HTML5, CSS3, JavaScript, PHP in MySQL/MariaDB.

Gesla bodo varno zgoščena, vnosi preverjeni, dostop pa omejen glede na uporabniško vlogo. Za delo s podatkovno bazo bomo uporabili pripravljene poizvedbe PDO. Aplikacija bo objavljena prek HTTPS.

## Dodatek B: Potrditev

- Profesor A – programiranje in podatkovna baza: __________________
- Profesor B – dizajn in uporabniška izkušnja: __________________
- Datum potrditve: __________________
