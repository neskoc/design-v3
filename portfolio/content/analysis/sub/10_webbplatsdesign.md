---
Title: Uppdrag 5
Description: Analys av kommunernas aktuella webbplatsdesign
Date: 2020-12-22
Template: analys
---

# Kmom10. Uppdrag 5: Analys av kommunernas aktuella webbplatsdesign

Uppgiften går ut på att göra en analys av aktuell webbplatsdesign och trender för 3 till 5 svenska kommuner.

## Urval

För att få så bra teckning som möjligt har jag har valt att analysera 5 kommuners webbplatser där 2 är bland de största, 2 bland de medelstora och en bland de minsta.

1. [__Stockholms stad__](https://start.stockholm/)
2. [__Göteborgs stad__](https://goteborg.se/)
3. [__Gävles kommun__](https://www.gavle.se/)
4. [__Sundsvalls kommun__](https://sundsvall.se/)
5. [__Härnösands kommun__](https://www.harnosand.se/)

### Verktyg

- [__WaybackMachine__](https://webb.archive.org) - verktyg för att kolla förändringarna genom tiden
- [__BuiltWith__](https://builtwith.com) - en gratis variant av den tjänsten för att kolla använd teknik

## Analys av webbplatserna

Jag har valt att analysera aktuella trender inom tekniken som används för webbplatsdesign.
Dessutom har jag valt att kolla tillbaka i tiden med hjälp av WaybackMachine för att se historisk utveckling
samt för att kontrollera hur färsk informationen är.

###  Förändringar genom tiden

Ursprungligen hade jag en idé att försöka göra en djupare analys av historiska versioner med hjälp av WaybackMachine.
Det verktyget visade sig vara väldigt trög och buggig (instabil) samt den extraherade informationen av för av låg kvalité för en sådan analys.
Verktyget användes därför bara för att se historiska trender för förändringarna på webbplatserna.

Nedan kan man se tidsskalor som representerar frekvenserna av förändringarna på webbplatserna sedan WaybackMachine började samla in data (någon gång under 1996).

- Göteborg
    ![Göteborg](%base_url%/image/WaybackMachine_Goteborg.png&h=70 "Göteborg"){.image}
- Stockholm  
    ![Stockholm stockholm.se](%base_url%/image/WaybackMachine_Stockholm.png&h=70 "Stockholm stockholm.se"){.image}
    Ny url (stockholm.se -> start.stockholm, stockholm.se vidarebefordrar till start.stockholm)  
    ![Stockholm start.stockholm](%base_url%/image/WaybackMachine_start.Stockholm.png&h=70 "Stockholm start.stockholm"){.image}
- Gävle
    ![Gävle](%base_url%/image/WaybackMachine_Gavle.png&h=70 "Gävle"){.image}
- Sundsvall
    ![Sundsvall](%base_url%/image/WaybackMachine_Sundsvall.png&h=70 "Sundsvall"){.image}
- Härnösand
    ![Härnösand](%base_url%/image/WaybackMachine_Harnosand.png&h=70 "Härnösand"){.image}

Man kan se att samtliga webbplatser har ganska lika trender vad det gäller förändringarnas frekvens:

1. vågformade långtidstrender med stora
    - vågtoppar: 2005 och 2019/2020 samt
    - vågdalar: 1996/1997 och 2009/2010
2. korttidstrender: dessa är mer oregelbundna och svåra att identifiera

Man kan se att de största och mest frekventa förändringar skett under 2019/2020 i synnerhet vid årsskiftet 2018/2019 där det blev en brant ökning på samtliga webbplatser förutom Stockholm. Så man kan gissa att även någon större förändring av webbplatsdesign skedde under samma period.
Därmed skulle man kunna påstå att det man ser på dessa sajter idag verkligen representerar trendutvecklingen inom webbplatsdesign för kommunernas webbplatser.

### Bakomliggande teknik

|  | Google Analytics | Ramverk | Server | CMS | CDN | AV | JS Ramverk | Kartor |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| __Göteborg__ | x | Java EE | Apache, IIS | Websphere, Siteimprove | GStatic | YouTube | jQuery | Mapbox |
| __Stockholm__ | x | - | - | EPiServer | GStatic, CloudFront | - | Preact, React, jQuery, Lightning | - |
| __Gävle__ | x | .NET, PHP | nginx, IIS | Wordpress | CDN, GStatic, jsDeliver, Cloudflare | - | jQuery, Typeahead, FitVids, Underscore, KineticJS, Moment | - |
| __Sundsvall__ | x | .NET, PHP, OpenResty | nginx, IIS | Wordpress | CDN, GStatic, jsDeliver, Cloudflare | - | jQuery, Typeahead, Slick, LABjs, Raphael | Google |
| __Härnösand__ | x | Java EE | Apache, nginx | Siteimprove, SiteVision | GStatic, StackPath, BootstrapCDN | YouTube | jQuery, Typeahead, FitVids, Underscore, RequireJS, KineticJS, Moment, Backbone, Popper, Redux | Google |

#### Användar- och trafikanalys

Samtliga kommuners webbplatser använder sig av __Google Analytics__ men enbart Härnösand anonymiserar IP-adresser.  
De andra verktygen som förekommer på enstaka siter är: Vizzit (förekommer på två), Usabilla och Pingdom RUM.

Med andra ord är Google dominant.

#### Ramverk (serversidan)

__Java EE__ (2), en kombination av __ASP .NET/PHP__ (2) och en utan något identifierbart ramverk fast i och med att det är EPiServer som använder java kan man utgå ifrån att det är Java EE där också.

Här ser vi en ganska jämn fördelning mellan Java, .net och php.

#### Webbserver

Här har vi 3 __nginx__, 3 __IIS__, 2 __Apache__ och en kunde inte identifieras.
IIS har under de senaste åren tagit tillbaka en del av i synnerhet företagsmarknaden. Det som är nytt, i all fall för mig, är att nginx har fått så stark position.
I och för sig kan det vara så att Apache fortfarande ligger bakom men det är något man kan bara spekulera om.

#### CMS

Här kan vi se __Wordpress__ och __Siteimprove__ med var sina 2 kommuner samt SiteVision, EPiServer och Websphere med 1.
Det är de två kommuner som är medelstora som valt att använda enbart Wordpress dvs. en budget-variant.
Sedan har vi två kommuner som kör blandat fast kommersiellt och Stockholm som kör enbart EPiServer vilken nog är den dyraste.
För mig var det lite förvånande att så många valt Wordpress. Den verkar har fått ett bra fästa även bland medelstora organisationer
i alla fall med svenska mått mätt.

Här kan vi även se varifrån PHP kommer in i bilden (Wordpress).

#### JavaScript ramverk

Det är en uppsjö av olika ramverk som dyker upp men det är bara __jQuery__ som används på varje webbplats.
Så nykomlingarna har inte lyckats etablera sig bland svenska kommuner verkar det som.

#### Content Delivery Network (CDN)

Var ligger alla dessa js-ramverk då? Ja, storebror Google hanterar en hel del för att alla har valt Google Analytics för användarstatistik
och dess skript hämtas oftast från __GStatic__-servrar.  
Bortsett Google ligger __Cludflare__ och __jsDeliver__ bra till med var sina 2 kommuner. Sedan förekommer en del andra.

#### Media (Video)

Ingen av kommunerna har valt att ha videoinnehåll på första sidan. Troligtvis konsekvensen av att man inte vill dra ner hastigheten.  
Det som visas för Göteborg (youtube) kommer nog från någon undersida.
Det är märkligt att det inte förkommer på andra siter (på undersidorna) också.

#### Kartor

Av de analyserade webbplatserna använder sig två av __Google Maps__, en av __Mapbox__ (en uppstickare)
 och två använder sig inte av någon karttjänst fast kollar man sidfoten för Gävle kan man hitta länken till google-kartan och
 fast builtWith indikerar att Härnösand har en Google-karta någonstans lyckas jag inte hitta den (det måste vara ganska undangömt).  
Att Stockholm inte har några kartor är kanske förståeligt för start.stockholm är ett skyltfönster för de olika förvaltningarna och har ingen egen besöksadress.

### Avslutande ord

Man kan se att uppdateringfrekvenser för de olika kommuners webbplatser är ganska lika över en längre tidsperiod.  
Bland CMS är bilden rätt så diversifierad och Wordpress verkar ha fått en relativt stark ställning.

På serversidan är det en ganska balanserad bild bland de olika ramverken (java ee/.net/php).
Även bland webbservrarna är fördelningen ganska jämn där nginx är lite av en uppstickare.

jQuery är fortfarande den dominerande JS-ramverk.

Till slut trots den starka ställningen skyddet av personlig information har i Sverige samt att det handlar om offentlig sektor
använder alla kommuner Google Analytics. Jag skulle vilja påstå att det är väldigt tveksamt om exempelvis kommunerna verkligen
behöver en sådan tjänst. Den information som brukar användas kan oftast med relativt små resurser ordnas lokalt.  
Sedan tycker jag det är högt tveksamt att offentlig sektor så lättvindigt skickar en sådan information till en kommersiell aktör
som dessutom är (ö)känd för att samla och (miss)bruka alla sort of personliga uppgifter.
