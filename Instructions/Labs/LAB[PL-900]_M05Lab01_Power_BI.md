---
lab:
  title: "Lab\_5: Erstellen eines einfachen Dashboards"
  module: 'Module 5: Get Started with Power BI'
---

## Lab 5: Erstellen eines einfachen Dashboards

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Mandant ist ein Testmandant; er kann nach Abschluss des Kurses nicht verwendet oder aufgerufen werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab erstellen Sie einen Power BI-Bericht und ein Dashboard, das Daten zu Campusbesuchen visualisiert.

## Weiterführende Schritte des Lab

Wir werden die folgenden Schritte ausführen, um ein Power BI-Dashboard zu entwerfen und zu erstellen:

-   Einen Bericht mit verschiedenen Visualisierungen der Informationen zu Campusbesuchen erstellen

-   Eine Abfrage in natürlicher Sprache zum Erstellen zusätzlicher Visualisierungen verwenden

## Voraussetzungen

- Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**
- Abschluss von **Modul 2 Lab 1: Datenmodellierung**

## Vor dem Beginn zu beachtende Dinge

-   Wer ist das Zielpublikum des Berichts?
-   Wie wird das Publikum den Bericht verwenden? Typisches Gerät? Der Standort?
-   Haben Sie ausreichend Daten für die Visualisierung?
-   Welche möglichen Merkmale können Sie verwenden, um Daten über die Besuche zu analysieren?

## Übung 1: Power BI-Bericht erstellen

**Ziel**: In dieser Übung erstellen Sie einen Power BI-Bericht basierend auf den Daten des Excel-Arbeitsblatts, das wir in einer vorherigen Übung genutzt haben.

### Aufgabe \#1: Vorbereiten des Power BI-Diensts

1.  Eine Datei „Visits.pbix“ sollte auf Ihrer VM im Ordner „AllFiles“ auf dem Desktop gespeichert sein. Laden Sie die Datei [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) herunter, und speichern Sie sie auf Ihrem Computer, falls sie dort noch nicht vorhanden ist.

2.  Öffnen Sie eine neue Registerkarte, navigieren Sie zu <https://app.powerbi.com/>, und melden Sie sich bei Bedarf an.

3.  Wählen Sie im linken Navigationsbereich **Mein Arbeitsbereich** aus.

5.  Wählen Sie **Hochladen** und dann **Durchsuchen** aus.

6.  Suchen Sie die zuvor heruntergeladene Datei **visits.pbix**, und wählen Sie sie aus. 

7.  Wählen Sie nach Abschluss des Datenladevorgangs den **Besuchsbericht** aus.

    > **Hinweis**: Der Typ ist auf **Bericht** festgelegt. Wählen Sie das Dataset nicht aus.

8.  Wählen Sie **Bearbeiten** aus. 

    Sollte das Menüelement **Bearbeiten** nicht angezeigt werden, wählen Sie die Auslassungspunkte **...** und dann **Bearbeiten** aus.

Damit haben den Power BI-Dienst für Ihre Labs eingerichtet.


### Aufgabe \#2: Diagramm- und Zeitvisualisierungen erstellen

1.  Wählen Sie das **Kreisdiagrammsymbol** im Bereich **Visualisierungen** aus, um ein Diagramm einzufügen.

2.  Erweitern Sie **bc_Visit** im Bereich **Felder**. Ziehen Sie das Feld **Gebäude** in das Feld **Legende**, und legen Sie es dort ab.

3.  Ziehen Sie das Feld **Besuch** in das Feld **Werte**, und legen Sie es dort ab.

4.  Ändern Sie die Größe des Kreisdiagramms mithilfe der Ziehpunkte an den Ecken, sodass alle Diagrammkomponenten sichtbar sind.

5.  Klicken Sie auf den Bericht außerhalb des Kreisdiagramms, um die Auswahl aufzuheben, und wählen Sie das Symbol **Gestapeltes Säulendiagramm** im Fenster **Visualisierungen** aus.

6.  Erweitern Sie **bc_Visit** im Bereich **Felder**, wenn diese Angabe noch nicht erweitert wurde. Ziehen Sie das Feld **Besuch** in das Feld **Y-Achse**, und legen Sie es dort ab.

7.  Ziehen Sie das Feld **Start** in das Feld **X-Achse**, und legen Sie es dort ab.

8.  Klicken Sie im Bereich **Visualisierungen** auf das **x** neben **Jahr** und **Quartal**, sodass auf der Achse nur noch die Summen von **Monat** und **Tag** angezeigt werden.

9.  Ändern Sie die Größe des Diagramms mithilfe der Ziehpunkte an den Ecken je nach Bedarf.

10. Testen Sie die Berichtsinteraktivität:

    1.  Wählen Sie verschiedene Gebäudesegmente im Kreisdiagramm aus, und beobachten Sie Änderungen im gestapelten Säulendiagramm.

    2.  Wählen Sie das gestapelte Säulendiagramm aus. Wählen Sie den Pfeil nach oben aus, um ein **Drillup** auszuführen. Wählen Sie den Pfeil nach unten aus, um den **Drilldownmodus** zu aktivieren, und wählen Sie dann eine Spalte aus, um einen Drilldown zur nächsten Ebene (Tage) durchzuführen.

    3.  Führen Sie einen Drillup und Drilldown aus. Wählen Sie dann verschiedene Balken im gestapelten Säulendiagramm aus, und beobachten Sie Änderungen im Kreisdiagrammbericht.

11. Speichern Sie die derzeitige Arbeit, indem Sie **Diesen Bericht speichern** auswählen.


## Übung 2: Power BI-Dashboard erstellen

### Aufgabe \#1: Power BI-Dashboard erstellen

1.  Sie sollten den Bericht aus der vorherigen Aufgabe geöffnet haben.

2.  Wählen Sie im Menü den Eintrag **An ein Dashboard anheften** aus. Abhängig vom Layout müssen Sie möglicherweise **...** auswählen, um weitere Optionen anzuzeigen.

3.  Wählen Sie bei der Eingabeaufforderung **An Dashboard anheften** die Option **Neues Dashboard** aus.

4.  Geben Sie `Campus Management` als **Dashboardnamen** ein, und wählen Sie **Live anheften** aus.

5.  In einem Popup wird Ihnen mitgeteilt, dass das Dashboard erstellt wurde. Wählen Sie **Zum Dashboard wechseln** aus.

6.  Testen Sie die Interaktivität der angezeigten Kreis- und Balkendiagramme.


### Aufgabe \#2: Visualisierungen in natürlicher Sprache hinzufügen

1.  Wählen Sie in Ihrem Dashboard **Campusverwaltung** die Leiste **Stellen Sie eine Frage zu Ihren Daten** ganz oben aus.

2.  Geben Sie im Frage- und Antwortbereich `buildings by number of visits` ein. Ein Balkendiagramm wird angezeigt.

3.  Wählen Sie **Visualisierung anheften** aus.

4.  Wählen Sie **Vorhandenes Dashboard** und dann das Dashboard **Campusverwaltung** aus, und klicken Sie auf **Anheften**.

5.  Wählen Sie **F&A verlassen** aus.

Ihr **Campus Management**-Dashboard sollte mit drei visuellen Elementen angezeigt werden. Möglicherweise müssen Sie nach unten scrollen, um das neue Visuelle Q&A-Element anzuzeigen.

Ihr Dashboard sollte ungefähr wie folgt aussehen:

![](media/5-powerbi-result.png)
