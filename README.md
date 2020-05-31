# Ülesanne
Tegemist on OOP ülesandega, kus 70% punktidest tuleb automaattestidest ning 30% tuleb kaitsmisel õppejõu poolt.
Oled sõpradega viimastel aastatel mänginud palju lauamänge ning üks neist tuleb sinu juurde, kuna ta on kogu selle aja jooksul peale igat mängu tulemuse kirja pannud ning tahab, et sina koostaksid Pythoni programmi, mis neid andmeid analüüsib ning parima mängija välja selgitab.

## Tulemuste formaat
Tulemused on tekstifailis, kus iga rida tähistab ühte mängu ning on kujul:\
**mängu nimi**;**mängijate nimed**;**tulemuse tüüp**;**tulemused**

Mängijad võib mängul olla ükskõik kui palju ning **mängijate nimed** on kujul:\
**mängija1**,**mängija2**,**mängija3** jne

**tulemuse tüübi** jaoks on 3 võimalikku valikut ning see sõltub sellest, millise lauamänguga oli tegemist:\
**points** - tähendab, et mängu lõppedes saab iga mängija mingi arvu punkte, mille põhjal saab vajaduse korral leida paremusjärjestuse või võitja\
**places** - tähendab, et mängu lõppedes saab teada mängijate paremusjärjestuse, mille põhjal saab vajaduse korral leida võitja\
**winner** - tähendab, et mängu lõppedes saab teada vaid mängu võitja

**tulemuste** kuju sõltub tulemuse tüübist\
**points** korral on see kujul **a**, **b**, **c**, kus a, b ja c on vastavalt **mängija**, **mängija2** ja **mängija3** punktid\
**places** korral on see kujul **mängija2**, **mängija3**, **mängija1**, kus mängijate nimed on paremuse järjekorras (esimene on võitja, ning viimasena on viimasel kohal olnud mängija)\
**winner** korral on see kujul **mängija2**, kus on kirjas vaid võitja nimi

## Klass: Statistics
**Statistics** on peaming klass, mis haldab kogu tegevust.\
*Konstruktor*: \__init__(self, **filename**), kus **filename** on fail, kust tuleb lugeda tulemusi.
### Nõutud funktsionaalsus
#### Kokkuvõtvad andmed (4.5p)
* **get_player_names()** - tagastab listi mängijate nimedest (nimede järjekord pole oluline)
* **get_game_names()** - tagastab listi mängude nimedest (nimede järjekord pole oluline)
* **get_games_played_amount()** - tagastab *int*-i, mis kirjeldab, mitu mängu on mängitud
* **get_games_played_of_type(result_type)** - kus **result_type** on string võimalike väärtustega **points**, **places** või **winner**, funktsioon peab tagastama, mitu seda tüüpi mängu on mängitud
* **get_games_played_of_name(name)** - tagastab *int*-i, mis kirjeldab, mitu mängu nimega **name** on mängitud

#### Andmed mängija kohta (3p)
Selle osa jaoks oleks ilmselt mõistlik luua Player klass.
* **get_games_amount_played_by(player_name)** - tagastab *int*-i, mis kirjeldab, mitu mängu on mängija nimega **player_name** mänginud
* **get_favourite_game(player_name)** - tagastab mängu (*string*), mida mängija nimega **player_name** on enim mänginud, viigi korral tagastada neist suvaline
* **get_amount_of_games_won(player_name)** - tagastab *int*-i, mis kirjeldab, mitu mängu mängija nimega **player_name** on võitnud

#### Andmed mängu kohta (3p)
Selle osa jaoks oleks ilmselt mõistlik luua Game klass.
* **get_amount_of_players_most_often_played_with(game_name)** - tagastab *int*-i, mis kirjeldab, mitme mängijaga mängu nimega **game_name** enim mängitud on, viigi korral tagastada neist suvaline
* **get_most_frequent_winner(game_name)** - tagastab mängija (*string*), kelle võiduprotsent mängus nimega **game_name** on suurim, viigi korral tagastada neist suvaline (seda funktsiooni võidakse kutsuda ükskõik, mis tüüpi mängu korral)
* **get_player_with_most_amount_of_wins(game_name)** - tagastab mängija (*string*), kellel on mängus nimega **game_name** enim võite, viigi korral tagastada neist suvaline (seda funktsiooni võidakse kutsuda ükskõik, mis tüüpi mängu korral)
* **get_most_frequent_loser(game_name)** - tagastab mängija (*string*), kelle kaotuse protsent (protsent kordadest, kui mängija jäi viimasele kohale) mängus nimega **game_name** on suurim, viigi korral tagastada neist suvaline (seda funktsiooni kutsutakse vaid **points** või **places** mängu korral)
* **get_player_with_most_amount_of_losses(game_name)** - tagastab mängija (*string*), kellel on mängus nimega **game_name** enim kaotusi (viimasele kohale jäämisi), viigi korral tagastada neist suvaline (seda funktsiooni kutsutakse vaid **points** või **places** mängu korral)
* **get_record_holder(game_name)** - tagastab mängija (*string*), kes on mängus nimega **game_name** saanud enim punkte (ühe mängu jooksul), viigi korral tagastada see, kes selle tulemuse esimesena saavutas (seda funktsiooni kutsutakse vaid **points** mängu korral)

#### Parima mängija leidmine (4.5p)
Selle osa kohta automaattestid puuduvad, punktid määrab kaitsmisel õppejõud
* **get_best_player()** - tagastab parima mängija (*string*). See kuidas määratakse parim mängija on suuresti tudengi enda otsustada, kuid kindlasti tuleb arvesse võtta tulemusi igat tüüpi mängudest
* **get_best_player_of(game_name)** - tagastab mängu **game_name** parima mängija. Jällegi, kuidas täpselt otsustatakse, kuidas määrata parim mängija on tudengi otsustada, kuid mõned piirangud sellel siiski on.
 * Sõltuvalt mängu tüübist, peab süsteem parima mängija leidmiseks olema erinev
 * Iga mängu tüübi kohta parimat mängijat leidev loogika peab kasutama kõiki andmeid, mida antud mängu tüüp pakub (ehk **points** mängu puhul tuleb arvestada punkte / punktivahesid ning ei tohi lihtsalt punkte taandada paremusjärjestuseks ning **places** mängu puhul peab parema koha saanud mängijat paremini kohtlema (mitte ainult eristama võitjat ja kaotajat))
 * Süsteem peab olema huvitav / mitte-triviaalne, allpool on iga mängutüübi kohta toodud parima mängija leidmise süsteemi näited, mis ei anna maksimumpunkte, maksimumpunktide jaoks peab süsteem olema antud näidetega võrreldes kompleksem
 * **winner** - parim mängija on enim võite saanud mängija
 * **places** - iga koht annab n - x punkti, kus n on mängijate arv, ning x on koht, ning võitja on enim punkte saanud mängija
 * **points** - punktid liidetakse kokku ning enim punkte saanud mängija võidab
 * Iga kirjeldatud süsteemi kohta saab teha ka analoogse, kuid 'protsentuaalse' süsteemi, kus tulemus on jagatud läbi sellega, mitu korda antud mängija mängis, lahendused, mis selle lisaga piirduvad ei anna samuti maksimumpunkte
