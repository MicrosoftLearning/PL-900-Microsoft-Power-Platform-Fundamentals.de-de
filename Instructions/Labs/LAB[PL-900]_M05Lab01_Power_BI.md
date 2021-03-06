---
lab:
  title: 'Lab 5: Erstellen eines einfachen Dashboards'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 8d104c42de9d4114c668a63a4d8d30cbbcc4b39e
ms.sourcegitcommit: 36c8fda9cdc6f448416d7000e38c1606bea87d2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2022
ms.locfileid: "144812933"
---
# <a name="module-5-get-started-with-power-bi"></a>Modul 5: Erste Schritte mit Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Lab: Erstellen eines einfachen Dashboards

# <a name="scenario"></a>Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab erstellen Sie ein Power BI-Dashboard, das Daten zu Campusbesuchen visualisiert.

# <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Wir werden die folgenden Schritte ausführen, um ein Power BI-Dashboard zu entwerfen und zu erstellen:

-   Verbinden mit Dataverse

-   Daten so transformieren, dass sie benutzerfreundliche Beschreibungen für die zugehörigen Zeilen enthalten (Lookups)

-   Einen Bericht mit verschiedenen Visualisierungen der Informationen zu Campusbesuchen erstellen und veröffentlichen

-   Eine Abfrage in natürlicher Sprache zum Erstellen zusätzlicher Visualisierungen verwenden

-   Eine mobile Ansicht des Power BI-Dashboards erstellen

## <a name="prerequisites"></a>Voraussetzungen

-   Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**

-   Beendigung von **Modul 2 Lab 1 – Einführung in Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Vor dem Beginn zu beachtende Dinge

-   Wer ist das Zielpublikum des Berichts?

-   Wie wird das Publikum den Bericht verwenden? Typisches Gerät? Der Standort?

-   Haben Sie ausreichend Daten für die Visualisierung?

-   Welche möglichen Merkmale können Sie verwenden, um Daten über die Besuche zu analysieren?

# <a name="exercise-1-create-power-bi-report"></a>Übung 1: Power BI-Bericht erstellen

**Ziel**: In dieser Übung erstellen Sie einen Power BI-Bericht basierend auf den Daten des Excel-Arbeitsblatts, das wir in einer vorherigen Übung genutzt haben.

## <a name="task-1-prepare-power-bi-service"></a>Aufgabe \#1: Vorbereiten des Power BI-Diensts

1.  Laden Sie [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) herunter, und speichern Sie die Datei auf Ihrem Computer.

2.  Navigieren Sie bei Bedarf zu <https://app.powerbi.com/>, und melden Sie sich an.

3.  Wählen Sie unten links auf dem Bildschirm **Daten abrufen** aus.

4.  Wählen Sie die Schaltfläche **Abrufen** unter **Dateien** im Abschnitt **Neuen Inhalt erstellen** aus.

5.  Wählen Sie **Lokale Datei**.

6.  Suchen Sie die Datei **visits.pbix**, die Sie zuvor heruntergeladen haben, und wählen Sie sie aus.

7.  Sobald der Datenladevorgang abgeschlossen ist, wählen Sie den Bericht **Besuche** aus (beachten Sie, dass als Typ **Bericht** festgelegt ist).

8.  Klicken Sie auf **Bearbeiten**. Wenn das Menüelement **Bearbeiten** nicht angezeigt wird, klicken Sie auf **...** , und wählen Sie dann **Bearbeiten** aus.

Damit haben den Power BI-Dienst für Ihre Labs eingerichtet. 

## <a name="task-2-create-chart-and-time-visualizations"></a>Aufgabe \#2: Diagramm- und Zeitvisualisierungen erstellen

1.  Klicken Sie auf das **Kreisdiagramm** symbol im Bereich **Visualisierungen**, um ein Diagramm einzufügen.

2.  Drücken Sie den Dropdownpfeil neben **bc_name** im Bereich „Felder“. Ziehen Sie das Feld **Gebäude** in das Zielfeld **Legende**.

3.  Drücken Sie den Dropdownpfeil neben **bc_Visit** im Bereich „Felder“. Ziehen Sie das Feld **Besuch**, und legen Sie es im Feld **Werte** ab.

4.  Ändern Sie die Größe des Kreisdiagramms mithilfe der Ziehpunkte an den Ecken, sodass alle Diagrammkomponenten sichtbar sind.

5.  Klicken Sie auf den Bericht außerhalb des Kreisdiagramms, um die Auswahl aufzuheben, und wählen Sie „Gestapeltes Säulendiagramm“ im Bereich **Visualisierungen** aus.

6.  Drücken Sie den Dropdownpfeil neben **bc_Visit** im Bereich „Felder“. Ziehen Sie das Feld **Besuch**, und legen Sie es im Feld **Werte** ab.

7.  Ziehen Sie das Feld **Start** in das Zielfeld **Achse**.

8.  Klicken Sie im Bereich „Visualisierungen“ auf das **x** neben **Jahr** und **Quartal**, sodass auf der Achse nur noch die Summen von **Monat** und **Tag** angezeigt werden.

9.  Ändern Sie die Größe des Diagramms mithilfe der Ziehpunkte an den Ecken je nach Bedarf.

10. Testen Sie die Berichtsinteraktivität:

    1.  Klicken Sie auf verschiedene Gebäudesegmente im Kreisdiagramm, und beobachten Sie Änderungen im Zeitbericht.

    2.  Klicken Sie auf das Säulendiagramm. Drücken Sie die NACH-UNTEN-TASTE, um den **Drilldownmodus** zu aktivieren (oder klicken Sie mit der rechten Maustaste auf das Diagramm, und wählen Sie **Drilldown** aus), und klicken Sie dann auf eine Spalte, um auf die nächste Ebene (Tage) zu gelangen. 
    
    3.  Führen Sie einen Drillup und Drilldown aus. Wählen Sie dann verschiedene Balken im Zeitsäulendiagramm aus, und beobachten Sie Änderungen im Kreisdiagrammbericht.

11. Speichern Sie laufende Arbeiten, indem Sie auf **Speichern** klicken.

# <a name="exercise-2-create-power-bi-dashboard"></a>Übung \#2: Power BI-Dashboard erstellen

## <a name="task-1-create-power-bi-dashboard"></a>Aufgabe \#1: Power BI-Dashboard erstellen

1.  Sie sollten den Bericht aus der vorherigen Aufgabe geöffnet haben.

2.  Wählen Sie im Menü den Eintrag **An ein Dashboard anheften** aus. Je nach Layout müssen Sie möglicherweise auf **...** klicken, um weitere Menüelemente anzuzeigen.

3.  Wählen Sie bei der Eingabeaufforderung **An Dashboard anheften** die Option **Neues Dashboard** aus.

4.  Geben Sie **Campusverwaltung** unter **Dashboardname** ein, und klicken Sie auf **Live anheften**.

5.  Wählen Sie **Mein Arbeitsbereich** am oberen Rand aus, und wählen Sie dann das Dashboard **[Ihr Nachname] Campusverwaltung** aus.

6.  In einem Popup wird Ihnen mitgeteilt, dass das Dashboard erstellt wurde. Wählen Sie **Zum Dashboard wechseln** aus.

7.  Testen Sie die Interaktivität der angezeigten Kreis- und Balkendiagramme.

## <a name="task-2-add-visualizations-using-natural-language"></a>Aufgabe \#2: Visualisierungen in natürlicher Sprache hinzufügen

1.  Wählen Sie in Ihrem Dashboard **Campusverwaltung** die Leiste **Stellen Sie eine Frage zu Ihren Daten** ganz oben aus.

2.  Geben Sie im Frage- und Antwortbereich **Gebäude nach Anzahl der Besuche** ein. Ein Balkendiagramm wird angezeigt.

3.  Wählen Sie **Visualisierung anheften** aus.

4.  Wählen Sie **Vorhandenes Dashboard** und dann Ihr Dashboard **Campusverwaltung** aus, und klicken Sie auf **Anheften**.

5.  Klicken Sie auf **F&A beenden**.

Ihr **Campus Management**-Dashboard sollte mit drei visuellen Elementen angezeigt werden. Möglicherweise müssen Sie nach unten scrollen, um das neue Visuelle Q&A-Element anzuzeigen.

Ihr Dashboard sollte ungefähr wie folgt aussehen:

![](media/5-powerbi-result.png)
