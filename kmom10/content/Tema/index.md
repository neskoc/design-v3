---
Title: Tema
Description: Temabeskrivning
Template: tema
Hidden: true
---

## Temabeskrivning

### Typografi, designprinciper och designelement

I början bestämde jag mig för att göra alternativ 3 där jag skulle agera både kunden och utvecklaren. Projektet skulle vara min personliga profil.

För typografi valde jag följande fonter:

- Rubrikerna: Philosopher, sans-serif
- Resten: Open Sans, serif

Jag har valt Philosopher för den verkade vara populär fast inte för populär och jag gillade den. Sedan rekommenderade google några andra par-fonter och av dessa valde jag Open Sans för jag tyckte att den hade bäst läsbarhet. Roboto var också bra men den använde jag tidigare så jag ville testa något nytt.

Fontstorlekarna är följande baserat på best practices om relativa storlekar samt lagom spacing/vertikal rytm:

- brödtext
  - storlek: 1 rem
  - linjehöjd: 1.5
- magic-number: 1.5
- rubrik h1
  - storlek: 2.4 rem
  - margin båtten: 2 * magic-number
- rubrik h2
  - storlek: 2 rem
  - margin båtten: magic-number
- rubrik h3
  - storlek: 1.4 rem
  - margin båtten: 0

<b>Designprinciper och designelement</b>

Tanken var att ha en sida som både är visuellt tilltalande utan att vara för tung samt har hög läsbarhet. Dessutom används blånianser som både är lugnande men ger ett proffsigt intryck.  
Jag har valt lite konservativ framtoning för att jag vill lyfta fram den tekniska kompetensen.

Både färger och linjer (inramning) används för att lyfta fram innehållet.  
Exempelvis använder jag en genomskinlig bakgrundsfärg för att separera innehållet och från bakgrunden samtidigt som att det förbättrar läsbarhet.  
Dessutom separerar jag visuellt olika logiska delar med hjälp av inramning utan att det känns för mycket.

Jag använder också en del utrymme runtomkring olika block för att ge det lufig känsla. Dessutom underlättar blockupplägget ögat att följa texten och utökar läsbarheten. Texten balanseras också med strategiskt placerade bilder som också illustrerar innehållet men färgmässigt matchar resten av innehållet.

Symetri används både i sidled och vertikalt där blocken för det mesta är ungefär lika stora och/eller symetriska. Dessutom är olika textblock och bilder balanserade även till viss del med bakgrundsbilden.

Hierarki lyfts fram med olika rubrikstorlekar men också med hjälp av bakgrunsfärger.
Upplägget stödjer hur ögat förlyttar sig i västvärlden över en sidan:
- från toppen till botten: sidhuvud - huvudinnehåll - sidfot, logiska block efter varandra, rubrik - text
- från vänster till höger: logo - meny, flera spalter, bild -text alt. text -bild

### Färgpalett

Jag på nätet färgbeskrivningar för olika nationella flaggor och valde den ryska flaggans blå färg som grundfärg. Med hjälp av paletton.com genererade jag sedan färgpaletten (hittas i color-palett.scss).  

- grundfärg text: <div class="color" style="background-color: rgb(68, 68, 68); color:white">&nbsp;#444&nbsp;</div>
- sidhuvud rubrik, sidfot länkar: <div class="color" style="background-color:rgba(255,255,255,1); color:black">&nbsp;#fff&nbsp;</div>
- sidfot text: <div class="color" style="background-color:rgb(4, 60, 124); color:white">&nbsp;rgb(4, 60, 124)&nbsp;</div>
- sidhuvud/sidfot bakgrundsfärg: <div class="color" style="background-color:rgba(165,179,245,.7); color:black">&nbsp;rgba(165,179,245,.7)&nbsp;</div>
- sidhuvud meny, byline länkar: <div class="color" style="background-color: rgb(51, 81, 219); color:white">&nbsp;#3351db&nbsp;</div>
- sidhuvud meny aktiv: <div class="color" style="background-color:rgba(255,255,255,1); color:black">&nbsp;#fff&nbsp;</div>
- sidhuvud meny/sidfot länkar hover: <div class="color" style="background-color: rgb(68, 68, 68); color:white">&nbsp;#444&nbsp;</div>
- byline border: <div class="color" style="background-color: rgb(255, 127, 32); color:white">&nbsp;#ff7f20 (signalfärg)&nbsp;</div>
- main container bakgrunndsfärg: <div class="color" style="background-color: rgba(238, 238, 238, 0.8); color:black">&nbsp;rgba(238, 238, 238, 0.8)&nbsp;</div>
- block container bakgrunndsfärg: <div class="color" style="background-color: rgba(255,255,255,.5); color:black">&nbsp;rgba(255,255,255,0.5)&nbsp;</div>
- block inramningsfärg: <div class="color" style="background-color: rgb(165, 179, 245); color:black">&nbsp;rgb(165, 179, 245)&nbsp;</div>

### Beskrivning av SASS-koden

Huvudinnehållet finns i style.scss-filen.  
Denna fil innehåller grundinställningar och grunddefinitioner av designelement som html, body, main, container osv.

I början av filen inkluderas andra sass-filer dels för att ha en logiskt uppdelad struktur dels för att underlätta stödet för två olika designmallar. Vissa filer är gemensamma för båda mallarna medan alternativa mallens sass-filer har tillägg "-dark" i namnet. Här beskrivs bara grundmallen.

- @import '../../node_modules/normalize.css/normalize'  
  Den filen är egentligen en node-modul som normaliserar värdena så att innehållet ser likadant ut i de flesta webbläsare.

- @import 'variables'  
  Här definieras gemensamma variabler som avnänds genomgående i scss-filerna. Här definieras även fonter.  
  Huvudfilen innehåller variabler som definierar färger.
  Den filen importerar även even andra egna hjälpfiler:
  - @import 'color-palett': definerar komplett färgskala (bara en mindre del används)
  - @import 'common-variables': Här definieras olika mått som skärmens maximala bredd, fontstorlekar, magic-nummer och marigins.
  - @import 'common-variables-footer'

- @import 'typography'  
  Här definieras typografiska element som används för design.

- @import 'common'  
  Tanken var att ha gemensamma definitioner här men upplägget blev en annan och filen är kvar mest av historiska skäl.

- @import 'header'
  Innehåller difinitioner specifika för headern.

- @import 'byline'
  Definitioner specifika för byline-blocket.
 
- @import 'footer'  
  Definitioner specifika för fotblocket.

- @import 'report', @import 'kmoms'
  Namnen är kvarlevor från kmom1-6. Det är bara reportfilen som aktivt används.

- @import 'responsive'  
  Majoritet av designelement som är specifika för responsivitet hittas här.  
  Dessa avnänds för båda mallar medan alternativmallen har sina designspecifika anpassningar i slutet av style-dark.scss.
