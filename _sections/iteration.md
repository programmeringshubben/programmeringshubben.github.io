---
title: Iteration/Arrayer
icon: fa-th
order: 5
---

Datatypen array är oftast något svår att förstå sig på inledningsvis. Exempelvis så kan man inte manipulera storleken (t.ex. lägga till en plats eller ta bort en plats i listan) på en array då dessa är statiska. Vi måste dessutom alltid ha i åtanke att, åtminstone för C#, indexpositionerna i en array alltid startar från position 0. Dvs. att när vi då exempelvis itererar över en array så måste man <br>1) börja på 0 (om vi inte vill hoppa över det första elementet) och <br>2) vara försiktig så att vi inte pekar på en indexposition som inte finns. <br>Se nedan exempel:
```cs
int[] arr = new int[] { 2, 4, 6, 8, 10, 12, 14, 16, 18, 20 };

int x = arr[0]; // x = 2;
x = arr[9]; // x = 20;
x = arr[10]; // IndexOutOfRangeException då vi pekar på en position som inte existerar.
```

Iteration är ett koncept som tillåter oss att återupprepa ett stycke kod tills dess att vi når ett angivet resultat. En vanlig tillämpning av detta är nyttjandet av loopar såsom <code>for-loopar</code>, <code>while-loopar</code> och <code>foreach-loopar</code>. Föreställ dig exempelvis att vi vill söka efter ett angivet heltal i en array av heltal. Utan iteration så skulle vi behöva manuellt gå igenom varje element i arrayen och kontrollera dess värde med hjälp av <code>if-satser</code>. Genom att istället tillämpa iteration så kan vi säga åt vårt program att gå igenom hela arrayen åt oss och vi behöver bara skriva en <code>if-sats</code> istället för 10 (om arrayen från föregående kodexempel skulle nyttjas). Dvs. i stil med:
```cs
int search = 12; // Elementet vi letar efter i arrayen.
int[] arr = new int[] { 2, 4, 6, 8, 10, 12, 14, 16, 18, 20 };

for(int i = 0; i < arr.Length; i++){
  if(arr[i] == search){
    Console.WriteLine("Elementet hittades på plats:" + i);
  }
}
```
**OBS!** I ovan kodexempel så är det värt att lägga märke till följande aspekter:

+ Syntaxen för en <code>for-loop</code>. 
  + Vi skapar först en <code>int</code> som representerar indexpositionen i arrayen och tilldelar den värdet 0 (för att starta på den första positionen i arrayen). 
  + Vi säger därefter att loopen ska fortsätta köras __tills dess att__ <code>i</code> inte längre är mindre än 10 (<code>i < arr.Length</code>). 
  + Därefter så exekveras koden i loopen så att vi under den första iterationen får <code>arr[0] == search</code>. Då detta inte stämmer så hoppar vi upp till <code>i++</code> som kommer att öka värdet på <code>i</code> så att vi under nästa iteration istället får <code>arr[1] == search</code> osv.
+ Egenskapen <code>Length</code> hos arrayer som tillåter oss att hämta längden hos en array. I ovan fall så skulle vi därför få 10.

## Uppgiftsförteckning ##

Uppgift 1 | De första 100 positiva heltalen
----------|-------------------------------
Beskrivning | Skriv en metod, <code>PrintNumbers</code>, som skriver ut alla positiva heltal från 1 till och med 50.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void PrintNumbers(){
  for(int i = 1; i <= 50; i++){
    Console.WriteLine(i);
  }
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 2</th>
      <th>Strukturerad utskrift</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>PrintNumbersTwo</code>, som skriver ut alla positiva heltal från 1 till och med 50. Metoden ska skriva ut heltalen i intervaller av 10. Exempel på interaktion med metoden: <br>
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
1, 2, 3, ..., 10    // ... = 4-9
11, 12, 13, ..., 20 // osv.
...
41, 42, 43, ..., 50
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
void PrintNumbersTwo(){
  for (int i = 1; i <= 50; i++)
  {
      if(i == 10)
      {
        Console.Write(i);
        Console.WriteLine();
      }
      else if (i == 20)
      {
        Console.Write(i);
        Console.WriteLine();
      }
      else if (i == 30)
      {
        Console.Write(i);
        Console.WriteLine();
      }
      else if (i == 40)
      {
        Console.Write(i);
        Console.WriteLine();
      }
      else if (i == 50)
      {
        Console.Write(i);
        Console.WriteLine();
      }                   
      else
        Console.Write(i + ", ");
  }
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 3</th>
      <th>Strukturerad utskrift II</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
        Skriv en metod, <code>NestedPrint</code>, som skriver ut följande mönster: <br>
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
        *
        **
        ***
        ****
        *****
        </pre>
          </td>
    </tr>
          </tbody>
        </table>       
<strong>TIPS!</strong> För att lösa denna uppgift så rekommenderas det att du nyttjar nästlade loopar, dvs. en loop inuti en annan. Ha i åtanke att all kod i den inre loopen kommer att köras <em>för varje</em> iteration i den yttre loopen. Nyttja gärna debugging i Visual Studio för att felsöka om något blir tokigt eller helt enkelt för att följa med i koden.
  </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void NestedPrint(){
  for(int i = 1; i <= 5; i++)
  {
    for(int j = 1; j <= i; j++)
    {  
      Console.Write("*");
    }
    // Används för att "gå till nästa rad", dvs. en break-line.
    Console.Write("\n"); // Går även att byta ut mot Console.WriteLine();
  }
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 4</th>
      <th>Strukturerad utskrift III</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>NestedPrintTwo</code>, som skriver ut följande mönster:<br>
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
    *
   * * 
  * * *
 * * * *
* * * * *
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
static void NestedPrintTwo()
{
    int count = 1;
    for (int i = 5; i >= 1; i--)
    {
        for (int j = i - 1; j >= 1; j--)
            Console.Write(" ");
        for (int k = 1; k <= count; k++)
        {
            Console.Write("*");
            Console.Write(" ");
        }
        count++;
        Console.WriteLine();
    }
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 5</th>
      <th>Strukturerad utskrift IV</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>NestedPrintThree</code>, som tar emot ett heltal som användaren anger. Metoden ska sedan iterera så pass många gånger som heltalet representerar och, för varje iteration, skriva ut enligt följande mönster:<br>
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
// Givet heltalet 7 som input:
1
22
333
4444
55555
666666
7777777

// Givet heltalet 3 som input:
1
22
333
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
void NestedPrintThree(int iterations){
  for(int i = 1; i <= iterations; i++)
  {
    for(int j = 1; j <= i; j++)
    {  
      Console.Write(i);
    }
    Console.WriteLine();
  }
}
```
</details>

{::options parse_block_html="false" /}


<table>
  <thead>
    <tr>
      <th>Uppgift 6</th>
      <th>Strukturerad utskrift V</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>NestedPrintFour</code>, som tar emot ett heltal som användaren anger och skriver ut följande mönster:<br>
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
// OBS! Du behöver inte inkl. mellanslag mellan symbolerna!
// Givet heltalet 2 som input:
        *
      * * *
 
// Givet heltalet 5 som input:
        *
      * * *
    * * * * *
  * * * * * * *
* * * * * * * * *
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
<strong>Notera</strong> att enbart udda antal <code>*</code> skrivs ut per rad. Antalet rader som skrivs ut bestäms av det heltal som tas emot som argument.
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void NestedPrintFour(int iterations){
   for(int i = 0; i < iterations; i++)
   {
      for(int j = 1; j <= iterations-i; j++)
        Console.Write(" ");
      for(int k = 1; k <= 2 * i-1; k++)
        Console.Write("*");
     Console.WriteLine();
   }
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 7 | Summan av alla heltal mellan 1-100
----------|-------------------------------
Beskrivning | Skriv en metod, <code>GaussianSum</code>, som skriver ut summan av alla positiva heltal från 1 till och med 100. <br><br>**OBS!** Resultatet av beräkningen är 5050, men detta ska beräknas i metoden. Du ska mao. inte hårdkoda resultatet och skriva ut det.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void GaussianSum(){
  int sum = 0;
  for (int i = 1; i <= 100; i++)
  {
    sum += i;
  }
  Console.WriteLine(sum);
}

// alt. lösning
void GaussianSum(){
  Console.WriteLine(100(100+1)/2));
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 8</th>
      <th>Beräkna medelvärdet</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>Average</code>, som beräknar medelvärdet av heltal som anges av användaren. Metoden ska fortsätta ta emot heltal tills dess att användaren anger <code>-1</code>. När detta sker så beräknas medelvärdet vilket metoden sedan skriver ut <strong>och</strong> returnerar. Exempel på interaktion med metoden: <br>
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
Ange ett heltal: 50
Ange ett heltal: 11
Ange ett heltal: 116
Ange ett heltal: -1
Medelvärdet är: 59
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
int Average()
{
    int sum, count, input;
    sum = count = input = 0;

    while (input != -1)
    {
        Console.Write("Ange ett heltal: ");
        int.TryParse(Console.ReadLine(), out input);
        if (input == -1)
            break;
        sum += input;
        if (input != 0)
            count++;
    }

    if(count == 0)
    {
        Console.WriteLine("Beräkning kan ej genomföras");
        return 0;
    }
    else
    {
        Console.WriteLine("Medelvärdet är: " + (sum / count));
        return sum / count;
    }
    return 0;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 9 | Fakultet (matematik)
----------|----------
Beskrivning | Skriv en metod, <code>CalculateFactorial</code>, som tar emot ett heltal som argument och skriver ut fakulteten hos det talet. <br><br> **OBS!** För att beräkna fakulteten hos ett tal så beräknar man produkten hos alla heltal - från och med 1 - till och med heltalet i fråga. Dvs. att om vi exempelvis vill beräkna fakulteten för heltalet 5 så skulle det se ut enligt: !5 = 1 * 2 * 3 * 4 * 5 vilket ger oss 120. __Notera__ att heltalet i fråga måste vara större än 0, annars kan ingen beräkning ske.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void CalculateFactorial(int input){
  if(input > 0){
    for (int i = input - 1; i >= 1; i--)
    {
       input *= i;
    }
    Console.WriteLine("Fakulteten är: " + input);
  }
  else
    Console.WriteLine("Heltalet måste vara större än 0!");
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 10</th>
      <th>Rekursiv metod (Fakultet II)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
En rekursiv metod är en metod som anropar sig själv tills dess att ett s.k. "basfall" uppnås. Denna typ av metod är mer vanligt förekommande i funktionella språk, men det är fullt möjligt att nyttja dem även i <code>C#</code>. Fördelarna med denna typ av metoder är att de resulterar i mindre kod och oftast är mer resurseffektiva (dvs. snabbare). Nackdelarna är det kan vara svårt att förstå sig på processen samt att det är betydligt svårare att felsöka dem i jämförelse med vanlig iteration. Ett exempel på rekursion skulle vara följande: <br>
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
string Rec(int n) {
  if (n <= 0)   // Kontrollera att heltalet är ett positivt tal.
      return n + " must be higher than -1";
  else if (n > 9)
  {
      Console.Write(n);
      return "Completed"; // När vi har nått 10 så vill vi avsluta
  }
  else
  {
      Console.Write(n + ", ");
      return Rec(n + 1); // Rekursivt anrop. 1 + 1 -> 2 + 1 osv.
  }
}
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
Där metoden <code>Rec</code> räknar från det heltal som skrivs in till och med 10 och skriver ut följden i konsolen.<br><br> Uppgiften är att försöka lösa Uppgift 9 (Fakultet) på nytt fast genom att nyttja rekursion istället.<br><br><strong>OBS!</strong> Denna uppgift är svår och faller egentligen något utanför kursens ramar (dvs. att innehållet är överkurs). Tanken med uppgiften är att introducera begreppet rekursion samt tillhandahålla möjligheten att testa på det.
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void CalculateFactorial(int input){
  if(input == 0)
    return 1;
  else
    return input * CalculateFactorial(input - 1);
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 11 | Primtal?
----------|----------
Beskrivning | Skriv en metod, <code>IsPrime</code>, som tar emot ett heltal och avgör om heltalet är ett primtal eller ej. <br><br> Ett primtal är ett heltal som är större än 1 och som enbart är jämnt delbart med 1 eller sig självt. <br><br> Exempelvis så är 2, 3 och 5 primtal medan 4 och 6 inte är det då de även är jämnt delbara med 2. <br><br> **TIPS!** Nyttja modulus och iteration för att kontrollera om det finns fler än två (<code>1 resp. talet självt</code>) faktorer. Tänk på att jämna tal, utöver <code>2</code>, inte kan vara primtal.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
bool IsPrime(int input){
  // De första fallen kan hanteras via selektion.
  if (input == 1) return false;
  if (input == 2) return true;

  for (int i = 2; i * i <= input; i++)
  {
      if (input % i == 0)
          return false;                
  }
  // Om talet har passerat loopen så är det ett primtal.
  return true;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 12 | Alla primtal upp till...
----------|----------
Beskrivning | Skriv en metod, <code>PrimeNumbers</code>, som tar emot ett heltal och skriver ut samtliga primtal från 1 upp till och med det heltalet. <br><br> **TIPS!** Nyttja din implementation från Uppgift 11 för att lösa uppgiften.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void PrimeNumbers(int input){
  // De första fallen kan hanteras via selektion.
  if (input < 2)
    Console.WriteLine("Ange ett heltal större än 1.");
  else
  {
    for (int i = 1; i <= input; i++)
    {
      if(IsPrime(i))
        Console.WriteLine(i + " is a prime.");
    }
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 13 | Fibonacci
----------|----------
Beskrivning | Skriv en metod, <code>Fibonacci</code>, som tar emot ett heltal och skriver ut tal i Fibonnaci-sekvensen. Antalet tal som skrivs ut avgörs av det angivna heltalet. <br><br> Ett Fibonnaci-tal är summan av de två föregående talen i en sekvens av heltal. Exempelvis är de första 5 Fibonnaci-talen: 0 1 1 2 3. Vi kan i denna talföljd identifiera det tidigare nämnda mönstret givet <code>0 + 1 = 1</code>, <code>1 + 1 = 2</code>, <code>1 + 2 = 3</code> osv.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void Fibonacci(int input)
{
    int n1, n2 = 1, n3;
    n1 = n3 = 0;

    Console.WriteLine(n1);
    Console.WriteLine(n2);

    for (int i = 2; i < input; i++)
    {
        n3 = n1 + n2;
        Console.WriteLine(n3);
        n1 = n2;
        n2 = n3;
    }
}

Alt. lösning:
void Fibb(int input)
{
    int i = 0;
    for (int n1 = 0, n2 = 1, n3 = 0; i < input; n3 = n1 + n2, n1 = n2, n2 = n3, i++)
    {
        Console.WriteLine(n1);
    }
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 14</th>
      <th>Multiplikationstabellen för X</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>CalculateMultTable</code>, som tar emot ett heltal som argument och returnerar en array av heltal. Metoden ska beräkna multiplikationstabellen (från 1 till och med 10) för heltalet och bygga upp en array innehållandes denna multiplikationstabell. Ett exempel på interaktion med metoden är: <br>
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
int[] arr = CalculateMultTable(3);
// arr innehåller: [3, 6, 9, 12, 15, 18, 21, 24, 27, 30].
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
int[] CalculateMultTable(int input){
  int[] arr = new int[10];
  
  for(int i = 1; i <= arr.Length; i++){
    arr[i-1] = input * i;
  }
  
  return arr;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 15 | Utskrift av arrayer
----------|-------------------------------
Beskrivning | Skriv en metod, <code>PrettyPrint</code>, som tar emot en array av heltal som argument och inte returnerar någonting. Problemet med Uppgift 1 är att vi inte kan skriva ut innehållet i den array som skickas tillbaka i nuläget. Om vi exempelvis nyttjar <code>Console.WriteLine(CalculateMultTable(3));</code> så kommer vi enbart att skriva ut dess datatyp snarare än innehållet i arrayen. För att skriva ut innehållet så behöver man istället peka på vilket element man specifikt vill skriva ut och det är detta <code>PrettyPrint</code> är ämnad att utföra. <br><br>Metoden ska skriva ut en array enligt följande format: 5, 10, 15, 20, 25, 30, 35, 40, 45, 50<br><br>**NOTERA** att det alltså inte ska förekomma ett kommatecken efter det sista värdet. Metoden ska även kunna skriva ut innehållet i en array av heltal oavsett dess storlek.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void PrettyPrint(int[] input){  
  for(int i = 0; i < input.Length; i++){
    if(i == input.Length-1)
      Console.Write(input[i]);
    else
      Console.Write(input[i] + ", ");
  }
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 16 | Utskrift av arrayer (baklänges)
----------|-------------------------------
Beskrivning | Skriv en metod, <code>PrettyPrintReversed</code>, som tar emot en array av heltal som argument och skriver ut innehållet i arrayen baklänges. <br><br>Baklänges innefattar att om arrayen innehåller värdena [1, 3, 9] så ska utskriften vara [9, 3, 1]. <br> Metoden ska skriva ut en array enligt följande format: 5, 10, 15, 20, 25, 30, 35, 40, 45, 50<br><br>**NOTERA** att det alltså inte ska förekomma ett kommatecken efter det sista värdet. Metoden ska även kunna skriva ut innehållet i en array av heltal oavsett dess storlek.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void PrettyPrintReversed(int[] input){  
  for(int i = input.Legnth-1; i >= 0; i--){
    if(i == 0)
      Console.Write(input[i]);
    else
      Console.Write(input[i] + ", ");
  }
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 17 | Största värdet i en array
----------|-------------------------------
Beskrivning | Skriv en metod, <code>HighestNumber</code>, som tar emot en array av positiva heltal som argument och returnerar det största värdet i arrayen.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int HighestNumber(int[] input){
  int max = 0;
  for(int i = 0; i < input.Length; i++){
    if(input[i] > max)
      max = input[i];
  }
  return max;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 18 | Näst största värdet i en array
----------|-------------------------------
Beskrivning | Skriv en metod, <code>SecondHighestNumber</code>, som tar emot en array av heltal som argument och returnerar det näst största värdet i arrayen. <br><br> **TIPS!** Reflektera kring hur implementationen i Uppgift 17 kan anpassas för att hämta det näst största värdet istället för det största.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int SecondHighestNumber(int[] input)
{
    int max = input[0], nMax = 0;
    for (int i = 1; i < input.Length; i++)
    {
        if (input[i] > max)
        {
            nMax = max;
            max = input[i];
        }
        else if (input[i] > nMax && input[i] != max)
            nMax = input[i];
    }
    return nMax;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 19 | Medelvärdet i en array
----------|-------------------------------
Beskrivning | Skriv en metod, <code>AverageNumber</code>, som tar emot en array av heltal som argument och returnerar medelvärdet av alla värden i arrayen.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int AverageNumber(int[] input){
  int sum = 0;
  for(int i = 0; i < input.Length; i++){
    sum += input[i];
  }
  return sum / (input.Length-1);
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 20</th>
      <th>Summering av arrayer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>SumArrays</code>, som tar emot två arrayer av heltal som argument (<code>arrayA och arrayB</code>) och returnerar en array - <code>arrayC</code> - som innehåller summan av talen på resp. position.  Ett exempel på interaktion med metoden är: <br> 
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
int[] arrC = SumArrays(new int[] {5, 3, 4}, new int[] {13, 1, 10});
// arrC innehåller: [18, 4, 14]
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
<strong>OBS!</strong> Metoden kan utgå från att arrayerna alltid är av samma längd.
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int[] SumArrays(int[] arrayA, int[] arrayB){
  int[] arrayC = new int[arrayA.Length];
  
  for(int i = 0; i < arrayA.Length; i++){
    arrayC[i] = arrayA[i] + arrayB[i];
  }
  return arrayC;
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 21</th>
      <th>Count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>Count</code>, som tar emot en array av heltal och ett heltal som argument och returnerar antalet gånger det heltalet förekommer i arrayen. Ett exempel på interaktion med metoden är: <br> 
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
int c = Count(new int[] {6, 3, 3}, 3);
// c = 2;

c = Count(new int[] {6, 4, 1}, 2);
// c = 0;
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
<strong>OBS!</strong> Metoden kan utgå från att arrayerna alltid är av samma längd.
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int Count(int[] arr, int n){
  int count = 0;
  for(int i = 0; i < arr.Length; i++){
    if(arr[i] == n)
      count++;
  }
  return count;
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 22</th>
      <th>PrintUniques</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>PrintUniques</code>, som tar emot en array av heltal som argument och skriver ut alla unika värden i arrayen. Om arrayen <i>inte</i> innehåller några unika värden så ska <code>"There are no unique values in the array."</code> skrivas ut. Ett exempel på interaktion med metoden är: <br> 
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
PrintUniques(new int[] {6, 3, 3});
// Utskrift
6

PrintUniques(new int[] {6, 4, 1});
// Utskrift
6
4
1
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
<strong>TIPS!</strong> Nyttja din implementation av metoden <code>Count</code> från Uppgift 21.
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void PrintUniques(int[] arr)
{
    int count = 0;
    for (int i = 0; i < arr.Length; i++)
    {
        if (Count(arr, arr[i]) < 2)
        {
            Console.WriteLine(arr[i] + " is a unique value.");
            count++;
        }                   
    }

    if (count == 0)
        Console.WriteLine("There are no unique values in the array.");
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 23</th>
      <th>Sort array</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>SimpleSort</code>, som tar emot en array av heltal som argument och sorterar dem enligt storleksordning. Ett exempel på interaktion med metoden är: <br> 
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
int[] arr = SimpleSort(new int[] {6, 3, 1, 8, 4, 3});
// arr innehåller: [1, 3, 3, 4, 6, 8]
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
<strong>TIPS!</strong> Nyttja nästlade loopar för att lösa uppgiften.
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void SimpleSort(int[] arr)
{
    int temp = 0;
    for (int i = 0; i < arr.Length; i++)
    {
        for(int j = i; j < arr.Length; j++)
        {
            if(arr[i] > arr[j])
            {
              temp = arr[j];
              arr[j] = arr[i];
              arr[i] = temp;
            }
        }
    }
}
```
</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 24</th>
      <th>IsDuplicate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv en metod, <code>IsDuplicate</code>, som tar emot en array av heltal som argument samt ett heltal och avgör om heltalet förekommer fler än en gång i arrayen. Ett exempel på interaktion med metoden är: <br> 
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
bool dupe = IsDuplicate(new int[] {6, 3, 1, 8, 4, 3}, 3);
// dupe = true

dupe = IsDuplicate(new int[] {6, 3, 1, 8, 4, 3}, 1);
// dupe = false
                </pre>
              </td>
            </tr>
          </tbody>
        </table>
<strong>TIPS!</strong> Denna implementation kommer att påminnna om implementationen av <code>Count</code> (Uppgift 21).
      </td>
    </tr>
  </tbody>
</table>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
bool IsDuplicate(int[] arr, int n)
{
    int count = 0;
    for (int i = 0; i < arr.Length; i++)
    {
        if (arr[i] == n)
            count++;
    }

    if (count > 1)
        return true;

    return false;
}
```
</details>

{::options parse_block_html="false" /}
