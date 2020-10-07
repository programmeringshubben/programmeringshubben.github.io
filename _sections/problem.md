---
title: Problemlösning
icon: fa-lightbulb
order: 7
---

I denna sektion så hittar du övningsuppgifter utan några lösningsförslag. Tanken med dessa uppgifter är att du ska kombinera de koncept som har behandlats i tidigare sektioner för att lösa problem på egen hand. Om du kör fast så kan du i första hand återgå till relevanta tidigare sektioner, se över kursmaterialet eller Googla efter tillvägagångssätt på egen hand.

## Uppgiftsförteckning ##

Uppgift 1 | Summering och sammanslagning av arrayer (Enkel)
----------|-------------------------------
Beskrivning | Skriv en metod, <code>SumArrays</code>, som tar emot två arrayer av heltal som argument (<code>arrayA och arrayB</code>) och returnerar en array - <code>arrayC</code> - som innehåller summan av talen på resp. position. Dvs. att om värdet på position 0 i <code>arrayA</code> är 5 och värdet på position 0 i <code>arrayB</code> är 13 så ska position 0 i <code>arrayC</code> innehålla värdet 18 osv.<br><br> **OBS!** Om den ena arrayen är längre än den andra så ska värdet från den längre arrayen placeras i <code>arrayC</code>.

Uppgift 2 | Prisberäkning för inträde (Enkel)
----------|----------
Beskrivning | Skriv en metod, <code>AdmissionPrice</code>, som beräknar priset för inträde till ett nöjesfält baserat på gästernas ålder. Antalet gäster som tillhör gruppen bestäms utav användaren som skriver in <code>N</code>. Därefter hämtas samtliga av dessa gästers namn och deras resp. ålderin. <br> Pristabellen som gäller är:<br> - Barn (3-12): 50 kr. <br> - Pensionär (65+): 75 kr. <br> Samtliga resterande åldersgrupper betalar alltid 110 kr. <br> Om gruppen består utav fler än 4 gäster så ges en rabatt på 20% på totalpriset. Metoden ska efter beräkning skriva ut antalet gäster i gruppen och den totala summan.

Uppgift 3 | BMI kalkylator (Enkel)
----------|----------
Beskrivning | Skriv en metod som beräknar BMI (body mass index) värdet för en person. Metoden ska läsa in personens längd och vikt och därefter nyttja en utav två formler för att utföra beräkningen. Vilken formel som ska nyttjas beror på om längd och vikt anges enligt metriska eller imperiska mått (dvs. exempelvis cm gentemot feet + inches). Den metriska formeln är:<br><br> BMI = (weight / (height * height)) * 703 <br><br>och den imperiska formeln är: <br><br>BMI = (weight / (height * height))

Uppgift 4 | Ordbyte (Enkel)
----------|----------
Beskrivning | Skriv en metod, <code>ReplaceWord</code>, som byter alla förekomster av ett utvalt ord mot ett annat. Metoden ska ta emot en mening som argument och därefter fråga användaren vilket ord som ska bytas ut samt vad det ska bytas ut mot. Om ordet som ska bytas ut inte förekommer i meningen så ska användaren meddelas om detta och ges möjligheten att ange ett annat ord.

Uppgift 5 | Element på udda positioner (Enkel)
----------|----------
Beskrivning | Skriv en metod som tar emot en array av heltal och returnerar samtliga element som förekommer på udda indexpositioner. Dvs. att givet exempelvis arrayen [3, 5, 10, 2, 6] så ska 5 och 2 returneras. Om arrayen inte har några udda positioner så ska <code>null</code> returneras.

Uppgift 6 | Guessing game (Enkel)
----------|----------
Beskrivning | Skriv ett program som tillåter en användare att gissa på ett "hemligt" nummer. Efter varje gissning så ska programmet skriva ut huruvida gissningen var lägre eller större än det hemliga numret. Denna process ska återupprepas tills dess att användaren gissar rätt eller anger "EXIT". Om användaren gissar rätt så ska antalet gissningar som krävdes för att komma fram till svaret skrivas ut.

Uppgift 7 | LongestWord (Enkel)
----------|----------
Beskrivning | Skriv en metod, <code>LongestWord</code>, som tar emot en mening och returnerar det längsta ordet i meningen. Om det förekommer två eller flera ord - vilka samtliga har samma längd och är längre än resterande ord i meningen - så ska det första ordet returneras. Dvs. att givet exempelvis meningen <code>"I love cats"</code> så ska <code>"love"</code> skickas tillbaka. <br><br>**TIPS!** Nyttja den inbyggda metoden <code>Split</code> för att dela upp meningen på mellanslag.

Uppgift 8 | "Enkel" addition (Enkel)
----------|----------
Beskrivning | Skriv en metod, <code>SimpleAdd</code>, som tar emot ett heltal (n) och returnerar summan av alla heltal från 1 till och med n. Dvs. att om n är 12 så ska 78 returneras (1+2+3...11+12).

Uppgift 9 | ToggleString (Enkel)
----------|----------
Beskrivning | Skriv en metod, <code>ToggleString</code>, som tar emot en sträng och returnerar samma sträng efter att ha bytt ut alla gemener mot versaler och versal mot gemener. Dvs. att givet strängen "HelLo wORld" så ska "hELlO WorLD" returneras. Strängen måste vara längre än 1 tecken men mindre än 100 tecken, om detta krav inte uppfylls så ska en tom sträng returneras.

Uppgift 10 | PowerOf (Enkel)
----------|----------
Beskrivning | Skriv en metod, <code>PowerOf</code>, som tar emot två heltal (<code>n</code> & <code>p</code>). Metoden ska sedan returnera heltalet <code>n</code> upphöjt i <code>p</code>. Dvs. att givet heltalen 5 och 3 så ska 125 returneras. Om det istället är heltalen 5 och 4 så ska 625 returneras osv.<br><br>**TIPS!** Nyttja datatypen <code>long</code> istället för <code>int</code> för att undvika att heltalet blir för stort (det största möjliga värdet som en <code>int</code> kan innehålla är 32767). ***NOTERA*** att den inbyggda metoden <code>Math.Pow</code> inte ska nyttjas för att lösa uppgiften.

<table>
  <thead>
    <tr>
      <th>Uppgift 11</th>
      <th>FizzBuzz (Enkel)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>FizzBuzz</code>, som tar emot 3 heltal. <code>n</code> som representerar antalet iterationer, <code>x</code> som representerar det första delbara talet och <code>y</code> som representerar det andra delbara talet. Metoden fungerar på så sätt att den skriver ut alla tal mellan 1 till och med <code>n</code>. Om ett tal dock är <em>jämnt delbart</em> med <code>x</code> så ska "Fizz" skrivas ut framför talet. Om talet är <em>jämnt delbart</em> med <code>y</code> så ska “Buzz“ skrivas ut framför talet och om talet är <em>jämnt delbart med <code>x</code> och <code>y</code></em> så ska “FizzBuzz“ skrivas ut framför talet. <strong>OBS!</strong> Varje tal ska enbart skrivas ut en gång. Exempel på interaktion med metoden kan tänkas se ut enligt följande:<br>
        <table class="examples">
          <thead>
            <tr>
              <th>Körexempel</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <pre lang="csharp" class="highlight">
//Om x = 2 och y = 4
1
Fizz 2
3
FizzBuzz 4
5
Fizz 6
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
  </tbody>
</table>

Uppgift 12 | Palindrom (Enkel/Medel)
----------|----------
Beskrivning | Skriv en metod, <code>IsPalindrome</code>, som avgör om en sträng är ett palindrom eller ej. Ett palindrom är ett ord eller en mening som är exakt likadan skrivet baklänges, t.ex. "Sirap i paris". Metoden __ska__ ta mellanslag, specialtecken och versaler/gemener i beaktelse när den avgör om strängen är ett palindrom eller ej.

Uppgift 13 | Hotellbokning (Enkel/Medel)
----------|----------
Beskrivning | Inom en hotellverksamhet önskar man få överblick över vilka rum som är bokade samt vilka som är lediga. Skriv först ett program (eller en metod) som läser in "bokat" kontra "ledigt" i en array som består utav 15 platser. Varje plats i arrayen motsvarar ett rum på hotellet.<br><br>b. Utöka sedan programmet genom att lägga till möjligheten att genomföra bokningar. Vid en bokning så ska det första lediga rummet i rumslistan (arrayen) identifieras och sedan ändra värde till "bokat".<br><br>c. Utöka sedan programmet ytterligare genom att låta användaren ange om ett rum önskas bokas eller avbokas. Om rummet ska bokas kan implementationen i b) nyttjas,  om en avbokning ska ske så behöver vi dock kunna hantera detta. Vid en avbokning så ska rumsnummer anges och efter avbokning så ska värdet i arrayen ändras till "ledigt".

Uppgift 14 | Hitta medianen (Enkel/Medel)
----------|----------
Beskrivning | Medianen är det tal som representerar mitten i en talföljd. Om vi exempelvis har heltalen 10, 63 och 15 så agerar 15 medianvärdet. Om vi istället har heltalen 10, 63, 15 och 25 så blir medianen istället 20 (15 + 20 / 2). Skriv en metod som tar emot en array av heltal som en parameter och returnerar medianen. <br><br>**TIPS!** Tänk på att arrayen först och främst ___bör___ sorteras i storleksordning. Uppgift 23, SortArray, under sektionen "Iteration/arrayer" kan nyttjas för detta syfte. Efter detta så kan vi antingen enkelt plocka ut värdet i mitten (om arrayen består utav ett udda antal element) eller så behöver vi identifiera de två mittenvärden som finns i arrayen och utföra beräkningen enligt ovan exempel.

Uppgift 15 | StringFormat (Enkel/Medel)
----------|----------
Beskrivning | Skriv en metod, <code>StringFormat</code> som tar emot en array av strängar och skriver ut samtliga strängar i arrayen enligt nedan format: <br><br>Om arrayen innehåller <code>[apples, oranges]</code> så får vi: <code>apples and oranges</code><br> Om arrayen istället innehåller flera strängar t.ex. <code>[apples, oranges, bananas]</code> så får vi istället: <code>apples, oranges and bananas</code><br><br>**TIPS!** Nyttja metoden <code>string.Split</code>.

Uppgift 16 | Tillägg till array (Enkel/Medel)
----------|----------
Beskrivning | Skriv en metod, <code>AddInOrder</code>, som tar emot en array av heltal samt ett heltal, lägger till heltalet i arrayen och sedan returnerar arrayen. Heltalet ska placeras i korrekt ordning i arrayen. Om heltalet redan förekommer i arrayen så ska tillägget inte ske. **OBS!** Metoden kan föreutsätta att arrayen redan är placerad i storleksordning, men du får självfallet nyttja en sorteringsalgoritm om du vill utöka metoden själv.

Uppgift 17 | AlternateMerge (Medel)
----------|----------
Beskrivning | Skriv en metod, <code>AlternateMerge</code>, som tar emot två arrayer av heltal och returnerar en array som innehåller samtliga element från resp. array. Elementen ska dock placeras i turordning där vi först tar elementet på position 0 i den första arrayen följt av elementet på position 0 i den andra arrayen osv. Dvs. att givet arrayen [3, 5, 10, 2, 6] och [8, 1, 4, 12, 7] så skulle följande array returneras: [3, 8, 5, 1, 10, 4, 2, 12, 6, 7].

<table>
  <thead>
    <tr>
      <th>Uppgift 18</th>
      <th>Beräkning av heltal (Medel)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod som läser in ett godtyckligt antal positiva eller negativa tal från användaren. Metoden ska sedan räkna ut antalet positiva resp. negativa tal. För att avsluta inmatningen så ska användaren ange "e". Metoden ska då avslutningsvis skriva ut antalet positiva och negativa tal. Exempel på interaktion med metoden:<br>
        <table class="examples">
          <thead>
            <tr>
              <th>Körexempel</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <pre lang="csharp" class="highlight">
1
-4
-1
0
6
12
e
Antal positiva tal: 3
Antal negativa tal: -2
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
        <strong>NOTERA</strong> att "0" inte ska tillgodoräknas som ett positivt eller negativt tal. <strong>TIPS!</strong> Nyttja en <code>while</code>-loop för att läsa in heltal från användaren.
      </td>
    </tr>
  </tbody>
</table>

Uppgift 19 | Beräkning av SGD (Medel)
----------|----------
Beskrivning | Den största gemensamma delaren (SGD) för ett antal heltal är det största heltalet som talen kan delas med utan att ge någon rest. Exempelvis är <code>SGD(6, 9) = 3</code> då 3 är det största talet som är delbart med både 6 och 9. Skriv en metod som beräknar och returnerar den största gemensamma delaren för två heltal. <br><br>För att läsa mer om SGD och se mer utförliga exempel på hur processen går till så kan följande länk nyttjas: [SGD med Euklides algoritm](http://www.matteguiden.se/matte-diskret/de-hela-talen/storsta-gemensamma-delare/). **TIPS!** Nyttja modulus för att avgöra huruvida divisionen resulterar i rest kombinerat med iteration för att identifiera SGD.

<table>
  <thead>
    <tr>
      <th>Uppgift 20</th>
      <th>Teckenbyte (Medel)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod som kan läsa in flera textrader från användaren och byta ut varje förekomst av tecknet "O" till tecknet "Ö" resp. "o" till "ö". Metoden ska läsa in en rad i taget varvid metoden sedan ska presentera raden med de teckenbyten som har skett för att sedan läsa in nästa rad. Denna process ska upprepas tills dess att användaren anger "EXIT". Exempel på interaktion med metoden kan tänkas se ut enligt följande:<br><br>
        <table>
  <thead>
    <tr>
      <th>Körexempel</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <pre lang="csharp" class="highlight">
Input: Mors lilla Olle i skogen gick.
Output: Mörs lilla Ölle i skögen gick.
Input: Om vädret är fint så kommer Ofelia på festen.
Output: Öm vädret är fint så kömmer Öfelia på festen.
Input: EXIT
        </pre>
          </td>
    </tr>
          </tbody>
        </table>
  </td>
    </tr>
  </tbody>
</table>

Uppgift 21 | RotateArrayBy2 (Medel/Svår)
----------|----------
Beskrivning | Skriv en metod, <code>RotateArrayBy2</code>, som tar emot en array av heltal och roterar elementen i en array med 2 positioner åt vänster. Dvs. att givet arrayen [3, 5, 10, 2, 6] så skulle följande array returneras: [10, 2, 6, 3, 5]. **OBS!** Skriv din implementation ___utan___ att deklarera en ny array.

<table>
  <thead>
    <tr>
      <th>Uppgift 22</th>
      <th>"String slicing" (Medel/Svår)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod som tar emot en sträng samt ett heltal (<code>n</code>) och returnerar alla angränsande delsträngar (<code>substrings</code>) av längden <code>n</code> i den ordning som de anges. Exempel på interaktion med metoden:<br>
        <table class="examples">
          <thead>
            <tr>
              <th>Körexempel</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <pre lang="csharp" class="highlight">
// Givet strängen "49142" och heltalet 3 så får vi följande delsträngar:
"491"
"914"
"142"

// Givet strängen "49142" och heltalet 3 så får vi följande delsträngar:
"4914"
"9142"
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
        <i>Notera</i> att längden på delsträngarna måste vara större än 1 och att de självfallet inte kan vara längre än själva strängen. <strong>TIPS!</strong> Nyttja de inbyggda sträng-metoderna <code>Concat</code> samt <code>Substring</code>.
      </td>
    </tr>
  </tbody>
</table>

Uppgift 23 | Decimal to binary (Medel/Svår)
----------|----------
Beskrivning | Skriv en metod, <code>DecToBin</code>, som översätter ett heltal enligt det decimala talsystemet till det binära talsystemet. Det decimala talsystemet är det som vi nyttjar till vardags med basen 10 (0-9). Det binära talsystemet nyttjar istället basen 2 där något antingen är av eller på (0 eller 1). Således får vi exempelvis <code>1010</code> om vi översätter <code>10</code>, <code>1100100</code> om vi översätter <code>100</code> osv. **NOTERA** att ju längre något är till vänster i ett binärt tal, desto större är det. I <code>1010</code> så har vi 8, 4, 2, 1 där 1:orna indikerar de värden som ska tillgodoräknas (i detta fall 8:an och 2:an för 10).<br><br> Om du vill läsa mer om hur man konverterar från det decimala talsystemet till det binära så kan du nyttja följande länk: [Dec to binary](https://www.wikihow.com/Convert-from-Decimal-to-Binary). Om du vill nyttja en redan existerande konverterare så kan du kika på följande länk: [Dec/Bin Converter](https://www.rapidtables.com/convert/number/decimal-to-binary.html).<br><br> **TIPS!** Nyttja iteration och modulus. Uppgiften __skall__ lösas utan den inbyggda metoden <code>Convert.ToString</code>.

Uppgift 24 | Tidsberäkning av tågresor (Medel/Svår)
----------|----------
Beskrivning | Ett persontågsföretag vill ha ett program (en metod i detta fall) för att underlätta tidsberäkningen av tågresor med syftet att upprätta en tidtabell. Metoden ska läsa in avgångsort, avstånd mellan avgångsorten och destinationen samt datum och klockslag för avgång. Därefter ska metoden räkna ut vilket datum och vilken tid tåget kommer till destinationen. Tågets genomsnittliga hastighet är 130 km/h. <br><br>**TIPS!** Nyttja SVT-triangeln för att beräkna tiden (givet hastigheten och avståndet). Datatypen <code>DateTime</code> kan nyttjas för att enklare behandla datum och klockslag, men det krävs då att man utforskar lite vad datatypen har att erbjuda på egen hand. Det är dock fullt möjligt att nyttja strängar istället. Följande länk kan nyttjas för att få en inblick i <code>DateTime</code>: [DateTime](https://www.dotnetperls.com/datetime)

<table>
  <thead>
    <tr>
      <th>Uppgift 25</th>
      <th>Textmarkering (Medel/Svår)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
        Skriv ett program som läser in en sträng med valfri text. Programmet ska därefter markera alla förekomster av tecknet “å” genom att skriva ut texten igen och på raden under skriva ett <code>*</code> för varje förekomst av tecknet (“å”). Exempelvis kan interaktion med programmet se ut enligt följande:<br>
        <table>
  <thead>
    <tr>
      <th>Körexempel</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <pre lang="csharp" class="highlight">
        Svenska äpplen och fem året runt-äpplen
                               * 
        </pre>
          </td>
    </tr>
          </tbody>
        </table>
b. Utöka programmet så att det även markerar “ä”. Skriv även här ut tecknet <code>*</code>.<br><br>c. Utöka programmet ytterligare så att det istället för att skriva <code>*</code> för “å” och “ä” skriver tecknet <code>*</code> för “å” och tecknet <code>%</code> för “ä”.
  </td>
    </tr>
  </tbody>
</table>

Uppgift 26 | Summera individuella siffror i ett heltal (Medel/Svår)
----------|----------
Beskrivning | Skriv en metod som summerar samtliga siffror i ett heltal och returnerar summan. Om metoden exempelvis tar emot heltalet <code>1234</code> så ska <code>10</code> returneras. Uppgiften ska lösas ___utan___ att konvertera heltalet till en sträng. <br><br>**TIPS!** Nyttja division och det decimala talsystemet för att "hoppa" en decimal i taget och summera dessa allt eftersom. Dvs. att vi från <code>1234</code> först plockar ut 4:an vilket lämnar oss med <code>123</code>, därefter plockar vi ut 3:an osv.

Uppgift 27 | IsInteger (Medel/Svår)
----------|----------
Beskrivning | Skriv en metod, <code>IsInteger</code> som tar emot en sträng och avgör om strängen representerar ett riktigt heltal. Metoden ska ignorera mellanslag men behöver kunna hantera <code>+</code>-tecken och <code>-</code>-tecken. <br><br>**TIPS!** Metoden <code>char.IsDigit</code> kan nyttjas för att avgöra om ett tecken representerar en siffra eller ej.

<table>
  <thead>
    <tr>
      <th>Uppgift 28</th>
      <th>Begynnelsebokstäver (Medel/Svår)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod som skriver ut alla begynnelsebokstäver i en mening. Med begynnelsebokstäver så avses det första bokstaven i resp. ord i en mening. Exempel på interaktion med metoden:<br>
        <table>
  <thead>
    <tr>
      <th>Körexempel</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <pre lang="csharp" class="highlight">
// Input
Datorerna Synes Vänliga och Programmen Slutar Vårdslöst.

// Output
D S V o P S V
        </pre>
          </td>
    </tr>
          </tbody>
        </table>
  </td>
    </tr>
  </tbody>
</table>

Uppgift 29 | En bättre sökalgoritm (Svår)
----------|----------
Beskrivning | I introduktionen till sektionen "Iteration/Arrayer" så beskrivs en enkel sökalgoritm för att identifiera ett heltal i en array av heltal. Denna typ av sökalgoritm är dock väldigt ineffektiv då vi ev. måste iterera igenom hela arrayen innan vi kan fastställa om heltalet förekommer eller ej. Denna uppgift går således ut på att skriva en mer effektiv sökalgoritm. Processen för denna sökalgoritm kan beskrivas enligt nedan:<br><br>1. Kontrollera om elementet förekommer i mitten av arrayen.<br>2. Om det inte förekommer i mitten, är heltalet vi söker efter större än eller mindre än heltalet i mitten?<br>Om det är mindre -> Upprepa sökningen, fast denna gång enbart från det första elementet till och med elementet till vänster om mittenvärdet. <br>Om det är större -> Upprepa sökningen, fast denna gång enbart från det elementet till höger om mittenvärdet till och med det sista elementet i arrayen.<br>3. Upprepa processen tills vi har identifierat heltalet eller tills dess att vi kan fastställa att det inte förekommer i arrayen. **OBS!** Metoden förutsätter att arrayen redan är placerad i storleksordning.<br><br>Skriv en metod, <code>AvSearch</code>, som tar emot en array av heltal samt ett heltal. Metoden ska därefter identifiera om heltalet förekommer i arrayen eller ej. **TIPS!** För att fastställa att talet inte förekommer i arrayen så är det fördelaktigt att ständigt uppdatera ramen som vi vill undersöka. Om vi t.ex. i första iterationen ser att talet tillhör den vänstra delen av arrayen så kan vi ändra vårt "max-värde" (inledningsvis det sista elementet i arrayen) till mittenvärdet -1. Därefter så fortsätter vi att iterera tills dess att vårt "min-värde" (inledningsvis det första elementet i arrayen) är större än eller lika med vårt "max-värde". , men du får självfallet nyttja en sorteringsalgoritm om du vill utöka metoden själv.

Uppgift 30 | RemoveDuplicates (Svår)
----------|----------
Beskrivning | Skriv en metod, <code>RemoveDuplicates</code>, som tar emot en array av heltal. Metoden ska sedan ta bort alla duplicerade värden i arrayen. Dvs. att givet exempelvis arrayen: [6, 6, 3, 3, 1, 9, 4] så ska en array med värdena [6, 3, 1, 9, 4] returneras.<br><br>Testa först att skriva en implementation som ersätter alla duplicerade värden med 0:or snarare än att ta bort elementet från arrayen (reducera dess storlek). När du har lyckats med en sådan implementation så kan du sedan ge dig på den mer avancerade versionen som även reducerar arrayens storlek. <br><br>**TIPS!** Du kan nyttja implementationen från Uppgift 24 (<code>IsDuplicate</code>) under sektionen "Iteration/Arrayer" samt en ytterligare stödmetod som reducerar storleken på arrayen genom att ta bort ett angivet heltal från arrayen. Tänk i detta fall då på att inte ta bort ***alla*** förekomster av heltalet (vi vill exempelvis behålla en utav 6:orna i ovan exempel).<br><br> **NOTERA** att datastrukturen <code>array</code> ska nyttjas, inte <code>ArrayList</code>, <code>List</code> eller liknande datastrukturer. Det kan ev. dock vara fördelaktigt att reflektera kring inbyggda metoder för dessa andra typer av datastrukturer såsom <code>Append</code>, <code>Add</code> och <code>Remove</code>.
