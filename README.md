# cor-geavanceerde-klassen-leger-start
## bekijk eerst het filmpje "Geavanceerde klassen : oefening Leger opstart"

[ga naar filmpje in Leho](https://howest.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=803dae2e-9130-4abc-bd82-ab8c00d86f12)

Deze oefening behandelt de leerstof rond geavanceerde klassen, meer bepaald overerving en polymorfisme.

De bedoeling is dat we een leger samenstellen dat bestaat uit generaals, majoors, luitenanten, adjudanten, sergeanten, korporaals en soldaten.

Voor de samenstelling van een leger bestaan strikte regels
* een generaal voert bevel over 3 majoors
* een majoor voert bevel over 5 luitenanten
* een luitenant voert bevel over 3 adjudanten
* een adjudant voert bevel over 3 sergeanten
* een sergeant voert bevel over 4 korporaals
* een korporaal voert bevel over 5 soldaten

Generaals, majoors en luitenanten zijn officieren.  Om die makkelijk te herkennen beschikken die over kentekens (sterren) in het kleur goud.  
Adjudanten en sergeanten zijn onderofficieren.  De kleur van hun sterren is zilver.  
Korporaals en soldaten zijn troepen.  De kleur van hun sterren is brons.  

Generaals hebben 3 sterren.  
Majoors, adjudanten en korporaals hebben 2 sterren.  
Luitenanten, sergeanten en soldaten hebben 1 ster.  

Iedereen - officieren, onderofficieren en troep - zijn militairen.  
Alle generaals, majoors en luitenanten zijn officieren.  
Alle adjudanten en sergeants zijn onderofficieren.  
Alle korporaals en soldaten zijn troepen.  

Het mag dus duidelijk zijn dat de basisklasse "Militair" is.  
De klassen "Officier", "Onderofficier" en "Troep" erven over van "Militair".  
De klassen "Generaal", "Majoor", "Luitenant" erven over van "Officier".  
De klassen "Adjudant" en "Sergeant" erven over van "Onderofficier".  
De klassen "Korporaal" en "Soldaat" erven over van "Troep".  

De basisklasse Militair beschikt over volgende eigenschappen (gewone prop volstaat) : 
* Naam : string
* Gewicht : int
* Kleur : string
* Sterren : int
* AantalRechtstreeksOndergeschikten : int
* RechtstreeksOndergeschikte : List<Militair>

De basisklasse beschikt eveneens over 2 statische velden : 
* volgnummer : int
* Dictionary<string, int> aantalPersoort  (we komen hier in de oplossing uiteraard op terug)

De basisklasse heeft 1 argumentloze contructor.
Deze constructor doet het volgende : 
* het veld volgnummer wordt met 1 verhoogd
* de eigenschap Naam wordt gevuld met het soort van object, gevolgde door het volgnummer.  Als er dus bv een nieuwe korporaal wordt aangemaakt, dan dient de naam van de korporaal te zijn : "Korporaal 1" of "Korporaal 312" of ...
* je kan in de basisklasse te weten komen welk object er wordt aangemaakt met de instructie "this.GetType().Name;".  Stel dat een nieuwe instantie van de klasse Majoor wordt aangemaakt dan zal de constructor van de basisklasse wel degelijk uitgevoerd worden (Majoor erf over van Officier die op zijn beurt overerft van Militair).  Op dat moment zal this.GetType().Name de string "Majoor" opleveren.
* de list RechtstreeksOndergeschikte wordt geinstantieerd.

In de basisklasse wordt eveneens de ToString() methode overschreven : je beelt enkel de naam van de militair af.

De basisklasse heeft ook nog de methode TotaalAantalOndergeschikten die een int retourneert.  
Het is de bedoeling dat deze methode gaat gaan uitrekenen hoeveel ondergeschikten een gegeven militair heeft.    
Een generaal zal uiteraard het grootste aantal ondergeschikten hebben : 3438.  
Een majoor heeft er 1145, een luitenant 228 ... een soldaat 0.  
Uiteraard dienen deze aantal berekend te worden.

Tenslotte - maar hou dit voor het laatste - dien je in de constructor van de basisklasse ook nog een dictionary aan te vullen (aantalPersoort).  
Per soort (generaal, majoor ... soldaat) dien je bij te houden hoeveel er van gemaakt werden.  Zoek eventueel even op op het internet hoe je dit kan oplossen (of wacht op de oplossing van mij).

De klasse Officier erft over van Militair en heeft enkel een argumentloze constructor die de eigenschap Kleur vult met de waarde "Goud".  
De klasse Onderofficier erft over van Militair en heeft enkel een argumentloze constructor die de eigenschap Kleur vult met de waarde "Zilver".  
De klasse Troep erft over van Militair en heeft enkel een argumentloze constructor die de eigenschap Kleur vult met de waarde "Brons".  

De klasse Generaal erft over van Officier en heeft enkel een argumentloze constructor die het volgende doet : 
* eigenschap Sterren instellen op 3
* eigenschap gewicht instellen op 7
* eigenschap AantalRechtstreeksOndergeschikten instellen op 3
* aan de List-eigenschap RechtstreeksOndergeschikte evenveel Majoors toevoegen als de waarde van AantalRechtstreeksOndergeschikten

De klasse Majoor erft over van Officier en heeft enkel een argumentloze constructor die het volgende doet : 
* eigenschap Sterren instellen op 2
* eigenschap gewicht instellen op 6
* eigenschap AantalRechtstreeksOndergeschikten instellen op 5
* aan de List-eigenschap RechtstreeksOndergeschikte evenveel Leutenanten toevoegen als de waarde van AantalRechtstreeksOndergeschikten

De klasse Luitenant erft over van Officier en heeft enkel een argumentloze constructor die het volgende doet : 
* eigenschap Sterren instellen op 1
* eigenschap gewicht instellen op 5
* eigenschap AantalRechtstreeksOndergeschikten instellen op 3
* aan de List-eigenschap RechtstreeksOndergeschikte evenveel Adjudanten toevoegen als de waarde van AantalRechtstreeksOndergeschikten

De klasse Adjudant erft over van Onderofficier en heeft enkel een argumentloze constructor die het volgende doet : 
* eigenschap Sterren instellen op 2
* eigenschap gewicht instellen op 4
* eigenschap AantalRechtstreeksOndergeschikten instellen op 3
* aan de List-eigenschap RechtstreeksOndergeschikte evenveel Sergeanten toevoegen als de waarde van AantalRechtstreeksOndergeschikten

De klasse Sergeant erft over van Onderofficier en heeft enkel een argumentloze constructor die het volgende doet : 
* eigenschap Sterren instellen op 1
* eigenschap gewicht instellen op 3
* eigenschap AantalRechtstreeksOndergeschikten instellen op 4
* aan de List-eigenschap RechtstreeksOndergeschikte evenveel Korporaals toevoegen als de waarde van AantalRechtstreeksOndergeschikten

De klasse Korporaal erft over van Troep en heeft enkel een argumentloze constructor die het volgende doet : 
* eigenschap Sterren instellen op 2
* eigenschap gewicht instellen op 2
* eigenschap AantalRechtstreeksOndergeschikten instellen op 5
* aan de List-eigenschap RechtstreeksOndergeschikte evenveel Soldaten toevoegen als de waarde van AantalRechtstreeksOndergeschikten

De klasse Soldaat erft over van Troep en heeft enkel een argumentloze constructor die het volgende doet : 
* eigenschap Sterren instellen op 1
* eigenschap gewicht instellen op 1
* eigenschap AantalRechtstreeksOndergeschikten instellen op 0

In je WPF venster zorg je er voor dat na het laden van je venster 1 of 2 generaals aanmaakt.  In principe zouden hierdoor automatisch ook alle andere militairen moeten aangemaakt worden.  

LstGeneraals vul je met die generaals.  

Klik je op een generaal dan :   
* dienen zijn Majoors afgebeeld te worden in lstMajoors
* dient onderaan de naam, de rang, het aantal sterren in de juiste kleur, en het totaal aantal ondergeschikten te verschijnen.  

Klik je op een majoor dan : 
* dienen zijn Luitenanten afgebeeld te worden in lstLuitenanten
* dient onderaan de naam, de rang, het aantal sterren in de juiste kleur, en het totaal aantal ondergeschikten te verschijnen.  

...

