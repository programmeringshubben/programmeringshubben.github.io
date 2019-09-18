---
title: Datatyper
icon: fa-th
order: 3
---
Gällande grundläggande datatyper så behöver vi först och främst förstå att det finns olika typer av data. Vi har exempelvis datatypen <code>int</code> som kan nyttjas för att lagra numeriska värden, datatypen <code>string</code> för att lagra text och <code>char</code> för att lagra individuella bokstäver och tecken.

I denna sektion så kommer du att arbeta med dessa grundläggande datatyper, hur man interagerar med konsolen (input/output) samt konvertering av datatyper. För att göra detta så behöver man dock ha viss koll på de olika koncepten. Således följer en kortfattad beskrivning av resp. koncept nedan.

Datatyper:
```cs
// Grundläggande datatyper
bool b; // Hanterar värden av typen true eller false
int x; // Hanterar numeriska värden, t.ex. 123
char c; // Hanterar tecken, t.ex. '1' eller 'A'
DateTime date; // Hanterar datum och tid, t.ex. DateTime.Today

// Notera att det även finns en annan datatyp - decimal - för decimaltal.
double dd; // Hanterar decimaltal, t.ex. 12.3
string s; // Ord och meningar, t.ex. "Hello world"
```

Input/output:
```cs
// Input
// Läser det som användaren skriver in i konsolen.
// OBS! Alltid av typen string.
string input = Console.ReadLine();

// Output
// Skriver ut det som skrivs inom parenteserna i konsolen.
Console.WriteLine("Hello");

// .Write skriver ut innehållet på samma rad medan WriteLine bryter raden.
Console.Write("Hel");
Console.Write("lo");
```

Konvertering:
```cs
string input = Console.ReadLine();

// Fungerar enbart om input KAN konverteras till ett heltal.
// T.ex. kan "hej" inte konverteras till ett heltal.
int x = Convert.ToInt32(input);

// Fungerar alltid utan felmeddelande.
// Ger en felkod, 0, om konvertering misslyckas.
int y; 
int.TryParse(input, out y);
```

## Uppgiftsförteckning ##

Uppgift 1 | Att deklarera vs. att tilldela
----------|-----------------------------------
Beskrivning | Deklarera en variabel av resp. datatyp (<code>int</code>, <code>string</code>, <code>char</code>, <code>bool</code>) och tilldela sedan resp. variabel genom att tilldela dem ett värde.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
// Deklarering av variablerna. Vi skapar dem och ger dem ett namn men inget värde.
int x;
string s;
char c;
bool b;

// Tilldelning av variablerna. Vi ger dem ett värde.
x = 10;
s = "Hello world!";
c = 'H';
b = true;
```

</details>
{::options parse_block_html="false" /}

Uppgift 2 | Hello, Name!
----------|-------------------------------
Beskrivning | Skriv ett program som visar ditt namn och en fullständig adress (såsom du skulle se den på ett brev). Programmet ___ska___ läsa in input från användaren.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
Console.WriteLine("Enter your name: ");
string name = Console.ReadLine();
Console.WriteLine("Enter your address: ");
string address = Console.ReadLine();

Console.WriteLine("Hello, " + name + "!");
Console.WriteLine("Your full adress is: " + address);
```

</details>
{::options parse_block_html="false" /}

Uppgift 3 | Modifiering av datatyper - Konvertering
----------|-------------------------------
Beskrivning | Skriv ett program som läser in en siffra från en användare och sedan konverterar värdet till ett heltal. <br><br> TIPS! Tänk på att ALLT som läses in med <code>Console.ReadLine()</code> är av datatypen <code>string</code>. För att ändra detta till ett heltal så behöver man konvertera värdet. Detta kan ske på olika sätt, men försök dig på följande: <code>Convert.ToInt32()</code> samt <code>int.TryParse()</code>. Om du är intresserad av att läsa mer kring hur dessa metoder särskiljer sig så kan du kika på följande länk: [Parse vs ConvertToInt32 vs TryParse](http://www.dotnetstudy.com/int-parse-vs-convert-toint32-vs-int-tryparse?id=32)

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
   
```cs
string input = Console.ReadLine();
int x = Convert.ToInt32(input); // Detta fungerar enbart om värdet KAN transformeras till ett heltal. Om användaren t.ex. skriver in "Hej" så kommer applikationen att krascha.
Console.WriteLine(x);

int y;
int.TryParse(input, out y); // Metoden kommer att försöka omvandla värdet. Om det inte går så kommer y att innehålla värdet 0.
Console.WriteLine(y);
```

</details>

{::options parse_block_html="false" /}

Uppgift 4 | Konvertering med olika datatyper
----------|-------------------------------
Beskrivning | I Uppgift 3 så behandlas hur man konverterar från en <code>string</code> till en <code>int</code> men det finns såklart flera olika metoder beroende på vilka datatyper som nyttjas. Testa på att konvertera enligt nedan: <br> Från <code>int</code> till <code>string</code> <br> Från <code>double</code> till <code>int</code> <br> Från <code>double</code> till <code>string</code>

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
   
```cs
// Från int till string
int.TryParse(input, out int y);
string s = y.ToString();

// Från float till int
float x = 10.55f;
int a = Convert.ToInt32(x); // a = 11

// Från double till string
double z = 10.5;
string ss = z.ToString();

// Från float till string
float f = 42.31f;
string sss = f.ToString();
```

</details>

{::options parse_block_html="false" /}

Uppgift 5 | Olika typer av konvertering
----------|-------------------------------
Beskrivning | Man kan även konvertera på olika sätt. Det finns exempelvis s.k. explicit konvertering och implicit konvertering samt konvertering utan att anropa <code>Convert-klassen</code> (dvs. exempelvis <code>Convert.ToInt32</code>). <br><br> Explicit konvertering är det har nyttjats i tidigare uppgifter. Dvs. exempelvis genom metoder såsom <code>Convert.ToInt32</code> eller <code>int.TryParse</code>. Vi säger helt enkelt tydligt att vi vill genomföra konvertering. <br> Implicit konvertering tillåter oss att exempelvis gå från en <code>int</code> till en <code>double</code> utan att ange det då båda datatyper är av numerisk karaktär. <br><br> Det är även möjligt att genomföra explicit konvertering utan att ange en metod för konverteringen. Detta uppnås genom att placera datatypen som variabeln ska konverteras till - inom parenteser - framför variabeln. Testa på dessa olika typer av konvertering och ifall du är intresserad av att läsa mer om det så kan följande länk nyttjas: [Olika typer av konvertering C#](https://code-maze.com/csharp-basics-type-conversion/)

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
   
```cs
// Explicit
int.TryParse(input, out int y);
string s = y.ToString();

// Implicit
int a = 15;
int b = 3;
double kvot = a / b;

// Explicit med parenteser. Notera att detta inte fungerar i alla fall, t.ex. är det inte möjligt att byta ut double mot en string.
int x = 10;
double d = (double)x;
```

</details>

{::options parse_block_html="false" /}

Uppgift 6 | Summera två heltal
----------|-------------------------------
Beskrivning | Skriv ett program som läser in två heltal från en användare. Programmet ska sedan summera heltalen och skriva ut den resulterande summan. <br><br>**OBS!** Programmet ska inte krascha pga. felaktig inmatning (t.ex. om användaren anger en bokstav istället för en ett heltal).

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
 
```cs
int.TryParse(Console.ReadLine(), out int first);
int.TryParse(Console.ReadLine(), out int second);
int sum = first + second;
Console.WriteLine(sum);
```

</details>

{::options parse_block_html="false" /}

Uppgift 7 | Division av heltal
----------|-------------------------------
Beskrivning | Skriv ett program som läser in två heltal och sedan beräknar samt skriver ut kvoten. Utöka sedan programmet så att det även läser in två decimaltal och sedan beräknar samt skriver ut kvoten för divisionen mellan dessa tal.<br><br> **Notera** skillnaden som uppstår mellan de två beräkningarna då det är viktigt att vara medveten om denna diskrepans vid exempelvis beräkningar av procent.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
   
```cs
// Division med int
int.TryParse(input, out int x);
int.TryParse(input, out int y);
Console.WriteLine(x / y); // Ger 3 om x är 10 och y är 3. Ger 2 om x är 8 och y är 3.

// Division med double
double.TryParse(input, out int a);
double.TryParse(input, out int b);
Console.WriteLine(a / b); // Ger t.ex. 3.33 om x är 10 och y är 3. Ger 2.66 om x är 8 och y är 3.

// Division med int som ger en double
double kvot = x / y; // Ger 3 om x är 10 och y är 3
double korrektKvot = (double)x / (double)y; // Ger 3.33 om x är 10 och y är 3. Konvertering måste ske INNAN beräkning.
```

</details>

{::options parse_block_html="false" /}

Uppgift 8 | Grundläggande matematik
----------|-------------------------------
Beskrivning | Skriv ett program som läser in två heltal från användaren och som sedan skriver ut differensen mellan talen (subtraktion), produkten mellan talen (multiplikation) och kvoten mellan talen (division).

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>

```cs
int.TryParse(Console.ReadLine(), out int first);
int.TryParse(Console.ReadLine(), out int second);
int sub = first - second;
Console.WriteLine(sub);

int multi = first * second;
Console.WriteLine(multi);

double div = (double)first / (double)second;
Console.WriteLine(div);
```

</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 9</th>
      <th>Byta plats på värden</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
        Skriv ett program som byter värdet hos två variabler av datatypen heltal och skriver ut variablernas nya värden. Exempel på interaktion med programmet: <br>
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
// Innan byte:
First input contains: 3
Second input contains: 11 

// Efter byte:
First input contains: 11
Second input contains: 3
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
int.TryParse(Console.ReadLine(), out int first);
int.TryParse(Console.ReadLine(), out int second);
int temp = first;
first = second;
second = temp;
Console.WriteLine("First input contains: " + first);
Console.WriteLine("Second input contains: " + second);
```

</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 10</th>
      <th>Korrekt beräkning</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv ett program som tar emot tre heltal (x, y & z) och sedan utför beräkningar enligt följande: (x + y) * z resp. x * y + y * z. Programmet ska sedan skriva ut resultatet för resp. beräkning. Exempel på interaktion med programmet: <br>
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
// Input
// x = 3 
// y = 11 
// z = 2 

First calculation: 28
Second calculation: 55 
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
int.TryParse(Console.ReadLine(), out int x);
int.TryParse(Console.ReadLine(), out int y);
int.TryParse(Console.ReadLine(), out int z);
int sum1 = (x+y) * z;
int sum2 = x * y + y * z;
Console.WriteLine("First calculation: " + sum1);
Console.WriteLine("Second calculation: " + sum2);
```

</details>

{::options parse_block_html="false" /}

Uppgift 11 | Beräkna hastighet
----------|-------------------------------
Beskrivning | Skriv ett program som läser in avstånd och tid som input och sedan räknar ut hastighet i km/h. <br><br> **TIPS!** Använd datatypen float. Formeln som nyttjas för att beräkna hastighet (given tid och avstånd) är <code> v = s / t </code> där <code>s</code> är avstånd och <code>t</code> är antalet timmar.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
float.TryParse(Console.ReadLine(), out float distance);
float.TryParse(Console.ReadLine(), out float time);

float speed = distance / time;
```

</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 12</th>
      <th>Strängkonkatenering</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv ett program som läser in ett förnamn och ett efternamn. Konkatenera namnen genom att sätta ihop efternamnet med förnamnet. Tänk på att det utskrivna måste vara läsbart för datoranvändaren. <br><br> <strong>TIPS!</strong> För att konkatenera ("sätta ihop") strängar så kan man nyttja operatorn för addition (+) mellan de strängar man vill konkatenera. Exempel på interaktion med programmet: <br>
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
// Input för förnamn: Anon
// Input för efternamn: Nym 
Name: Nym, Anon. 
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
string fName = Console.ReadLine();
string lName = Console.ReadLine();

Console.WriteLine("Name: " + lName + ", " + fName + ".");
```

</details>

{::options parse_block_html="false" /}

<table>
  <thead>
    <tr>
      <th>Uppgift 13</th>
      <th>Modulus</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beskrivning</td>
      <td>
Skriv ett program som läser in ett heltal och dividerar det med 2. Programmet ska sedan skriva ut "resten" (det som blev över efter divisionen). **TIPS:** Operatorn för Modulus är <code>%</code>. Anledningen till varför vi får 1 i ovan exempel beror på att 2 går i 5 två gånger (2+2=4) vilket lämnar oss med "resten" som är en 1:a. Exempel på interaktion med programmet: <br>
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
Ange ett heltal: 5 
Resten efter division är: 1 
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
Console.Write("Ange ett heltal: ");
int.TryParse(Console.ReadLine(), out int input);
double d = input % 2;
Console.WriteLine("Resten efter division är: " + d);
```
</details>

{::options parse_block_html="false" /}
