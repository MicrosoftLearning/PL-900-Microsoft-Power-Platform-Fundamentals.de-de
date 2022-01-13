---
lab:
    title: 'Lab 7: Ein einfaches Dashboard erstellen'
    module: 'Modul 5: Erste Schritte mit Power BI'
---

# Modul 5: Erste Schritte mit Power BI
## Lab: Ein einfaches Dashboard erstellen

# Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab erstellen Sie ein Power BI-Dashboard, das Daten zu Campusbesuchen visualisiert.

# Allgemeine Schritte des Lab

Wir werden die folgenden Schritte ausführen, um das Power BI-Dashboard zu entwerfen und zu erstellen:

-   Eine Verbindung zu Dataverse herstellen
-   Die Daten so transformieren, dass sie benutzerfreundliche Beschreibungen für die zugehörigen Zeilen enthalten (Lookups)
-   Einen Bericht mit verschiedenen Visualisierungen der Informationen zu Campusbesuchen erstellen und veröffentlichen
-   Eine Abfrage in natürlicher Sprache zum Erstellen zusätzlicher Visualisierungen verwenden
-   Eine mobile Ansicht des Power BI-Dashboards erstellen


## Voraussetzungen

* Beendigung von **Modul 0 Lab 0 – Lab-Umgebung bestätigen**
* Beendigung von **Modul 2 Lab 1 – Einführung in Microsoft Dataverse**

## Vor dem Beginn zu beachtende Dinge

-   Wer ist das Zielpublikum des Berichts?
-   Wie wird das Publikum den Bericht verwenden? Typisches Gerät? Standort?
-   Haben Sie ausreichend Daten für die Visualisierung?
-   Welche möglichen Merkmale können Sie verwenden, um Daten über die Besuche zu analysieren?

# Übung Nr. 1: Power BI-Bericht erstellen 

**Ziel:** In dieser Übung erstellen Sie einen Power BI-Bericht auf Basis von Daten aus der Dataverse-Datenbank.

## Aufgabe Nr. 1: Power BI Desktop installieren/Power BI-Dienst vorbereiten

1. Befolgen Sie die folgenden Anweisungen zum Einrichten von Power BI: 

    - Wenn Power BI Desktop **bereits** installiert ist, fahren Sie mit [Aufgabe 2](#task-2-prepare-data) fort.
    
    - Wenn Sie Power BI Desktop nicht installiert haben, führen Sie **Schritt 2** aus.
    
    - Wenn Sie nicht über die erforderlichen Berechtigungen verfügen oder beim Ausführen von Power BI Desktop Probleme auftreten, fahren Sie mit **Schritt 4** fort.

2. Navigieren Sie zu [https://aka.ms/pbidesktopstore](https://aka.ms/pbidesktopstore), um Power BI Desktop herunterzuladen und zu installieren.

    > [WICHTIG!]
    > Wenn bei der Installation von Power BI Desktop per Microsoft Store Probleme auftreten, versuchen Sie es mit einem eigenständigen Installationsprogramm, das von [https://aka.ms/pbiSingleInstaller](https://aka.ms/pbiSingleInstaller) heruntergeladen werden kann.

3. Wenn Sie Power BI Desktop erfolgreich installiert haben, können Sie jetzt zu [Aufgabe 2](#task-2-prepare-data) übergehen. Andernfalls fahren Sie mit dem nächsten Schritt fort.

    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Installieren von Desktopanwendungen verfügen oder Schwierigkeiten beim Ausführen oder Konfigurieren von Power BI Desktop haben, führen Sie die folgenden Aufgabenschritte aus.

4. Laden Sie [visits.pbix](../../Allfiles/visits.pbix) herunter, und speichern Sie die Datei auf Ihrem Computer.

5. Navigieren Sie zu [https://app.powerbi.com/](https://app.powerbi.com/), und klicken Sie auf **Anmelden**. 

6. Klicken Sie auf **Mein Arbeitsbereich**. 

7. Wenn die Seite **Daten abrufen** angezeigt wird, klicken Sie auf **Überspringen**. 

8. Erweitern Sie **+Neu**, und wählen Sie **Eine Datei hochladen** aus.

    > [WICHTIG!]
    > Wenn Sie die Option **+Neu** nicht sehen, müssen Sie möglicherweise das neue Erscheinungsbild für Power BI aktivieren. Stellen Sie sicher, dass Sie die Option **Neues Erscheinungsbild** am oberen Rand Ihres Bildschirms auf **Ein** umschalten.

9. Wählen Sie **Lokale Datei** aus.

10. Suchen Sie die Datei **visits.pbix**, die Sie zuvor heruntergeladen haben, und wählen Sie sie aus.

11. Sobald der Datenladevorgang abgeschlossen ist, wählen Sie  den Bericht **Besuche** aus (beachten Sie, dass als Typ **Bericht** festgelegt ist).

12. Klicken Sie auf **Bearbeiten**. Wenn das Menüelement **Bearbeiten** nicht angezeigt wird, klicken Sie auf [...], und wählen Sie dann **Bearbeiten** aus.

13. Damit haben den Power BI-Dienst für Ihre Labs eingerichtet. Fahren Sie fort mit [Aufgabe 3](#task-3-create-chart-and-time-visualizations), aber verwenden Sie den Power BI-Dienst online unter [https://app.powerbi.com](https://app.powerbi.com) anstelle von Power BI Desktop im gesamten Lab.

## Aufgabe Nr. 2: Daten vorbereiten

1.  Finden Sie die URL Ihrer Organisation heraus.

    * Navigieren Sie auf einer neuen Registerkarte zu Power Platform Admin Center unter <https://admin.powerplatform.com>.
    
    * Wählen Sie in der linken Navigationsseite „Umgebungen“ aus, und öffnen Sie dann Ihre Übungsumgebung.
    
    * Klicken Sie im Panel **Details** mit der rechten Maustaste auf **Umgebungs-URL**, und wählen Sie dann **Linkadresse kopieren** aus.
    
2. Öffnen Sie Power BI Desktop, und melden Sie sich mit Ihren Anmeldeinformationen an, wenn Sie dazu aufgefordert werden.

3. Wählen Sie **Daten abrufen** und wählen Sie dann **mehr...** aus.

4. Wählen Sie **Power Platform** auf der linken Seite aus, wählen Sie **Common Data Service (Legacy)** aus und klicken Sie dann auf **Verbinden**. Melden Sie sich bei Aufforderung mit Ihren Anmeldeinformationen an und klicken Sie auf **Verbinden**.

5. Fügen Sie die Umgebungs-URL, die Sie zuvor kopiert haben, in das Feld **Server-URL** ein, und klicken Sie dann auf **OK**.

6. Erweitern Sie den Knoten **Entitäten**, wählen Sie die Entitäten **bc_Building** und **bc_Visit** aus, und klicken Sie auf **Laden**.

7. Klicken Sie in der linken vertikalen Symbolleiste auf das Symbol für **Modell**.

8. Ziehen Sie die Spalte **bc_buildingid** aus der Tabelle **bc_Building** in die Spalte **bc_building** in der Tabelle **bc_Visit**. Dadurch wird eine Beziehung zwischen den beiden Tabellen erstellt, mit deren Hilfe Power BI dann zusammengehörige Daten anzeigen kann.

9. Wählen Sie auf der linken Symbolleiste das Symbol **Bericht** aus.

10. Erweitern Sie den Knoten **bc_Visit** im Bereich **Felder**.

11. Klicken Sie auf **...** neben **bc_Visit**, und wählen Sie **Neue Spalte** aus.

12. Stellen Sie die Formel wie folgt fertig:

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    und drücken Sie die EINGABETASTE. Dadurch wird den Besuchsdaten ein neues Feld mit dem Gebäudenamen hinzugefügt.

13. Klicken Sie auf **...** neben dem Feld **Spalte**, das Sie gerade erstellt haben, und wählen Sie **Umbenennen** aus. Geben Sie **Gebäude** als Feldnamen ein.

14. Klicken Sie auf **...** neben dem Feld **bc_visitid**, und wählen Sie **Umbenennen** aus. Geben Sie als Feldnamen **Besuch** ein.

15. Klicken Sie auf **...** neben dem Feld **bc_scheduledstart**, und wählen Sie **Umbenennen** aus. Geben Sie **Start** als Feldnamen ein.

16. Speichern Sie die aktuelle Arbeit, indem Sie auf **Datei \| Speichern** und einen Dateinamen Ihrer Wahl eingeben.

## Aufgabe Nr. 3: Diagramm- und Zeitvisualisierungen erstellen

1. Klicken Sie auf das Kreisdiagrammsymbol im Bereich **Visualisierungen**, um ein Diagramm einzufügen.

2. Ziehen Sie das Feld **Gebäude** in das Zielfeld **Legende**.

3. Ziehen Sie das Feld **Besuch** in das Zielfeld **Werte**.

4. Ändern Sie die Größe des Kreisdiagramms mithilfe der Ziehpunkte an den Ecken, sodass alle Diagrammkomponenten sichtbar sind.

5. Klicken Sie auf den Bericht außerhalb des Kreisdiagramms, um die Auswahl aufzuheben, und wählen Sie „Gestapeltes Säulendiagramm“ im Bereich **Visualisierungen** aus. 

6. Ziehen Sie das Feld **Besuch** in das Zielfeld **Werte**.

7. Ziehen Sie das Feld **Start** in das Zielfeld **Achse**.

8. Klicken Sie im Bereich „Visualisierungen“ auf das **x** neben **Tag** und **Quartal**, sodass als Achse nur die Summen von **Jahr** und **Monat** angezeigt werden.

9. Ändern Sie die Größe des Diagramms mithilfe der Ziehpunkte an den Ecken je nach Bedarf.

10. Testen Sie die Berichtsinteraktivität:

    * Wählen Sie verschiedene Gebäudesegmente im Kreisdiagramm aus, und beobachten Sie Änderungen im Zeitbericht.
    
    * Klicken Sie auf das Säulendiagramm. Klicken Sie auf den Pfeil nach unten, um den **Drilldown**-Modus zu aktivieren, und klicken Sie dann auf die Spalte, um einen Drilldown zur nächsten Ebene (Monate) durchzuführen. Alternativ dazu können Sie auch auf **Daten/Drilldown ausführen \| Nächste Ebene erweitern** im Menüband klicken.
    
    * Führen Sie einen Drillup und Drilldown aus. Wählen Sie dann verschiedene Balken im Zeitsäulendiagramm aus, und beobachten Sie Änderungen im Kreisdiagrammbericht.
    
11. Speichern Sie die aktuelle Arbeit, indem Sie auf **Datei \| Speichern** klicken.

# Übung Nr. 2: Power BI-Dashboard erstellen

## Aufgabe Nr. 1: Power BI-Bericht veröffentlichen

1. Klicken Sie auf die Schaltfläche **Veröffentlichen** auf der Registerkarte „Startseite“ des Menübands.

2. Wählen Sie **Mein Arbeitsbereich** als Ziel aus, und klicken Sie dann auf **Auswählen**.

3. Warten Sie, bis die Veröffentlichung abgeschlossen ist, und klicken Sie dann auf **\<Name Ihres Berichts\>.pbix in Power BI öffnen**.

## Aufgabe Nr. 2: Power BI-Dashboard erstellen

1. Sie sollten den Bericht aus der vorherigen Aufgabe geöffnet haben.

2. Wählen Sie im Menü den Eintrag **An ein Dashboard anheften** aus. Je nach Layout müssen Sie möglicherweise auf [...] klicken, um weitere Menüelemente anzuzeigen.

3. Wählen Sie bei der Eingabeaufforderung **An Dashboard anheften** die Option **Neues Dashboard** aus.

4. Geben Sie **[Ihr Nachname] Campusverwaltung** als **Dashboardname** ein, und klicken Sie auf **Live anheften**.

5. Wählen Sie am oberen Rand **Mein Arbeitsbereich** aus, und wählen Sie dann das Dashboard **[Ihr Nachname] Campusverwaltung** aus.

6. Testen Sie die Interaktivität der angezeigten Kreis- und Balkendiagramme.

## Aufgabe Nr. 3: Visualisierungen in natürlicher Sprache hinzufügen

1. Wählen Sie in Ihrem Dashboard **Campusverwaltung** die Leiste **Stellen Sie eine Frage zu Ihren Daten** ganz oben aus.

2. Geben Sie im Frage- und Antwortbereich **Gebäude nach Anzahl der Besuche** ein. Das Balkendiagramm wird angezeigt.

3. Wählen Sie **Visualisierung anheften** aus.

4. Wählen Sie **Vorhandenes Dashboard** aus, wählen Sie Ihr Dashboard **[Ihr Nachname] Campusverwaltung** aus, und klicken Sie dann auf **Anheften**.

5. Klicken Sie auf **Q&A beenden**.

Ihr Dashboard **[Ihr Nachname] Campusverwaltung** sollte angezeigt werden. Möglicherweise müssen Sie nach unten scrollen, um das neue visuelle Q&A-Element anzuzeigen. 

Ihr Dashboard sollte ungefähr wie folgt aussehen:

![Power BI-Dashboard](media/5-powerbi-result.png)

## Aufgabe Nr. 4: Mobile Telefonansicht erstellen und einen Bericht mit einem QR-Code freigeben

1. Wählen Sie im Dashboard **Bearbeiten \| Mobile Ansicht** aus.

2. Ordnen Sie die Kacheln wie gewünscht neu an.

3. Klicken Sie auf **Telefonansicht** oben rechts, und ändern Sie die Ansicht in **Webansicht**.

4. Wählen Sie **Mein Arbeitsbereich** oben aus, und wählen Sie dann Ihren **Bericht** aus.

5. Wählen Sie **Bearbeiten** und dann **... \| QR-Code generieren** aus.

6. *Optional:* Wenn Sie über ein mobiles Gerät verfügen, scannen Sie den Code mit einer der für iOS- und Android-Plattformen verfügbaren QR-Scanner-App oder mit der Kamera-App, falls Ihr Gerät dies unterstützt. Melden Sie sich bei Ihrem Konto an, wenn Sie dazu aufgefordert werden. Navigieren Sie auf einem mobilen Gerät durch den Bericht, und schauen Sie ihn sich näher an.

# Herausforderungen

* Dashboards und Berichte, die Ihre Campus- und Gebäudepläne enthalten sollen
* Berichten und Analysieren von Besuchsmustern und -trends
* Visualisierung von Überschreitungen der Besuchszeiten
* Streaming von Power BI zur Verarbeitung in Quasi-Echtzeit für einen großen Campus 
