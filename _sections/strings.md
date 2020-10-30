---
title: Strängar
icon: fa-th
order: 6
---

En sträng är egentligen en array utav tecken (<code>char</code>). Detta innebär att vi kan behandla en sträng likt hur vi behandlar en array. Föreställ dig exempelvis att vi har en sträng i stil med: 
```cs
string hello = "Hello World!";
```
och att vi är intresserade av att hämta det tecken som förekommer på just indexposition 4. Vi kan uppnå detta genom att skriva <code>hello[4]</code> (som då är 'o'). <br><br> Vi skulle även kunna iterera över en sträng, likt hur vi skulle göra för en array som består av heltal. Exempelvis enligt:
```cs
string text = "Hello everybody!";
char c = '';
for (int i = 0; i < text.Length; i++)
{
    c = text[i]; // nyttjar indexering. 'c' kommer första iterationen att innehålla 'H' sedan 'e' osv.
}
```
Datatypen <code>string</code> innehåller även många olika inbyggda metoder som gör det möjligt att enkelt hantera och manipulera strängar på olika sätt. Några exempel på några vanligt förekommande metoder är <code>IndexOf</code>, <code>Substring</code>, <code>Split</code>, <code>ToUpper</code> och <code>ToLower</code>.

<code>IndexOf</code> kan nyttjas för att returnera indexpositionen hos en specifik <code>char</code> i en sträng men även för att kontrollera om en sträng förekommer inuti en annan sträng. Om en sådan förekomst inte påträffas (dvs. om strängen inte finns i den andra strängen) så returneras -1, vilket kan nyttjas som en typ av kod vid felhantering. Exempel på nyttjande av metoden:
```cs
string text = "Hello world, it is I!";
string searchText = "world";
int startIndex = text.IndexOf(searchText); // startIndex = 6
int startIndex2 = text.IndexOf('e'); // startIndex2 = 1
string searchText2 = "test";
int startIndex3 = text.IndexOf(searchText2); // startIndex3 = -1
```

<code>Substring</code> kan nyttjas för att returnera en del utav en sträng. Vilken del som ska returneras samt och storleken på denna del är beror på vilka argument som anges. Exempelvis kan vi ange att vi vill ha allt från en angiven startposition <code>string s = exempel.Substring(3);</code> men vi kan även ange ytterligare ett argument som avser hur långt vi vill gå från startpositionen (dvs. längden på delsträngen) <code>string s = exempel.Substring(3, 7);</code>. **OBS!** Även blanksteg räknas som ett tecken i en sträng. Exempel på nyttjande av metoden:
```cs
string text = "Hello world, it is I!";
string subString = text.Substring(6); // subString = "world, it is I!"
string subString2 = text.Substring(6, 5); // subString = "world"
```

<code>Split</code> kan nyttjas för att returnera en array av strängar från en sträng som separerats på ett (eller flera) angivet/angivna tecken. Som namnet antyder innefattar metoden att vi "splittar" (delar upp) en sträng. Exempel på nyttjande av metoden:
```cs
string fruits = "Apples, Oranges, Pears";

// Vi anger att vi vill dela upp strängen vid ','.
// Resultatet blir en array som innehåller 3 st. strängar.
string[] listOfFruits = fruits.Split(','); // listOfFruits = ["Apples", "Oranges", "Pears"]
```
För att undvika tomma strängar så har vi även möjligheten att nyttja något som kallas för <code>StringSplitOptions</code>:
```cs
string fruits = "Apples, Oranges, Pears";

// Vi anger att vi vill dela upp strängen vid ',' och ' '.
// Resultatet blir en array som innehåller 3 st. strängar.
string[] listOfFruits = fruits.Split(new char[] { ',', ' ' }, StringSplitOptions.RemoveEmptyEntries);
```
**Notera** att utan <code>StringSplitOptions</code> så skulle vi få en array med 5 element då mellanslag förekommer framför "Oranges" resp. "Pears" i strängen.

<code>ToLower</code> och <code>ToUpper</code> är metoder som kan nyttjas för att helt enkelt transformera en sträng så att den antingen enbart innehåller gemener eller versaler. Detta kan vara särskilt smidigt i fall som exempelvis då vi vill jämföra två strängar eller kontrollera dess innehåll. Exempel på nyttjande av metoderna:
```cs
string input1 = "HelLO wOrlD";
string toLower = input1.ToLower(); // "hello world"

string input2 = "HelLO wOrlD";
string toUpper = input2.ToUpper(); // "HELLO WORLD"
```

I denna sektion så förväntas du öva på dessa olika former av strängmanipulering.

## Uppgiftsförteckning ##

Uppgift 1 | StringLength
----------|-------------------------------
Beskrivning | Skriv en metod, <code>StringLength</code>, som tar emot en sträng som argument och beräknar längden på strängen (antalet tecken). Då en <code>string</code> kan, som tidigare nämnt, tolkas som en array av bokstäver så kan man självfallet nyttja egenskapen <code>Length</code> precis som vi har gjort i tidigare uppgifter men detta är inte syftet sett till uppgiften. Metoden <code>StringLength</code> ska dock beräkna längden via iteration istället.<br><br>**TIPS!** Nyttja en <code>foreach</code>-loop för att iterera över strängen.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int StringLength (string input){
  int length = 0;
  foreach(char c in input)
  {
      length++;
  }
  return length;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 2 | Reverse string
----------|-------------------------------
Beskrivning | Skriv en metod, <code>StringReversed</code>, som tar emot en sträng som argument och skriver ut strängen i bakvänd ordning. Dvs. givet strängen <code>"Hello world!"</code> så ska <code>"!dlrow olleH"</code> skrivas ut.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void StringReversed (string input){
  for(int i = input.Length-1; i >=0; i--)
  {
      Console.Write(input[i]);
  }
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 3 | RemoveSpaces
----------|-------------------------------
Beskrivning | Skriv en metod, <code>RemoveSpaces</code>, som tar emot en sträng som argument och skriver ut den efter att alla mellanslag har tagits bort från strängen. Om inga mellanslag förekommer i strängen så ska "No spaces in string." skrivas ut istället. <br><br>**TIPS!** Nyttja den inbyggda metoden <code>Split</code>.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void RemoveSpaces (string input){
  string[] noSpaces = input.Split(' ');
  if(noSpaces.Length < 2)
      Console.WriteLine("No spaces in string.");
  else
  {  
      string output = string.Empty;
    
      for(int i = 0; i < noSpaces.Length; i++)
      {
          output += noSpaces[i];
      }
      
      Console.WriteLine(output);
}

// Alt. lösning
void RemoveSpaces (string input){
    string output = string.Empty;
    int count = 0;

    for(int i = 0; i < input.Length; i++)
    {
        if(input[i] != " ")
            output += input[i];
        else
            count++;
    }

    if(count > 0)
        Console.WriteLine("No spaces in string.");
    else
        Console.WriteLine(output);
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 4 | RemoveSpecificChar
----------|-------------------------------
Beskrivning | Skriv en metod, <code>RemoveSpecificChar</code>, som tar emot ett tecken samt en sträng som argument och returnerar strängen efter att alla tecken som matchar argumentet har tagits bort.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
string RemoveSpecificChar (string input, char c){
    string output = string.Empty;

    for(int i = 0; i < input.Length; i++)
    {
        if(input[i] != c)
            output += input[i];
    }

    return output;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 5 | Sammanställning av sträng
----------|-------------------------------
Beskrivning | Skriv en metod, <code>GetStringContent</code>, som tar emot en sträng som argument och skriver ut alla bokstäver, siffror och specialtecken som förekommer i strängen. Dvs. givet meningen "Hello world! 123" så ska följande skrivas ut: <br><br>Bokstäver: 10 <br> Siffror: 3 <br> Specialtecken: 1. <br><br>Notera att mellanslag inte tillhör någon kategori och därför inte ska tillgodoräknas. **TIPS!** Det finns en inbyggd metod för datatypen <code>char</code> som kan avgöra om ett tecken är en siffra samt en annan som kan avgöra om ett tecken är en bokstav. 

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
void GetStringContent(string input)
{
    int digits, letters, symbols;
    digits = letters = symbols = 0;

    for (int i = 0; i < input.Length; i++)
    {
        // För att hantera mellanslag
        if (input[i] == ' ') { }

        else if (char.IsDigit(input[i]))
            digits++;
        else if (char.IsLetter(input[i]))
            letters++;
        else
            symbols++;
    }

    Console.WriteLine("Bokstäver: " + letters);
    Console.WriteLine("Siffror: " + digits);
    Console.WriteLine("Specialtecken: " + symbols);
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 6 | Manuell Substring
----------|-------------------------------
Beskrivning | Skriv en metod, <code>SubString</code>, som tar emot en sträng samt ett heltal som argument och returnerar en delsträng från och med det angivna heltalet där heltalet representerar en indexposition. <br><br> Skriv sedan en annan metod, <code>SubString</code> som tar emot en sträng samt två heltal som argument och returnerar en delsträng mellan indexpositionen som det första heltalet avser och indexpositionen som det andra heltalet avser. <br><br> **OBS!** Metoderna har samma namn men inte samma metodsignatur (två argument gentemot tre). Vi kommer att behandla detta ytterligare i senare kurser, men notera gärna detta. <br> Denna uppgift är tänkt att öka förståelsen för hur <code>Substring</code> fungerar genom att skriva en egen implementation av metoden. Uppgiften ska därför inte lösas mha. den inbyggda metoden <code>Substring</code>.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
string SubString(string input, int start)
{
    string substring = string.Empty;
    
    // Felhantering för att undvika IndexOutOfRange
    if(input.Length <= start || start < 1)
        return substring;
    
    for (int i = start; i < input.Length; i++)
    {
        substring += input[i];
    }

    return substring;
}

string SubString(string input, int start, int stop)
{
    string substring = string.Empty;
    
    // Felhantering för att undvika IndexOutOfRange
    if(input.Length <= start || start < 1 || input.Length <= stop)
        return substring;
    
    for (int i = start; i <= stop; i++)
    {
        substring += input[i];
    }

    return substring;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 7 | Manuell IndexOf
----------|-------------------------------
Beskrivning | Skriv en metod, <code>IndexOfChar</code>, som tar emot en sträng, ett tecken samt ett heltal - som avser startposition för sökningen - och skickar tillbaka indexpositionen som tecknet förekommer på i strängen. Om tecknet inte förekommer i strängen så ska -1 returneras. <br><br> **OBS!** Denna uppgift är tänkt att öka förståelsen för hur <code>IndexOf</code> fungerar genom att skriva en egen implementation av metoden. Uppgiften ska därför inte lösas mha. den inbyggda metoden <code>IndexOf</code>.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
int IndexOfChar(string input, char c, int pos)
{
    for(int i = pos; i < input.Length; i++)
    {
        if(input[i] == c)
            return i;
    }

    return -1;
}
```
</details>

{::options parse_block_html="false" /}

Uppgift 8 | IsStringInString
----------|-------------------------------
Beskrivning | Skriv en metod, <code>IsStringInString</code>, som tar emot två strängar som argument och avgör om den andra strängen förekommer i den första strängen. **TIPS!** Nyttja den inbyggda metoden <code>Substring</code> eller din implementation från Uppgift 6 för att jämföra den andra strängen mot den första strängen. Nyttja den inbyggda metoden <code>IndexOf</code> eller din implementation från Uppgift 7 för att hämta positionen i den första strängen där delsträngen (den andra strängen) börjar.

---

{::options parse_block_html="true" /}

<details><summary markdown="span">Lösningsförslag</summary>
  
```cs
bool IsStringInString(string input, string substring)
{
    // Positionen i input för den första bokstaven i substring
    int index = input.IndexOf(substring[0]);
    // variabel som tillåter oss att gå vidare till nästa "IndexOf"-värde
    int pos = 0;

    // Iteration för att om substring[0] t.ex. är 'a' så förekommer det sannolikt flera gånger i strängen.
    // -1 är felkoden för om tecknet inte hittas i strängen.
    while(index != -1)
    {
        // Felhantering så att vi inte får IndexOutOfRange.
        // Vi plockar ut en delsträng från input, med samma längd som "substring" och jämför dem mot varandra.
        if (index + substring.Length < input.Length && input.Substring(index, substring.Length) == substring)
            return true;
        
        // Uppdatera från vilken indexposition vi vill titta på.
        // Om vi inte gör detta så kommer vi att kolla på t.ex. position 10 för evigt.
        pos = index + 1;
        index = input.IndexOf(substring[0], pos);        
        // Alt. Uppgift 7 implementation
        // index = IndexOfChar(input, substring[0], pos);
    }

    return false;
}
```
</details>

{::options parse_block_html="false" /}
