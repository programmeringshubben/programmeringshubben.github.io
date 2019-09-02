---
title: Inledning
icon: fa-th
order: 2
---

För att lösa uppgifterna som du ser på denna sida så behöver du först skapa en konsol-applikation i Visual Studio för språket C#. Var uppmärksam när du skapar detta projekt så att du väljer **C#** och inte **Visual Basic** (som är ett annat programmeringsspråk). När du gör detta så kommer du att bemötas av koden som du ser nedan:
```cs
using System;

namespace PracticeAssignments // Namnet beror på vad du har döpt ditt projekt till.
{
  class Program
  {
    static void Main(string[] args)
    {
      // Write to console
      Console.WriteLine("Hello World!");
      Console.WriteLine("Press the Enter key to exit.");

      // Keep the terminal open until the user presses Enter.
      Console.ReadLine();
    }
  }
}
```
Det är inom *metoden* <code>Main</code> som du kommer att skriva din kod, till en början. Om vi kör koden från ovan exempel så kommer vi t.ex. att skriva ut "Hello World!" i konsolen. Konsolen kommer därefter att vänta på att du, eller användaren, klickar på Enter-tangenten innan applikationen stängs ned. Vi nyttjar alltså <code>Console.WriteLine()</code> för att skriva ut information i konsolen och <code>Console.ReadLine()</code> för att läsa in information från användaren.

För nästan varje uppgift på denna sida så förväntas det att du nyttjar dessa verktyg för att lösa uppgiften så lägg dem på minnet!

### Föreslagen struktur ###
Då det snabbt kan bli omständigt att skapa en ny konsolapplikation för resp. uppgift så rekommenderar vi till en början att du, till en början, enbart arbetar i <code>Main</code>-metoden och separerar varje uppgift med hjälp av kommentarer. Dvs. exempelvis enligt nedan:
```cs
public class Program
{
  static void Main(string[] args)
  {
      // Uppgift 1 - Att deklarera vs. att instansiera
      int x;
      ...
      // Uppgift 2 - Hello, Name!
      Console.WriteLine("Enter your name: ");
      ...
  }
}
```
Där "..." representerar den kod du skriver för att lösa uppgiften.

Ett annat alternativ, något du förväntas nyttja senare oavsett fallet, är att strukturera ditt program med hjälp av metoder. Tanken här är att du skapar en ny, egendefinierad metod för resp. uppgift som du sedan _anropar_ från <code>Main</code>-metoden. Mer information kring just metoder finner du under sektionen "Metoder" ([Hoppa hit!](https://noitaloiv.github.io/test/#metoder)). För att nyttja metoder så skriver man först en ny metod _utanför_ <code>Main</code>-metoden som i nedan exempel:
```cs
public class Program
{
  static void Main(string[] args)
  {

  }
  // HÄR, efter den avslutande '}'
  // "static void" är något du måste lägga till framför metodnamnet, annars kan vi inte anropa metoden från Main
  // Hur en s.k. "metodsignatur" ser ut beskrivs ytterligare under sektionen "Metoder".
  static void Uppgift1()
  {
      int x;
      ...
  }
  
  static void Uppgift2()
  {
      Console.WriteLine("Enter your name: ");
      ...
  }
}
```

När du sedan är klar med din implementation, eller om du vill testa den, så behöver du _anropa_ den metod som du har skrivit från <code>Main</code>-metoden. Exempel på hur man gör detta ser vi nedan:
```cs
public class Program
{
  static void Main(string[] args)
  {
      // Metodanrop för att köra Uppgift1
      Uppgift1();
      
      // Metodanrop för att köra Uppgift2
      Uppgift2();
      
      // Osv.
  }

  static void Uppgift1()
  {
      int x;
      ...
  }
  
  static void Uppgift2()
  {
      Console.WriteLine("Enter your name: ");
      ...
  }
}
```
