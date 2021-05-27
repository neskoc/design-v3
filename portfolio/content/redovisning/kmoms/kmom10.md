---
Title: Kmom10
Description: Redovisning av kursmoment 10
Date: 2021-01-07
Template: kmoms
---

## Kursmoment 10: Redovisning

### Uppdrag 1: Webbplats

Jag har valt att skapa en webbplats med mig själv som kund. För att börja med utgick jag ifrån min tidigare portfolio men det blev en del förändringar/förbättringar.  
Upplägget är detsamma: sidhuvud, huvudinnehåll, byline och sidfot.
Det som är nytt är färgpalett, typsnitt, bilder, mer designelement och bättre responsivitet.  
Jag använder friskt både grid och flexbox men så här i efterhand skulle jag har hållit mig nog bara till flexbox.

Jag använder cimage för att ändra storleken för image men det enda stället där det verkligen har en nytta är för en bild som på about-sidan som för det mesta används som utfyllnad och balans.
När strukturen går  från kolumner till rader plattas bilden till och går från en stående rektangel till en liggande fast mindre.

Tyvärr blev det en hel del html inne i markdown-filer. I och med att jag valt att även göra alternativt tema har jag försökt tänka på det från början. Temaförändringar styrs enbart med hjälp av sass-filer.


### Uppdrag 2: Tema

En detaljerad beskrivning av temat hittas under den gömda sidan (länk hittas på about-sidan) http://localhost/dbwebb-kurser/design/me/kmom10/Tema Därför har jag lite svårt att bestämma mig om vad som skall tas upp (upprepas) här.  
Jag har valt två fonter: Philosopher och Open Sans som också är nerladdade. Dessa fonter är av google också rekommenderade att paras ihop.

I mitt arbete med temat försökte jag få med så många som möjligt av de rekommenderade designprinciperna/elementen. Jag använder mig av linjerna, färgerna, symmetri, genomsynlighet, balans, hierarki, kontrast (bakgrundsbild exempelvis), inramning, riktning och sunda typografiska regler i större eller mindre grad.

Till skillnad från tidigare kmoms har jag gjort temat mer luftig och lättare med ganska bra balans mellan de olika sidorna (ingen sida känns för tung). Även färgerna är valda för att öka läsbarhet.

### Uppdrag 3: Responsivitet och tillgänglighet

Webbplatsen använder sig av två till tre kolumner på större enheter/skärmar.
Dessa sedan kollapsar till en kolumn ovanpå varandra. De flesta bilderna visar då inte.  
Även inramningen tas bort och punkter centreras mot vänster.
På större enheter finns mer ”luft” på sidorna men dessa minskas på de mindre enheterna utan att läsbarheten försämras.

Menyn i sidhuvudet kollapsar till en s.k. hamburgersymbol som expanderas i en kolumn med gott om utrymme att gör val även med tjocka fingrar. Jag brukar generellt ha problem med mina när jag använder beröringskänsliga skärmar på mobila telefoner i synnerhet när jag skall skriva text.
Samtliga sidor får 100% i ”accessibility” i Lighthouse och samtliga färgfilter från https://www.toptal.com/designers/colorfilter/ verkar ge bra resultat utan större avvikelse mot originalen.

### Uppdrag 4: Tema alternativt

För alternativt tema har jag utgått ifrån det mörka temat jag hade tidigare dvs. mitt alternativt tema skulle kunna kallas för en sorts mörk tema.  

I det här fallet har jag valt att göra ett renare tema utan så mycket lull-lull (inga bakgrundsbilder, fonter utan serifer, tydliga kontraster och inga bakgrundsfärger för huvudinnehållet.  
Även i stället för inramning har jag valt raka linjer (vågrätta alternativt lodrätta) som avskiljare.
Man känner igen sig från ursprungsdesign men man får en business-känsla.

Det blev lite jobb med vissa bilder och logon för att dessa skulle se bra ut i båda teman men till slut har jag lyckats att det ser bra ut i båda alternativen.

För nya fonter har jag valt Merriweather (brödtext) och SourceSansPro (rubriker) båda utan serifer. Texten är lättläst och fonterna ger en modern känsla (inga serifer).

### Uppdrag 5: Analys aktuell webbplatsdesign

Som i tidigare kmoms har jag gjort analyserna själv.

Här har jag valt att göra en analys av aktuell webbplatsdesign och trender för svenska kommuner.
För att få så bra teckning som möjligt har jag har valt att analysera 5 kommuners webbplatser där 2 är bland de största, 2 bland de medelstora och en bland de minsta.

För verktyg har jag valt följande:
- WaybackMachine - verktyg för att kolla förändringarna genom tiden
- BuiltWith - en gratis variant av den tjänsten för att kolla använd teknik

Utifrån analysen kan man se att uppdateringfrekvenser för de olika kommuners webbplatser är ganska lika över en längre tidsperiod.
Bland CMS är bilden rätt så diversifierad och Wordpress verkar ha fått en relativt stark ställning.

På serversidan är det en ganska balanserad bild bland de olika ramverken (java ee/.net/php). Även bland webbservrarna är fördelningen ganska jämn där nginx är lite av en uppstickare.

jQuery är fortfarande den dominerande JS-ramverk.  
Trots den starka ställningen som skyddet av personlig information har i Sverige samt att det handlar om offentlig sektor använder alla kommuner Google Analytics. Detta känns som väldigt tveksamt val.

### Uppdrag 6: Analys av bilder och laddningstider

Jag har valt att göra en analys inom design av webbplatser: bilder och laddningstider dvs. att mäta hur sidan laddas och om den innehåller några saker som kan förbättras med tanke på laddningstid och användbarhet.

För varje webbplats (både Mobile och Desktop) analyseras:
- tre sidor med Google Pagespeed
- för varje sida mätningen upprepas tre gånger och snittvärdet redovisas

Samtliga mätresultat delvis rådata men också snittade värden grupperade efter sidor och enhet finns som ett ods-document.

Resultat från både DevTools och PageSpeed Insights är i princip samstämmiga och över alla undersidor dvs. de indikerar väldigt höga värden 96-100% och 04 - 0.5 sekunder laddningstid. Även mängd data som överförs är rätt så låg, 03 - 2MiB viket betyder att sidorna upplevs som snabba även om nätverkshastighet inte är hög.

Utifrån mätdata kan man utläsa att mobilvarianterna brukar ligga på nästan samma nivåer som skrivbordsvarianterna. Anledningen till detta är att mobilvarianten enbart är anpassat med hjälp av css och det finns ingen optimerad och dedikerad version just för de mobila enheterna.  
I och med att hastigheterna är i överlag höga finns egentligen inget större behov för en mobilvariant specialoptimerad för lägre nätverkshasigheter.

### Allmänt om projektet

Jag gjorde misstaget i början att jag bestämde mig att göra en webbpresentation som jag själv skulle kunna använda i framtiden. Det största misstaget var att jag inte ville kompromissa med mig sjäv.  
Jag fastnade i att kravspecifikationen inte riktigt passade på hur jag egentligen skulle ha velat lägga upp/fördela innehållet.  
I och med att jag aldrig arbetade som freelancare hade jag svårt att komma med en trovärdig portfolio. Till slut bestämde jag mig att skjuta upp avslutning av projektet för senare tillfälle.

Därefter tog jag upp tråden i slutet av läsperioden 3 men fastnade på samma ställe. Nu i slutet av läsperiod 4 fattade jag  beslut att tänja lite på mina egna kriterier och fuska med innehållet där jag valt att använda olika skolprojekt för portfolion. Det kändes inte helt rätt men samtidigt har mina planer på egenföretag luckrats upp så behovet att vara 100% korrekt vägde inte så tungt längre.

Att jag dröjt med att göra klart projektet hade både sina för- och nackdelar.  
Om jag börjar med nackdelarna låg dem i att jag fick starta om flera gånger och med andra ord blev det allt längre uppvärmningstid ju längre tiden gick.

Fördelarna var att vi gick igenom JavaScript så jag kunde förstå hur skriptet jag använde för responsive meny fungerade och det blev inte längre så skrämmande.  
Den andra fördelen är att vi gick igenom olika designprinciper i webbapp-kursen vilket också gjorde att jag förstod bättre olika designkoncept samt att exempelvis flexbox kändes rätt så naturlig att använda nästan överallt.

Så här i efterhand skulle jag ha gjort hela upplägget på ett annat sätt men att komma till denna insyn behövda jag göra alla dessa fel jag gjort och lösa de olika problem jag stött på. Med andra ord trots att jag inte är helt nöjd med utfallet har jag fått väldigt mycket nytta av det. Sedan brukar jag behöva lite tid för att nya saker och ting skall sätta sig.

### Allmänt om kursen

Generellt har jag svårt för design så jag upplevde kursen som ganska besvärlig fast jag lärde mig väldigt mycket. Jag har skrivit en hel del om detta i mina redovisningar för tidigare kmoms så jag skall inte upprepa mig.

Så här i efterhand tycker jag att kursmaterialet var bra och jag har sparat en hel del länkar som jag troligtvis kommer ha mer nytta av framöver. Fast under själva kursen tyckte jag att vissa saker hade kunnat läggas upp på det annat sätt och med en annan ordning. För en design-analfabet tyckte jag att det var lite svårt att ta sig igenom.  
Även pico var inte så lämplig för kursen tycker jag men jag har svårt att tänka mig ett bättre alternativ för ett sådant kursupplägg.

Genomgångarna var på en lagom hög nivå tycker jag medan föreläsningarna tyckte jag var ganska långsamma och tog upp för lite saker (jag brukade spela upp de på 1,3-1,4 hastighet).

Betyget för kursen är en 8 tycker jag och även om det inte är högre betyg är jag väldigt nöjd med kursen (jag uppskattar den mycket mer nu än i december).

### Avslutande kommentar

Det blev lite förvirrat hur man skall hantera repositori.
Jag har kvar gamla portfolio och sedan har jag kmom10 och man skulle ha följt instruktionerna skulle det bli omöjligt att få båda i den gamla repon.  
Därför har jag skapat en ny på me-nivån med portfolio och kmom10 under den.  
Denna har nu fått version v.10.1.0 medan ursprungsrepo fanns under portfolio.
