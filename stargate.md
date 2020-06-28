# Ülesanne
Inimkond on äsja avastanud tähevärava, mille abil on võimalik saata inimesi teistele planeetidele. Mis peaks olema suurhetk inimkonna ajaloos muutub aga kiiresti tragöödiaks, kuna galaktikat avastades leitakse, et teiste planeetide asunike ning inimeste vaated ei lähe kokku selles osas, kes peaks seda galaktikat valitsema. POTUS pani kõik oma lootused eliitrühmale nimega SG-1: parimatest parimad ning inimkonna ainuke relv teel galaktika valitsemise poole. SG-1 esimesed missioonid olid paljulubavad, kuid see kõik muutus, kui tulerahvas ründas. SG-1 püüti kinni ning hukati armutult. Tähevärava Keskuse juht Hammond Texasest ei julge teadet POTUS-e lemmikrühma ebaõnnestumisest avalikustada. See aga tähendab, et Hammond Texasest peab jätkama galaktika koloniseerimist samas tempos kui varemgi. Enam ei saa ta aga kasutada SG-1'te ning alles on jäänud vaid tuhandeid kõrgelt treenitud õhuväe sõdureid. Nende efektiivseks kasutamiseks palub ta sinu abi.

## Aruanne POTUS-ele
Tähevärava Keskusel on praegu **C** ressurssi.  
POTUS-e praegune rahastus annab Tähevärava keskusele juurde **D** ressurssi päevas.  
POTUS-ele tuleb teha aruanne Tähevärava Keskuse tegemiste kohta **B** päeva pärast.  
Sinu ülesandeks on selleks ajaks omada võimalikult suurt ressursitootlikkust koloniseeritud planeetidel.

## Mudel

Statistikud on suutnud uute planeetide avastamist, nende koloniseerimist ning koloniseerimisest saadavat kasu kirjeldada väga lihtsa mudeli abil ning kindral kinnitab sulle, et see mudel on veatu.

* Planeedi avastamiseks (avastamise käigus saab teada kõik parameetrid) kulub **M** ressurssi.
* Planeeti kirjeldab 3 parameetrit:
  * Koloniseerimiseks kuluv päevade arv **N**
  * Ühe koloniseerimispäeva jooksul kuluvate ressursside arv **R**
  * Ressursside arv, mida planeet peale koloniseerimist tootma hakkab **T**
* Planeetide parameetrid on üksteisest sõltumatud ning alluvad binoomjaotustele.
* Binoomjaotuste parameetrid ei ole teada, kuid neid saab hinnata järjest rohkem planeete avastades.  
* Tähevärava Keskusel on **A** tiimi ning tiimid saavad iga päev teha ühte järgnevatest tegevustest:
  * Avastada uus planeet.
  * Veeta üks päev mingit planeeti koloniseerides.
* Kui planeedi koloniseerimisega on tegeletud **N** päeva, siis saavad seal kasumi saamiseks töötama hakata tsiviilelanikud - planeet hakkab igapäevaselt tootma **T** ressurssi.

## Sisendandmete vahemikud
Sisendandmed saab programm kohe teada  
**A:** 5 - 15 ; tiimide arv  
**B:** 1000 - 2000 ; päevade arv  
**C:** 5000 - 15000 ; algne ressursside arv  
**D:** 500 - 1000 ; algne rahastus (ressursitootlikkus)  
**M:** 100 - 1000  ; planeedi avastamiseks kuluv ressursside arv  

N, R ja T binoomjaotuste parameetrid on "mõistliku" suurusega arvestades A, B, C, D ja M vahemikke.

## Mall

```
Class Strategy:

  def __init__(self, teams, days, initial_resources, initial_production, exploration_cost):
    """The initial parameters are given at the start."""

  def get_actions():
    """
    Called at the beginning of each day.

    Return a list of actions describing what your teams will do.
    (you may return less actions than you have teams, but not more)

    If you wish to explore with a team,
    then the corresponding list element
    should be the string "explore".

    If you wish to work towards colonizing a planet,
    then the corresponding list element
    should be an integer with the planet's ID.
    """
    return []

  def give_results(results):
    """
    Called at the end of each day.

    'results' will be a list, describing what each of your teams did.

    If the corresponding team was sent out to explore,
    then the element will be a list of 4 int's describing the planet that they found. [ID, N, R, T]

    If the corresponding team was sent out to colonize a planet,
    then the element will simply be none.
    """

  def sync(days_past, days_left, resources, production, planets):
    """
    Called each day after 'give_results'.

    It is completely possible to keep your data
    about the galaxy and humanity's resources in sync with reality
    using only the 'init', 'get_actions' and 'give_results' functions,
    but if you for some reason don't want to do that,
    then this function should give you all of the information
    about the current state of the galaxy.

    If you keep track of it yourself,
    feel free to ignore this function,
    it is only meant to simplify things for those,
    who are unsure of their ability to track said information correctly.

    days_past will be an int that describes how many days have passed.
    days_left will be an int that describes how many days are left until POTUS'es report.
    resources will be an int describing how many resources humanity has at their disposal currently
    production will be an int describing how many resources humanity gets each day
    (production for the day that just passed has already been added to resources)
    planets will be a list of all the planets,
    that humanity has discovered,
    where the index, is the same as the ID
    and each element will be a list [N_l, R, T],
    where N_l, is the amount of days left,
    for the planet to be colonized.
    If N_l is 0, then the planet is colonized and is producing resources.
    """

```
