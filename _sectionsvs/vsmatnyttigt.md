---
title: Matnyttigt i Visual Studio
icon: fa-th
order: 3
---
Visual Studio (VS) erbjuder oerhört mycket funktionalitet, olika typer av fönster, möjligheten att testa sin kod i realtid och mycket mer. En nackdel med detta är dock att du med största sannolikhet aldrig kommer att behöva stora delar av det som erbjuds. Således behandlar denna sektion olika aspekter av VS som du sannolikt kommer att stöta på eller åtminstone kan dra nytta utav.

<h3>Solution Explorer</h3>
Solution Explorer är ett fönster i Visual Studio (VS) där du kan se det projekt som du för närvarande arbetar i och samtliga filer som detta projekt innehåller. Fönstret är generellt placerat till höger i VS och, även fast det kanske inte är högst aktuellt under denna kurs, så kommer det att nyttjas flitigt under framtida kurser på programmet.

I Solution Explorer kan du bl.a. lägga till en ny fil, t.ex. en ny klassfil, textfil eller dylikt. Du gör detta genom att högerklicka på ditt projekt -> Navigera till Add -> Därefter till "New Item". Bilden nedan visar hur du navigerar dit.

<img src="{{ '/Images/image6.png' | relative_url }}" alt="'Add item' genom Solution Explorer" class="image centered"/>

Alternativt så kan du välja "Existing Item". Detta är relevant om du t.ex. vill lägga till en redan existerande fil, t.ex. en klass från ett annat projekt.

På samma sätt så är det möjligt att exkludera och inkludera filer samt att ta bort dem permanent. Detta uppnås genom att t.ex. högerklicka på filen och välja "Exclude From Project" (se bilden nedan). "Exclude" innefattar att du exkluderar filen från det nuvarande projektet i VS, men du tar inte bort filen. "Include" är motsatsen till "Exclude" och "Delete" innebär, som namnet antyder, att du tar bort filen
permanent.

<img src="{{ '/Images/image9.png' | relative_url }}" alt="'Exclude From Project' och 'Delete'" class="image centered"/>

Som du även ser i bilden ovan så har du möjligheten att ändra namn på filer här. Fördelen med att ändra namnet i denna meny är att du samtidigt erbjuds möjligheten att ändra referenserna i projektet för denna fil till det nya namnet. Detta blir mer aktuellt under framtida programmeringskurser.

<h3>"Debugging" och felsökning</h3>
> _90% of coding is debugging. The other 10% is writing bugs._
> - Bram Cohen


> _If debugging is the process of removing bugs, then programming must be the process of putting them in._
> - Edsger W. Dijkstra

Tyvärr så finns det en grad av sanning i ovan påståenden vilket innefattar att debugging och felsökning är något av det viktigaste att snabbt lära sig och ta till sig som en programmerare. Fördelen med att nyttja Visual Studio som utvecklingsmiljö är att den förenklar denna process markant. Du har exempelvis möjligheten att "följa med" i din kod samtidigt som den exekveras, Visual Studio säger ifrån om du försöker exekvera ett program som innehåller fel och du ges även - förhållandevis - tydlig information om vad som har gått fel.

För att "följa med" i koden så uppnår man detta genom att placera en s.k. "breakpoint" i vänsterspalten (den röda pricken i bilden nedan).

<img src="{{ '/Images/image12.png' | relative_url }}" alt="En 'Breakpoint' i Visual Studio" class="image centered"/>

Notera att en breakpoint enbart kan placeras på samma rad där det förekommer kod. För att ta bort en breakpoint så räcker det med att du klickar på den igen. För att ta bort alla breakpoints i hela projektet samtidigt kan du, istället för att manuellt klicka på resp. breakpoint, navigera till Debug-fliken -> "Delete All Breakpoints". Alternativt så kan du nyttja kortkommandot CTRL + SHIFT + F9.

När du sedan exekverar ditt program genom att klicka på Start (eller F5) så kommer programmet att stanna upp vid din placerade breakpoint. Från denna punkt har du då möjligheten att gå igenom din kod, steg-för-steg. Detta gör du smidigast med tangenterna F10 samt
F11. Under tiden som du "stegar igenom" din kod så kan du även exempelvis kontrollera innehållet i en variabel genom att placera muspekaren över variabeln (se bilden nedan). Detta är särskilt givande när du arbetar med iteration/loopar och vill se vad som händer varje iteration (varje cykel).

<img src="{{ '/Images/image3.png' | relative_url }}" alt="Kontrollera variabler under run-time" class="image centered"/>

<h3>"Error List"</h3>
I Visual Studio har du ytterligare ett fönster, placerat på botten av VS. I detta fönster hittar du ev. fel i koden som kommer att hindra dig från att exekvera ditt program tills dessa fel är åtgärdade. Exempelvis om du har glömt ett avslutande semikolon eller försöker göra något som VS inte tillåter. I din "Error List" får du då information om vart felet är, vad det beror på och i vilken fil
felet förekommer (se bilden nedan). Du kan även dubbelklicka på dessa felmeddelanden för att direkt nå platsen där felet förekommer, du behöver mao. inte leta igenom din kod.

<img src="{{ '/Images/image10.png' | relative_url }}" alt="'Error List' i Visual Studio" class="image centered"/>

<h3>Fönster i Visual Studio och radnumrering</h3>
Skulle du av en händelse oavsiktligt stänga ned antingen "Solution Explorer", "Error List" eller något annat fönster i VS så är det inga problem att återställa dessa. Du gör detta genom att navigera till View-fliken -> Identifiera det fönster du vill öppna igen -> Klicka på det alternativet.

Utöver det så är radnumrering eller "lines" inte aktiverat i Visual Studio ifrån början. Detta är mao. något man måste aktivera manuellt. Detta är självfallet inget krav, men om det är något som du personligen föredrar så uppnår du detta genom att navigera till Tools-fliken -> Navigera till Options -> Du kommer då direkt till "Environment" (här kan du även ändra temat för Visual Studio om du vill). För att aktivera radnummer så behöver du därefter navigera till "Text Editor" i vänsterspalten -> Välj sedan undermenyn "All Languages" och checka i checkboxen för "Lines numbers".
