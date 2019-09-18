---
title: Selektion
icon: fa-th
order: 4
---
I förhållande till konceptet selektion så behöver vi reflektera kring olika "vägar" som ett program kan ta. Ett program behöver nämligen kunna utföra olika saker beroende på vilka beslut en användare tar, precis som i vårt vardagliga liv! Vi kan exempelvis välja att ta bussen till jobbet __ELLER__ ta cykeln. __OM__ vi tar bussen så kostar det en viss summa, men vi anländer ev. snabbare. __OM__ vi ___istället___ tar cykeln så kostar det inget, men det kan ev. ta lite längre tid och vara omständigare (t.ex. vid regn). Det finns självfallet även möjligheten att gå till jobbet om exempelvis ___både___ bussen är inställd och cykeln har fått punktering. Detta är mao. vad vi blir tvunga att välja __OM__ de andra alternativen inte är tillgängliga.

Föreställ dig exempelvis att du nyttjar en hemsida som kräver inloggning för att lämna kommentarer. För att skapa ett konto så krävs det att man är äldre än 12 år gammal och att man anger ett användarnamn samt lösenord. Ett exempel på en simplistisk lösning för detta problem skulle kunna tänkas vara:  

```csharp
string usr = "";
string pass = "";
int age = 0;

Console.WriteLine("Ange ditt användarnamn: ");
usr = Console.ReadLine();
Console.WriteLine("Ange ditt lösenord: ");
pass = Console.ReadLine();
Console.WriteLine("Ange din ålder: ");
int.TryParse(Console.ReadLine(), out age);

if(age < 12)
    Console.WriteLine("Du måste vara minst 12 år för att skapa ett användarkonto!");
else if(age == 0) // Om konverteringen inte lyckades, t.ex. om "Tjugofem" anges istället för "25".
    Console.WriteLine("Du måste ange din ålder!");
else if(usr == "" || pass == "") // '||' representerar den logiska operatorn OR
    Console.WriteLine("Du måste ange ett användarnamn och ett lösenord!");
else
    Console.WriteLine("Ditt konto har skapats!");
```

Detta representerar alltså ett fall där vi gör en sak __OM__ (<code>if</code>) ett - eller flera - kriterium är uppfyllt/uppfyllda, __I ANNAT FALL__ (<code>else if</code>) så kontrollerar vi annat fall. Om vi i slutändan inte kan välja någon av dessa vägar så når vi vårt sista alternativ där vi helt enkelt säger att vi  __ANNARS__ eller __I ALLA ANDRA FALL__ (<code>else</code>) väljer det alternativet. Detta är vad som kallas för selektion.

**NOTERA** att vi inte ___måste___ nyttja if/else parvis. Vi kan mao. ha en <code>if</code>-sats utan en medföljande <code>else</code>-sats. Vi säger då att vi utför detta __OM__ kravet är uppfyllt, om det inte är det så gör vi ingenting. 

## Uppgiftsförteckning ##

Uppgift 1 | Kontrollera input och grundläggande operatorer
----------|-------------------------------
Beskrivning | Skriv ett program (eller en metod) som kontrollerar att: <br><br> - Input inte är lika med talet 5 och att det är mindre än 10. <br> - Input är lika med en annan variabel, <code>intLika1</code>. Denna variabel kan du tilldela vilket arbiträrt värde du än vill. <br> - Input innehåller bokstaven 'h' eller siffran '3'. Annars ska programmet skriva ut "Not true". <br><br> **TIPS:** Operatorn för "lika med" är <code>==</code>. Notera att enbart ett tilldelningstecken (=) indikerar just tilldelning medan två i rad alltså genomför en jämförelse. "inte lika med" kombinerar operatorn för "inte" (!) och "lika med" för att bilda "!=". För att kontrollera om en sträng innehåller en bokstav så kan metoden <code>Contains</code> nyttjas i uppgiften. För att kontrollera flera uttryck samtidigt så kan operatörerna för AND (<code>&&</code>) och OR (<code>||</code>) nyttjas.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int.TryParse(Console.ReadLine(), out int input);
if(input != 5 && input < 10) { 
  // Code goes here. 
}

int intLika1 = 112;
if(input == intLika1) { 
  // Code goes here. 
}

string newInput = Console.ReadLine();
if(!newInput.Contains('h') || !newInput.Contains('3')) { 
  // Code goes here. 
}
else { 
  Console.WriteLine("Not True"); 
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 2 | Odd numbers?
----------|-------------------------------
Beskrivning | Skriv ett program som läser in två heltal och skriver ut huruvida det stämmer om båda är udda eller ej. <br><br> **TIPS:** För att kontrollera om en siffra är jämn eller udda så rekommenderar vi att man nyttjar operatorn modulus. Om det inte finns någon rest efter att talet i fråga har dividerats med 2 så vet vi att talet är jämnt och vice versa.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int.TryParse(Console.ReadLine(), out int input1);
int.TryParse(Console.ReadLine(), out int input2);

if(input1 % 2 != 0 && input2 % 2 != 0){
  Console.WriteLine("It's true!");
}
else{
  Console.WriteLine("It's not true!");
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 3</th>
      <th>Positivt eller negativt?</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv ett program som läser in ett heltal och skriver ut huruvida det är ett positivt heltal eller ett negativt heltal. Exempel på interaktion med programmet:<br>
        <table class="examples">
          <thead>
            <tr>
              <th>Körexempel</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <pre lang="csharp" class="code-example">
 // Om input är: -12
-12 är ett negativt tal.

 // Om input är: 3
3 är ett positivt tal.
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int.TryParse(Console.ReadLine(), out int input1);

if(input1 >= 0){
  Console.WriteLine(input1 + " är ett positivt tal.");
}
else{
  Console.WriteLine(input1 + " är ett negativt tal.");
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 4| Skottår
----------|-------------------------------
Beskrivning | Skriv ett program som läser in ett årtal och sedan skriver ut huruvida det årtalet är ett skottår eller ej. För att avgöra om ett år är ett skottår så ska programmet utgå från följande parametrar: <br><br> Om ett årtal är jämnt delbart med 4, 100 eller 400 så är det ett skottår. <br>Om årtalet som läses in är negativt så ska programmet skriva ut: "Du måste ange ett årtal efter år 0!".

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int.TryParse(Console.ReadLine(), out int year);

if(year < 1){
  Console.WriteLine("Du måste ange ett årtal efter år 0!");
}
else if(year % 400 == 0 || year % 100 == 0 || year % 4 == 0){
  Console.WriteLine(year + " är ett skottår!");
}
else{
  Console.WriteLine(year + " är INTE ett skottår!");
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 5</th>
      <th>Om m, skriv n</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv ett program som läser in ett heltal. Om heltalet är lika med 33 så ska heltalet + 9 skrivas ut, om heltalet är större än, eller lika med, 150 så ska heltalet delat i 2 skrivas ut. I alla andra fall ska heltalet upphöjt i 2 skrivas ut. Exempel på interaktion med programmet:<br>
        <table class="examples">
          <thead>
            <tr>
              <th>Körexempel</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <pre lang="csharp" class="code-example">
// Om input är: 33
42

// Om input är: 240
120

// Om input är: 149
22201
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int.TryParse(Console.ReadLine(), out int m);

if(m == 33){
  Console.WriteLine(m + 9);
}
else if(m >= 150){
  Console.WriteLine(m / 2);
}
else{
  Console.WriteLine(m * m);
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 6 | Går det att bada?
----------|-------------------------------
Beskrivning | Kajsa gillar att bada, dock tar vattnet ibland slut hemma och dessutom kan värmen variera ganska mycket. Denna metod undersöker om badet är redo. Kraven för att badet ska vara redo är att det måste finnas vatten, och att vattnet måste vara mellan 30 och 42 grader (inklusive). Programmet förväntas därför läsa in en parameter som avgör om badet har vatten eller ej. Detta kan anges i följande format: "true", "yes" eller "y". Programmet ska även läsa in en annan parameter som kan representera intervallet 30-48 grader.<br><br> **OBS!** Tänk på att om badkaret saknar vatten så kan vi inte kontrollera vattnets temperatur.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
Console.WriteLine("Ange om badkaret har vatten (true, yes eller y):");
string hasWater = Console.ReadLine();
bool b = false;
if(hasWater == "true" || hasWater == "yes" || hasWater == "y"){
  b = true;
  Console.WriteLine("Ange vattnets temperatur:");
  int.TryParse(Console.ReadLine(), out int temp);
  if(temp >= 30 && temp <= 42 && b){
    Console.WriteLine("Badet är redo.");
  }
  else{
    Console.WriteLine("Badet är INTE redo.");
  }
}
else{
  Console.WriteLine("Badkaret saknar vatten.");
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 7</th>
      <th>Är personen arbetsför?</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv ett program som läser in en persons ålder. Programmet ska sedan kategorisera arbetsföra personer efter deras ålderskategori och skriva ut vilken kategori som personen tillhör. Kategorierna är: <br>16-19: Tonåring <br> 20-29: Ung vuxen <br> 30-39: Vuxen <br> 40-49: Medelålder <br> 50-64: Äldre <br><br>Om personen är under 16 eller äldre än 64 så ska programmet skriva ut att personen inte tillhör arbetsför kategori. Exempel på interaktion med programmet:<br>
        <table class="examples">
          <thead>
            <tr>
              <th>Körexempel</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <pre lang="csharp" class="code-example">
Ange personens ålder: 35
Personens kategori är: Vuxen

Ange personens ålder: 15
Personen tillhör inte arbetsför kategori!
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
Console.Write("Ange personens ålder: ");
int.TryParse(Console.ReadLine(), out int age);

if(age < 16 || age > 64){
  Console.WriteLine("Personen tillhör inte arbetsför kategori!");
}
else{
  if(age > 15 && age < 20){
    Console.WriteLine("Personens kategori är: Tonåring");
  else if(age > 19 && age < 30){
    Console.WriteLine("Personens kategori är: Ung vuxen");
  else if(age > 29 && age < 40){
    Console.WriteLine("Personens kategori är: Vuxen");
  else if(age > 39 && age < 50){
    Console.WriteLine("Personens kategori är: Medelålder");
  else{
    Console.WriteLine("Personens kategori är: Äldre");
  }
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 8</th>
      <th>Vilket betyg får studenten?</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv ett program som kontrollerar om en student har nått betyget G eller VG på en tentamen. Programmet behöver först läsa in antalet skrivpoäng som studenten har i en variabel och sedan ska programmet jämföra dess värde mot betygsgränserna som anges enligt: <br><br> U: <60 <br> G: 60-84 <br> VG: 85-100 <br><br>Om studenten uppfyller kraven, dvs. antingen uppnår betyget G eller VG så ska programmet skriva ut "Studenten har avslutat kursen med betyget X!". Exempel på interaktion med programmet:<br>  
        <table class="examples">
          <thead>
            <tr>
              <th>Körexempel</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <pre lang="csharp" class="code-example">
Ange studentens skrivpoäng: 90
Ange studentens bonuspoäng: 0
Studenten har avslutat kursen med betyget VG!

Ange studentens skrivpoäng: 57
Ange studentens bonuspoäng: 6
Studenten har avslutat kursen med betyget G!
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
      <br><em>OBS!</em> Om något har gått tokigt till i systemet så behöver vi dock kunna avgöra detta. Ifall studentens skrivpoäng därför är negativa eller över 100 så ska programmet skriva ut "Något har gått fel vid inmatning.". <br><br> Vi behöver även kontrollera om studenten har fått bonuspoäng från andra moment på kursen och, om så är fallet, så behöver detta tas i beaktning vid bedömningen. Om en student exempelvis skriver 57 på tentamen men har sedan tidigare bonuspoäng som omfattar 6 poäng på tentamen så ska studenten ha betyget G.
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
Console.WriteLine("Ange studentens skrivpoäng: ");
int.TryParse(Console.ReadLine(), out int points);
Console.WriteLine("Ange studentens bonuspoäng: ");
int.TryParse(Console.ReadLine(), out int bonus);

if(points < 0 || points > 100){
  Console.WriteLine("Något har gått fel vid inmatning.");
}
else{
  if((points + bonus) < 60){
    Console.WriteLine("Studenten har inte nått minst betyget G på kursen");
  else if((points + bonus) >= 60 && (points + bonus) < 85){
    Console.WriteLine("Studenten har avslutat kursen med betyget G!");
  else{
    Console.WriteLine("Studenten har avslutat kursen med betyget VG!");
  }
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 9 | Introduktion till Switch
----------|-------------------------------
Beskrivning | Skriv ett program som tar emot ett heltal och skriver ut den veckodag som matchar det heltalet. Dvs. att om användaren skriver in '5' så ska 'Fredag' skrivas ut osv. <br>Om heltalet inte matchar en veckodag så ska istället följande skrivas ut: "Incorrect input".<br><br>**TIPS!** Nyttja en s.k. switch-sats för att lösa uppgiften. För att läsa mer om dessa och se exempel på hur de kan nyttjas så kan du nyttja följande länk: [Information om switch-satser](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/switch)

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
string input = Console.ReadLine();

switch(input){
  case "1":
      Console.WriteLine("Måndag");
      break;
  case "2":
      Console.WriteLine("Tisdag");
      break;
  case "3":
      Console.WriteLine("Onsdag");
      break;
  case "4":
      Console.WriteLine("Torsdag");
      break;
  case "5":
      Console.WriteLine("Fredag");
      break;
  case "6":
      Console.WriteLine("Lördag");
      break;
  case "7":
      Console.WriteLine("Söndag");
      break;
  default:
      Console.WriteLine("Incorrect input");
      break;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 10 | Väder för veckan
----------|-------------------------------
Beskrivning | Skriv ett program som skriver ut vädret för en angiven dag den nuvarande veckan. Vädret beror så klart på veckodag och gäller måndag till söndag enligt följande: <br>Mån: Soligt och >25C" <br>Tis: "Molnigt och runt 22C" <br>Ons: "Regn och <16C" <br>Tor: "Sol och regn, >20C" <br>Fre: "Orimligt varmt, runt 30C" <br>Lör: "Orimligt varmt, runt 32C" <br>Sön: "Regn och vind, <18C". <br><br>Veckodagen skall anges enligt följande format, med måndag som ett exempel: <code>"MONDAY"/"Monday"/"monday"/"mon"/"1"</code>. <br>Om det angivna formatet inte nyttjas så ska "Incorrect input" skrivas ut.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
string day = Console.ReadLine();

switch(day){
  case "MONDAY": case "Monday": case "monday": case "mon": case "1":
      Console.WriteLine("Soligt och >25C");
      break;
  case "TUESDAY": case "Tuesday": case "tuesday": case "tue": case "2":
      Console.WriteLine("Molnigt och runt 22C");
      break;
  case "WEDNESDAY": case "Wednesday": case "wednesday": case "wed": case "3":
      Console.WriteLine("Regn och <16C");
      break;
  case "THURSDAY": case "Thursday": case "thursday": case "thu": case "4":
      Console.WriteLine("Sol och regn, >20C");
      break;
 // Notera att det inte spelar någon roll om du skriver resp. "case" efter varandra enligt ovan eller på nästkommande rad som här.
  case "FRIDAY": 
  case "Friday":
  case "friday":
  case "fri":
  case "5":
      Console.WriteLine("Orimligt varmt, runt 30C");
      break;
  case "SATURDAY":
  case "Saturday":
  case "saturday":
  case "sat":
  case "6":
      Console.WriteLine("Orimligt varmt, runt 32C");
      break;
  case "SUNDAY":
  case "Sunday":
  case "sunday":
  case "sun":
  case "7":
      Console.WriteLine("Regn och vind, <18C");
      break;
  default:
      Console.WriteLine("Incorrect input");
      break;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 11 | Vinst eller förlust?
----------|-------------------------------
Beskrivning | Skriv ett program som avgör om en person har gått med vinst eller förlust på en försäljning givet ett inköpspris och ett försäljningspris. Utgå exempelvis från följande scenario: <br><br>Karl köper andelar i en viss fond för 2300 kr runt löning med syfte att spara pengar. Han inser dock efter två veckors tid att han behöver pengarna pga. ett antal kostsamma utekvällar. Han säljer därför av sina andelar. Tyvärr så har fonden inte utvecklats väl under denna period och han säljer därför av andelarna för 1900 kr. Karl har därför gått med förlust på 400 kr (-17.3913043478261%). Du behöver ___inte___ avrunda procentsatsen. Om inköpet har resulterat i varken en vinst eller förlust så ska detta förmedlas via konsolen. <br><br>**TIPS:** Tänk på att du behöver nyttja datatypen <code>double</code> för att räkna med decimaler (vilket blir nödvändigt vid procentberäkning).

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int.TryParse(Console.ReadLine(), out int buyPrice);
int.TryParse(Console.ReadLine(), out int sellPrice);
double percent = 0;

if (sellPrice < buyPrice)
{
    double diff = buyPrice - sellPrice;
    percent = diff / (double)buyPrice;
    Console.WriteLine("The loss is: " + diff + " (-" + percent * 100 + "%)");
}
else if(sellPrice > buyPrice)
{
    double diff = sellPrice - buyPrice;
    percent = diff / (double)buyPrice;
    Console.WriteLine("The profit is: " + diff + " (" + percent * 100 + "%)");
}
else
{
    Console.WriteLine("You've made neither a profit or a loss.");
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 12 | Typ av triangel?
----------|-------------------------------
Beskrivning | Skriv ett program som tar emot längden från alla tre sidor hos en triangel och avgör om triangeln är likbent, liksidig eller oliksidig.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int a, b, c;

Console.Write("Skriv in längden för sida a:");
int.TryParse(Console.ReadLine(), out a);
Console.Write("Skriv in längden för sida b:");
int.TryParse(Console.ReadLine(), out b);
Console.Write("Skriv in längden för sida c:");
int.TryParse(Console.ReadLine(), out c);
Console.WriteLine(); // En extra blankrad

if(a == b && a == c){
  Console.WriteLine("Triangeln är en liksidig triangel.");
}
else if(a == b || a == c){
  Console.WriteLine("Triangeln är en likbent triangel.");
}
else{
  Console.WriteLine("Triangeln är en oliksidig triangel.");
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 13 | En enkel meny
----------|-------------------------------
Beskrivning | Skriv ett program som presenterar användaren till en enklare meny med tre alternativ. Dessa alternativ ska vara:<br> - Beräkna arean hos en cirkel.<br> - Beräkna arean hos en rektangel. <br> - Avsluta programmet utan beräkning. <br><br>Notera att du behöver olika parametrar för de olika fallen. Exempelvis behöver du radien för att beräkna arean hos en cirkel men höjd och bredd för att istället beräkna arean hos en rektangel.<br><br>**TIPS!** För att nyttja PI i <code>C#</code> så kan du nyttja egenskapen <code>Math.PI</code>, men det går så klart även bra att enbart nyttja <code>3.14</code> istället.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int input, r, b, h, area;

Console.WriteLine("Välj ett av följande alternativ:");
Console.WriteLine("1: Beräkna arean hos en cirkel.");
Console.WriteLine("2: Beräkna arean hos en rektangel.");
Console.WriteLine("3: Avsluta applikationen.");

int.TryParse(Console.ReadLine(), out input);
switch(day){
  case 1:
      Console.Write("Skriv in radien hos cirkeln: ");
      int.TryParse(Console.ReadLine(), out r);
      Console.WriteLine("Arean hos rektangeln är: " + Math.PI*r*r);
      break;
  case 2:
      Console.Write("Skriv in höjden hos rektangeln: ");
      int.TryParse(Console.ReadLine(), out h);
      Console.Write("Skriv in bredden hos rektangeln: ");
      int.TryParse(Console.ReadLine(), out b);
      Console.WriteLine("Arean hos rektangeln är: " + b*h);
      break;
  case 3:
      Console.WriteLine("Applikationen avslutas.");
      break;
  default:
      Console.WriteLine("Din input är felaktig. Försök igen.");
      break;
}
```
</details>

{::options parse_block_html="false" /}
