---
Title: Uppdrag 6
Description: Bilder och laddningstider
Date: 2021-05-25
Template: analys
---

## Kmom10. Uppdrag 6: Analys av bilder, laddningstider och användbarhet

Uppdraget går ut på att göra en analys inom design av webbplatser: bilder och laddningstider dvs. att mäta hur sidan laddas och om den innehåller några saker som kan förbättras med tanke på laddningstid och användbarhet.

För varje webbplats (både Mobile och Desktop):
- tre sidor som skall väljas ut för mätning med Google Pagespeed
- för varje sida mätningen skall upprepas tre gånger och snittvärdet redovisas

Den analyserade sidan hittas under [Kmom10 home](http://www.student.bth.se/~necu20/dbwebb-kurser/design/me/kmom10/)  
![Kmom10 home](%assets_url%/img/Design-kmom10.png "Kmom10 home"){.image}

### Verktyg

- __Google PageSpeed Insights__ för att få fram ett generellt betyg på skalan 1 till 100
- __Mozilla DevTools: Network__ för att få ta fram antal förfrågningar, laddningstider i sekunder och nedladdningstraffiken i Megabyte
- __Libre Office__ för att sammanställa mätresultat i ett kalkylark


### Resultat

Samtliga [mätresultat](%assets_url%/Sitespeed-analysis-kmom10.ods) delvis rådata
men också snittade värden grupperade efter site och undersidor finns som ett ods-document.



Resultat från både DevTools och PageSpeed Insights är i princip samstämmiga och över alla undersidor dvs. de indikerar väldigt höga värden 96-100% och 04 - 0.5 sekunder laddningstid. Även mängd data som överförs är rätt så låg, 03 - 2MiB viket betyder att sidorna upplevs som snabba även om nätverkshastighet inte är hög.

#### PageSpeed Insights

Nedan illustreras värdena för home-sidan.
![Google PageSpeed Insights](%assets_url%/img/PageSpeed_Insights.png "Google PageSpeed Insights"){.image}

#### DevTools Network

Med tortdiagram nedan illustrateras hur fördelningen mellan olika typer av innehåll viktas inom home-sidans http-response.
![Mozilla DevTools Network Circle Diagram](%assets_url%/img/Network-broadband-circel-diagram.png "Mozilla DevTools Network tårtdiagram"){.image}
Man kan se att bilderna förbrukar i princip 70% (tid) till 99% (datamängd) av nätverksresurserna.

På följande bild illustreras effekten av mellanlagrade element.
![Mozilla DevTools Network Content](%assets_url%/img/Network-content-transfer.png "Mozilla DevTools Network Content"){.image}

Utifrån mätdata kan man utläsa att mobilvarianterna brukar ligga på nästan samma nivåer som skrivbordsvarianterna. Anledningen till detta är att mobilvarianten enbart är anpassat med hjälp av css och det finns ingen optimerad och dedikerad version just för de mobila enheterna.  
I och med att hastigheterna är i överlag höga finns egentligen inget större behov för en mobilvariant specialoptimerad för lägre nätverkshasigheter.

En annan intressant sak är användning av mellanlagringen på klientsidan.
Varje mätning gjordes tre gånger och sedan snittades resultatet.  
Varje första mätning gjordes med tömd cache medan två efterföljande mätningar gjordes utan dess tömning.  
Detta förklarar de lägre värdena för samtliga kolumner i mätningarna nr2 och 3.

### Förbättringspotential

1. I http-response header kan man ange max-age som skulle förbättra laddningstider upprepade besök.

2. För att minska väntetiden kan man i html-headern ange <link rel="preload"> för att priotiera hämtning av vissa resurser som javascript eller css-fil(er).


3. Storlek på vissa bilder kan bättre anpassas (bilden kan komprimeras) till den faktiska storleken som visas på skärmen.

### Övrigt

Jag brukar använda olika plugins för att blockera annonser och dylikt men dessa hade inte behövt stängas av för att de testade sidorna inte missbrukar bandbredden.  
Med andra sidan upplevelsen av hastigheten kommer vara samma oavsett om man använder sig av tillägg till webbläsaren oavsett om det er addblock-er eller skydd för personlig integritet.

__Författare__: Nenad Cuturic.
