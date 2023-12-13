# Updated GDT - README
## Game-of-Dice-Task für Limesurvey

Dieses Projekt ist eine für Limesurvey aktualisierte Version der Game-of-Dice Task.<br />
<br />
> [!WARNING]
> **WICHTIGE vorab Info:** In der ersten Frage müssen Sie in den "Source-Code" der Frage gehen, um Einstellungen anpassen zu können. <br />
> Mehr dazu finden Sie unter dem Punkt **"Einstellungen anpassen"**.
<br />

## Inhaltsangabe
# Table of Contents
1. **Generelle Struktur**
2. **Ressourcen einfügen**
3. **Einstellungen anpassen**
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## GENERELLE STRUKTUR: 

Für das GDT haben wir 10 Fragegruppen. <br />
<br />
Die erste beinhaltet die Willkommensnachricht, sowie eine unsichtbare Frage, welche die Einstellungen beinhaltet. <br />
Sollten Sie also eine eigene Willkommensnachricht hinzufügen, müssen Sie trotzdem die Unsichtbare Frage behalten! <br />
<br />
Die zweite beinhaltet die Einführung, in der die Teilnehmer-Daten abgefragt werden. <br />
<br />
Die dritte bis neunte Fragegruppe beinhaltet für die Teilnehmer eine Anleitung des GDTs. Diese variiert je nach mobiler oder Desktop-Ansicht. <br />
<br />
Die zehnte Fragegruppe beinhaltet die Runden des GDTs die der Spieler spielt. <br />
Alle Runden werden in der selben Fragegruppe gespielt und danach geht die Umfrage automatisch in die nächste Fragegruppe. Daher gibt es keinen "Weiter"-Knopf. <br /> 
<br />
Damit diese Fragegruppe funktioniert **MUSS** vorher die unsichtbare Frage in unserer ersten Fragegruppe aufgerufen werden. <br />
<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## RESSOURCEN EINFÜGEN

Die Dateien aus der ***"Ressourcen.zip"*** müssen in den richtigen Ornder Ihrer Limesurvey-Umfrage. <br />
Sobald ihre Umfrage in Limesurvey erstellt wurde, finden Sie in Ihrem Limesurvey Ordner unter dem Pfad ***"limesurvey\upload\surveys"*** ein Ordner, der als Namen Ihre **SurveyID** hat. <br />
In diesem Ordner gibt es einen ***"files"*** Ordner. Dort müssen Sie die Dateien einfügen. (Nicht in einem Zusatz Ordner, sondern einzeln direkt dadrin!) <br />
<br />
Sollten Sie Ihre **SurveyID** nicht kennen, können Sie diese in der Übersicht Ihrer Umfrage in Limesurvey finden. Ebenfalls kann man diese in der URL im Limesurvey sehen.


------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## EINSTELLUNGEN ANPASSEN:


Falls Sie die Rundenanzahl anpassen möchten oder die Ergebnisse der einzelnen Runden ändern möchten, können Sie das in der allerersten Frage unserer Umfrage machen. <br />
Diese hat als Textinhalt ***"WICHTIG!"***, damit diese leicht zu finden ist. <br />
Wenn Sie die Frage in Limesurvey ausgewählt haben, müssen Sie auf ***"Bearbeiten" ("Edit")*** drücken, wodurch Sie den Inhalt der Frage sehen und bearbeiten können. <br />
Über dem Text ***"Wichtig!"*** können Sie einen Button ***"Quellcode" ("Source")*** finden. Sobald Sie dadrauf drücken, sehen Sie im Textfeld den Code der Frage. <br />
Dort steht auch nochmal, was Sie machen müssen. <br />
<br />

### Rundenanzahl

Es gibt einmal die Variable *"RundenAnzahl"* in Zeile 4. <br />
Dort können Sie die existierende Zahl durch eine beliebige Zahl austauschen. Diese Zahl bestimmt wieviele Runden die Teilnehmer spielen müssen. 
> [!WARNING]
> Bitte achten Sie dadrauf, dass hinter der Zahl ein **Symikolon (;)** steht. Sonst funktioniert der Code nicht. <br />
> Bsp:
> 
> ```
> var RundenAnzahl = 18;
> ```

> [!CAUTION]
> Sollten Sie mehr als 30 Runden spielen, **MÜSSEN** Sie ebenfalls die Variable *"RundenErgebnisse"* bearbeiten! 


### Ergebnisse

In Zeile 10 befindet sich die Variable *"RundenErgebnisse"*, welche das Ergebnis für jede Runde bestimmt. <br />
Die Zahlen in den eckigen Klammern stehen für die Würfelergebnisse im Spiel in chronologischer Reihenfolge. <br />
<br />
Bspw. wenn die Klammer *[4,5,6]* beinhaltet, dann wird in *Runde 1* eine 4 gewürfelt, in *Runde 2* eine 5 und in *Runde 3* eine 6. <br />
Alle überflüssigen Zahlen werden ignoriert!

> [!CAUTION]
> Wenn zu wenig Zahlen in der Klammer stehen, funktioniert das Spiel nicht! Es müssen **mindestens** soviele Zahlen wie Runden dadrin stehen!

> [!WARNING]
> Auch hier gilt: Bitte achten Sie dadrauf, dass hinter der geschlossenen *eckigen Klammer (])* ein **Symikolon (;)** steht. Zusätzlich müssen die Zahlen mit einem **Komma (,)** getrennt werden. <br />
> Bsp:
> 
> ```
> var RundenErgebnisse = [1,2,3];
> ```

<br />
Die voreingegebenen Rundenergebnisse beinhalten Zahlen für 30 Runden, sodass alle Zahlen gleich oft auftauchen. <br />
Ebenfalls sind diese so angeordent, dass bei *6*, *12*, *18* oder *24* Runden alle Zahlen gleich oft auftauchen. <br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------
