# Ülesanne
Inimkond on äsja avastanud tähevärava, mille abil on võimalik saata inimesi teistele planeetidele. Mis peaks olema suurhetk inimkonna ajaloos muutub aga kiiresti tragöödiaks, kuna galaktikat avastades leitakse, et teiste planeetide asunike ning inimeste vaated ei lähe kokku selles osas, kes peaks seda galaktikat valitsema. POTUS pani kõik oma lootused eliitrühmale nimega SG-1: parimatest parimad ning inimkonna parim relv teel galaktika valitsemise poole. SG-1 esimesed missioonid olid paljulubavad, kuid see kõik muutus, kui tulerahvas ründas. Nad püüdsid SG-1 kinni ning hukkasid nad armutult. Tähevärava Keskuse juht kindral Hammond Texasest ei julge teadet POTUS-e lemmikrühma ebaõnnestumisest avalikustada. See aga tähendab, et kindal Hammond Texasest peab jätkama galaktika koloniseerimist samas tempos kui varemgi, kuid enam ei ole tal SG-1 ning alles on jäänud vaid tuhandeid kõrgelt treenitud õhuväe sõdureid. Selleks palub ta sinu abi.

Statistikud on suutnud uute planeetide avastamist, nende koloniseerimist ning koloniseerimisest saadavat kasu kirjeldada väga lihtsa mudeli abil ning kindral kinnitab sulle, et see mudel on veatu.

## Mudel
* Planeeti kirjeldab 3 parameetrit
  * Koloniseerimiseks kuluv päevade arv **N**
  * Ühe koloniseerimispäeva jooksul kuluvate ressursside arv **R**
  * Ressursside arv, mida planeet peale koloniseerimist tootma hakkab **T**
* Planeedi avastamiseks (avastamise käigus saab teada kõik parameetrid) kulub **M** ressurssi.
* Praegu on Tähevärava Keskusel **C** ressurssi.
* Tähevärava Keskusel on **A** tiimi ning tiimid saavad iga päev teha ühte järgnevatest tegevustest:
  * Avastada uus planeet (kulutades selleks **M** ressurssi).
  * Veeta üks päev mingit planeeti koloniseerides (kulutades selleks **R** ressurssi, kus **R** sõltub planeedist).
* Kui planeet on koloniseeritud peavad seal kasumi saamiseks töötama tsiviilelanikud, kuid ressurssides on nende väärtus 0, ehk iga päev peale planeedi koloniseerimist saab sealt **T** ressurssi *niisama*.
* Planeetide parameetrid on üksteisest sõltumatud ning alluvad normaaljaotustele.
* Normaalaaljaotuste parameetrid ei ole teada, kuid neid saab hinnata järjest rohkem planeete avastades.

## Aruanne POTUS-ele
Tähevärava Keskusel on praegu **B** ressurssi.  
POTUS-ele tuleb teha aruanne Tähevärava Keskuse tegemiste kohta **D** päeva pärast.  
Sinu ülesandeks on selleks ajaks omada võimalikult palju ressursse.
