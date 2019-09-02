---
title: Starta Visual Studio
icon: fa-th
order: 1
---
Det första steget blir ju såklart att starta en instans av programmet. Förutsatt att du sitter i en utav laborationssalarna så uppnås detta enklast genom att klicka på Windows-tangenten (till höger om vänster CTRL-tangent) och därefter söka efter Visual Studio genom att börja skriva "v-i-s-u…" osv. Visual Studio 20XX kommer då att dyka upp i högerkolumnen och du behöver då enbart klicka på ikonen för att skapa en instans av programmet. Det kommer mao. efterlikna bilden nedan.

<img src="{{ '/Images/image11.png' | relative_url }}" alt="Visual Studio i laborationssal" class="image centered"/>

Det är "Visual Studio" du vill öppna (**OBS!** _Visual Studio 2017_ förekommer inte i ovan bild men är att föredra över _Visual Studio 2013_), inte någon utav de andra applikationerna. Den första gången du startar Visual Studio så kommer du möjligtvis att bemötas av en pop-up som ber dig logga in. Detta behöver du *INTE* göra, utan klicka istället på "Not now". Du behöver även välja ett tema. Detta har ingen som helst inverkan på din kod och kan även ändras i efterhand. Därefter kan det ta ett par minuter innan programmet startar och du ser Visual Studios "startsida".

<h3>Att skapa projekt i Visual Studio</h3>
När du väl har startat Visual Studio (VS) så behöver du välja ett projekt. I VS så kan man däremot skapa flera olika typer av projekt såsom konsol-applikationer, Windows Forms-applikationer och Webbaserade tjänster. För resp. projekttyp så autogenereras viss kod åt dig som utvecklare och denna kod ser betydligt annorlunda ut beroende på vilket projekt du vill arbeta i. Det är således viktigt att man väljer korrekt projekttyp. I denna kurs kommer ni enbart att använda er utav en s.k. konsol-applikation.

<h3> Konsolapplikationer </h3>
För att skapa ett nytt projekt så finns det två tillvägagångssätt: Du kan antingen göra detta genom att klicka på "New Project" på startsidan i Visual Studio eller genom att navigera från fliken "File" -> "New" -> "Project". I bilden nedan så ser du att det finns flera olika typer av projekt. Det är här viktigt att du kontrollerar vilken projekttyp som är markerad. I bilden så ser du exempelvis i vänsterspalten att "Visual C#" är markerat (vilket vi vill ha) men att det även finns projekt för andra språk såsom <code>Basic</code>, <code>F#</code> och <code>C++</code> . Dvs. att det bör se mer eller mindre se likadant ut för dig när du skapar ett eget projekt.

<img src="{{ '/Images/image13.png' | relative_url }}" alt="En C# konsolapplikation" class="image centered"/>

Notera att du, om du arbetar i laborationsmiljön, först och främst behöver ändra på "Location". "Location" representerar den mapp där du kommer att spara ditt projekt. Anledningen bakom detta är att hårddisk C: har begränsat med utrymme på laborationsdatorerna vilket ev. kan resultera i att ditt arbete försvinner. För att undvika detta så bör du istället välja att spara dina projekt på hårddisk U:. Vi rekommenderar att här att du först skapar två mappar så att du alltid enkelt kan hitta tillbaka till dina projektfiler, t.ex. "Visual Studio" som i sin tur innehåller en mapp vid namn "Projects". I Visual Studio så ändrar du därefter "Location" till mappen "Projects".

**OBS!** Tänk även på att namnge ditt projekt något rimligt. Exempelvis "GP_Inlamnning1" eller "GP_ChatClient", beroende på vilken uppgift och kurs du håller på med etc. Detta underlättar för dig att särskilja projekt från olika kurser.

När du väl har valt platsen där projektet ska sparas, ett projektnamn och klickat på "OK" så möts du därefter av en klass kallad "Program" vilken innehåller en metod, "Main". Det bör efterlikna nedan kodexempel (minus kommentarerna). 
```csharp
namespace GP_ChatClient // Namnet beror på vad du har döpt ditt projekt till.
{
  class Program
  {
    static void Main(string[] args)
    {
      // Här placerar du din kod.
    }
  }
}
```
Det är <code>Main</code>-metoden som kommer att exekveras när du startar din applikation och det är därför här du, till en början, kommer att vilja placera majoriteten av din kod. Detta innefattar bl.a. funktionaliteten involverad i att läsa användarinput och skriva ut saker. Du kommer under kursens gång att övergå till att placera funktionalitet i s.k. metoder vilka du sedan kommer att anropa från <code>Main</code>-metoden.
