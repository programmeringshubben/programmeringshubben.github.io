---
title: Demoprojekt
icon: fa-lightbulb
order: 5
---
<a href="DemoProjekt.zip" class="button" style="margin-top:0;margin-bottom:40px;color:#a6a6a6>Ladda ned</a>
<br>
Om du känner för att testa på utvecklingsmiljön så hittar du här ett lite mindre demoprojekt som du kan nyttja för att
bli familjär med Visual Studio-miljön och testa på några utav uppgifterna som du hittar på webbplats.

Testa exempelvis på att exekvera ett program (F5), att "följa med" i koden och bli familjär med hur fönster och dylikt
ser ut i Visual Studio.

Ett exempel på vad du kan testa i projektet är hur "felsäkert" programmet är genom att skriva
in text istället för ett årtal när programmet frågar om ditt födelseår. Du märker då att
programmet kraschar och att ett felmeddelande dyker upp, <code>FormatException</code>. Detta beror på att
vi försöker konvertera text till ett heltal (<code>Convert.ToInt32</code>) vilket inte är möjligt. Reflektera kring
hur man kan undvika detta problem eller, om du vill utmana dig själv, lös problemet!
