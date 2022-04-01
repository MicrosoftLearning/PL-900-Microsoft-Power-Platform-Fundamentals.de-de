---
lab:
  title: 'Lab 7: Erstellen eines einfachen Dashboards'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 5381acb81a59a46f6eb6aca9f2bde18de9846473
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898948"
---
# <a name="module-5-get-started-with-power-bi"></a>Modul 5: Erste Schritte mit Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Lab: Erstellen eines einfachen Dashboards

# <a name="scenario"></a>Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab erstellen Sie ein Power BI-Dashboard, das Daten zu Campusbesuchen visualisiert.

# <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Wir werden die folgenden Schritte ausführen, um das Power BI-Dashboard zu entwerfen und zu erstellen:

-   Verbinden mit Dataverse
-   Daten so transformieren, dass sie benutzerfreundliche Beschreibungen für die zugehörigen Zeilen enthalten (Lookups)
-   Einen Bericht mit verschiedenen Visualisierungen der Informationen zu Campusbesuchen erstellen und veröffentlichen
-   Eine Abfrage in natürlicher Sprache zum Erstellen zusätzlicher Visualisierungen verwenden
-   Eine mobile Ansicht des Power BI-Dashboards erstellen


## <a name="prerequisites"></a>Voraussetzungen

* Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**
* Beendigung von **Modul 2 Lab 1 – Einführung in Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Vor dem Beginn zu beachtende Dinge

-   Wer ist das Zielpublikum des Berichts?
-   Wie wird das Publikum den Bericht verwenden? Typisches Gerät? Der Standort?
-   Haben Sie ausreichend Daten für die Visualisierung?
-   Welche möglichen Merkmale können Sie verwenden, um Daten über die Besuche zu analysieren?

# <a name="exercise-1-create-power-bi-report"></a>Übung 1: Power BI-Bericht erstellen 

**Ziel**: In dieser Übung erstellen Sie, basierend auf Daten aus der Dataverse-Datenbank, einen Power BI-Bericht.

## <a name="task-1-install-power-bi-desktop--prepare-power-bi-service"></a>Aufgabe 1: Power BI Desktop installieren/Power BI-Dienst vorbereiten

1. Befolgen Sie die folgenden Anweisungen zum Einrichten von Power BI: 

    - Wenn Power BI Desktop **bereits** installiert ist, fahren Sie mit [Aufgabe \#2](#task-2-prepare-data) fort.
    
    - Wenn Sie Power BI Desktop nicht installiert haben, führen Sie **Schritt 2** aus.
    
    - Wenn Sie nicht über die erforderlichen Berechtigungen verfügen oder beim Ausführen von Power BI Desktop Probleme auftreten, fahren Sie mit **Schritt 4** fort.

2. Navigieren Sie zu [https://aka.ms/pbidesktopstore](https://aka.ms/pbidesktopstore), um Power BI Desktop herunterzuladen und zu installieren.

    > [!IMPORTANT]
    > Wenn bei der Installation von Power BI Desktop per Microsoft Store Probleme auftreten, versuchen Sie es mit einem eigenständigen Installationsprogramm, das von [https://aka.ms/pbiSingleInstaller](https://aka.ms/pbiSingleInstaller) heruntergeladen werden kann.

3. Wenn Sie Power BI Desktop erfolgreich installiert haben, können Sie jetzt zu [Aufgabe \#2](#task-2-prepare-data) übergehen. Andernfalls fahren Sie mit dem nächsten Schritt fort.

    > Wenn Sie nicht über die erforderlichen Berechtigungen zum Installieren von Desktopanwendungen verfügen oder Schwierigkeiten beim Ausführen oder Konfigurieren von Power BI Desktop haben, führen Sie die folgenden Aufgabenschritte aus.

4. Laden Sie [visits.pbix](../../Allfiles/visits.pbix) herunter, und speichern Sie die Datei auf Ihrem Computer.

5. Navigieren Sie zu [https://app.powerbi.com/](https://app.powerbi.com/), und klicken Sie auf **Anmelden**. 

6. Klicken Sie auf **Mein Arbeitsbereich**. 

7. Wenn die Seite **Daten abrufen** angezeigt wird, klicken Sie auf **Überspringen**. 

8. Erweitern Sie **+Neu**, und wählen Sie **Eine Datei hochladen** aus.

    > [!IMPORTANT]
    > Wenn Sie die Option **+Neu** nicht sehen, müssen Sie möglicherweise das neue Erscheinungsbild für Power BI aktivieren. Stellen Sie sicher, dass Sie die Option **Neues Erscheinungsbild** am oberen Rand Ihres Bildschirms auf **Ein** umschalten.

9. Wählen Sie **Lokale Datei**.

10. Suchen Sie die Datei **visits.pbix**, die Sie zuvor heruntergeladen haben, und wählen Sie sie aus.

11. Sobald der Datenladevorgang abgeschlossen ist, wählen Sie den Bericht **Besuche** aus (beachten Sie, dass als Typ **Bericht** festgelegt ist).

12. Klicken Sie auf **Bearbeiten**. Wenn das Menüelement **Bearbeiten** nicht angezeigt wird, klicken Sie auf **...** , und wählen Sie dann **Bearbeiten** aus.

13. Damit haben den Power BI-Dienst für Ihre Labs eingerichtet. Fahren Sie fort mit [Aufgabe \#3](#task-3-create-chart-and-time-visualizations), aber verwenden Sie den Power BI-Dienst online unter [https://app.powerbi.com](https://app.powerbi.com) anstelle von Power BI Desktop im gesamten Lab.

## <a name="task-2-prepare-data"></a>Aufgabe 2: Vorbereiten von Daten

1.  Finden Sie die URL Ihrer Organisation heraus.

    * Navigieren Sie auf einer neuen Registerkarte zum Power Platform Admin Center unter <https://admin.powerplatform.com>.
    
    * Wählen Sie in der linken Navigationsseite „Umgebungen“ aus, und öffnen Sie dann Ihre Übungsumgebung.
    
    * Klicken Sie im Bereich **Details** mit der rechten Maustaste auf **Umgebungs-URL**, und wählen Sie dann **Linkadresse kopieren** aus.
    
2. Öffnen Sie Power BI Desktop, und melden Sie sich mit Ihren Anmeldeinformationen an, wenn Sie dazu aufgefordert werden.

3. Wählen Sie **Daten abrufen** und dann **Weitere...** aus.

4. Wählen Sie **Power Platform** auf der linken Seite aus, wählen Sie **Common Data Service (Legacy)** aus, und klicken Sie dann auf **Verbinden**. Melden Sie sich mit Ihren Anmeldeinformationen an, wenn Sie dazu aufgefordert werden, und klicken Sie auf **Verbinden**.

5. Fügen Sie die Umgebungs-URL, die Sie zuvor kopiert haben, in das Feld **Server-URL** ein, und klicken Sie dann auf **OK**.

6. Erweitern Sie den Knoten **Entitäten**, wählen Sie die Entitäten **bc_Building** und **bc_Visit** aus, und klicken Sie auf **Laden**.

7. Klicken Sie in der linken vertikalen Symbolleiste auf das Symbol für **Modell**.

8. Ziehen Sie die Spalte **bc_buildingid** aus der Tabelle **bc_Building** in die Spalte **bc_building** in der Tabelle **bc_Visit**. Dadurch wird eine Beziehung zwischen den beiden Tabellen erstellt, damit Power BI dann zusammengehörige Daten anzeigen kann.

9. Wählen Sie in der linken Symbolleiste das Symbol **Bericht** aus.

10. Erweitern Sie den Knoten **bc_Visit** im Bereich **Felder**.

11. Klicken Sie auf **...** neben **bc_Visit**, und wählen Sie **Neue Spalte** aus.

12. Stellen Sie die Formel wie folgt fertig:

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    und drücken Sie die EINGABETASTE. Dadurch wird den Besuchsdaten ein neues Feld mit dem Gebäudenamen hinzugefügt.

13. Klicken Sie auf **...** neben dem Feld **Spalte**, das Sie gerade erstellt haben, und wählen Sie **Umbenennen** aus. Geben Sie **Gebäude** als Feldnamen ein.

14. Klicken Sie neben dem Feld **bc_visitid** auf **...** , und wählen Sie **Umbenennen** aus. Geben Sie als Feldnamen **Besuch** ein.

15. Klicken Sie auf **...** neben dem Feld **bc_scheduledstart**, und wählen Sie **Umbenennen** aus. Geben Sie **Start** als Feldnamen ein.

16. Speichern Sie laufende Arbeiten, indem Sie auf **Datei \| Speichern** klicken und einen Dateinamen Ihrer Wahl eingeben.

## <a name="task-3-create-chart-and-time-visualizations"></a>Aufgabe 3: Diagramm- und Zeitvisualisierungen erstellen

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
    
    * Klicken Sie auf das Säulendiagramm. Klicken Sie auf den Pfeil nach unten, um den **Drilldown**-Modus zu aktivieren, und klicken Sie dann auf die Spalte, um einen Drilldown zur nächsten Ebene (Monate) durchzuführen. Eine weitere Möglichkeit besteht darin, im Menüband auf **Daten/Drill \| Nächste Ebene erweitern** zu klicken.
    
    * Führen Sie einen Drillup und Drilldown aus. Wählen Sie dann verschiedene Balken im Zeitsäulendiagramm aus, und beobachten Sie Änderungen im Kreisdiagrammbericht.
    
11. Speichern Sie laufende Arbeiten, indem Sie auf **Datei \| Speichern** klicken.

# <a name="exercise-2-create-power-bi-dashboard"></a>Übung Nr. 2: Power BI-Dashboard erstellen

## <a name="task-1-publish-power-bi-report"></a>Aufgabe Nr. 1: Power BI-Bericht veröffentlichen

1. Klicken Sie auf die Schaltfläche **Veröffentlichen** auf der Registerkarte „Startseite“ des Menübands.

2. Wählen Sie **Mein Arbeitsbereich** als Ziel aus, und klicken Sie dann auf **Auswählen**.

3. Warten Sie, bis die Veröffentlichung abgeschlossen ist, und klicken Sie dann auf **\<name of your report\>.pbix in Power BI öffnen**.

## <a name="task-2-create-power-bi-dashboard"></a>Aufgabe Nr. 2: Power BI-Dashboard erstellen

1. Sie sollten den Bericht aus der vorherigen Aufgabe geöffnet haben.

2. Wählen Sie im Menü den Eintrag **An ein Dashboard anheften** aus. Je nach Layout müssen Sie möglicherweise auf **...** klicken, um weitere Menüelemente anzuzeigen.

3. Wählen Sie bei der Eingabeaufforderung **An Dashboard anheften** die Option **Neues Dashboard** aus.

4. Geben Sie **[Ihr Nachname] Campusverwaltung** als **Dashboardname** ein, und klicken Sie auf **Live anheften**.

5. Wählen Sie **Mein Arbeitsbereich** am oberen Rand aus, und wählen Sie dann das Dashboard **[Ihr Nachname] Campusverwaltung** aus.

6. Testen Sie die Interaktivität der angezeigten Kreis- und Balkendiagramme.

## <a name="task-3-add-visualizations-using-natural-language"></a>Aufgabe 3: Visualisierungen in natürlicher Sprache hinzufügen

1. Wählen Sie in Ihrem Dashboard **Campusverwaltung** die Leiste **Stellen Sie eine Frage zu Ihren Daten** ganz oben aus.

2. Geben Sie im Frage- und Antwortbereich **Gebäude nach Anzahl der Besuche** ein. Das Balkendiagramm wird angezeigt.

3. Wählen Sie **Visualisierung anheften** aus.

4. Wählen Sie **Vorhandenes Dashboard** aus, wählen Sie Ihr Dashboard **[Ihr Nachname] Campusverwaltung** aus, und klicken Sie dann auf **Anheften**.

5. Klicken Sie auf **F&A beenden**.

Das Dashboard **[Ihr Nachname] Campusverwaltung** sollte angezeigt werden. Möglicherweise müssen Sie nach unten scrollen, um das neue Visuelle Q&A-Element anzuzeigen. 

Ihr Dashboard sollte ungefähr wie folgt aussehen:

![Power BI-Dashboard](media/5-powerbi-result.png)

## <a name="task-4-build-mobile-phone-view-and-share-a-report-with-a-qr-code"></a>Aufgabe Nr. 4: Mobile Telefonansicht erstellen und einen Bericht mit einem QR-Code freigeben

1. Wählen Sie im Dashboard die Option **Bearbeiten \| Layout auf Mobilgeräten** aus.

2. Ordnen Sie die Kacheln wie gewünscht neu an.

3. Klicken Sie oben rechts auf **Layout auf Mobilgeräten**, und ändern Sie die Ansicht in **Weblayout**.

4. Wählen Sie **Mein Arbeitsbereich** oben aus, und wählen Sie dann Ihren **Bericht** aus.

5. Wählen Sie **Bearbeiten** und dann **... \| QR-Code generieren** aus.

6. *Optional:* Wenn Sie über ein mobiles Gerät verfügen, scannen Sie den Code mit einer der für iOS- und Android-Plattformen verfügbaren QR-Scanner-App oder mit der Kamera-App, falls Ihr Gerät dies unterstützt. Melden Sie sich bei Ihrem Konto an, wenn Sie dazu aufgefordert werden. Navigieren Sie auf einem mobilen Gerät durch den Bericht, und schauen Sie ihn sich näher an.

# <a name="challenges"></a>Herausforderungen

* Dashboards und Berichte, die Ihre Campus- und Gebäudepläne enthalten sollen
* Berichten und Analysieren von Besuchsmustern und -trends
* Visualisierung von Überschreitungen der Besuchszeiten
* Streaming von Power BI zur Verarbeitung in Quasi-Echtzeit für einen großen Campus 
