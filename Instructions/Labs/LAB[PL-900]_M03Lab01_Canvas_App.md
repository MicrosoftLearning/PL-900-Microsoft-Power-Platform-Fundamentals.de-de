---
lab:
  title: 'Lab 2: Eine Canvas-App erstellen'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 24d99d14079d40f74a43ed0de64dd6ae5d7046c7
ms.sourcegitcommit: 0118c25a230425d0ccba16e6c3922053ee07c183
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2022
ms.locfileid: "144810919"
---
# <a name="module-3-get-started-with-power-apps"></a>Modul 3: Erste Schritte mit Power Apps
## <a name="lab-how-to-build-a-canvas-app"></a>Lab: Eine Canvas-App erstellen

# <a name="scenario"></a>Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Derzeit nutzt die Campusverwaltung eine Excel-Kalkulationstabelle, um die Besucherregistrierung nachzuverfolgen. Sie möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

# <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Wir werden uns beim Entwerfen der App an nachstehende Gliederung halten:

-   Erstellen einer Canvas-App aus Daten in der Tabelle „Besuch“

-   Konfigurieren, wie die Besuche im Bildschirm „Durchsuchen“ angezeigt werden

-   Vornehmen einiger einfacher Änderungen an der App

-   Testen der App-Funktionalität

## <a name="prerequisites"></a>Voraussetzungen

-   Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**

# <a name="exercise-1-create-visits-app"></a>Übung \#1: Erstellen der Besuche-App (Visits)

**Ziel**: In dieser Übung erstellen Sie eine Canvas-App, indem Sie Ihre Tabelle „Visits Initials“ (Besucherinitialen) verbinden, die Sie zuvor erstellt haben.

## <a name="task-1-create-a-visits-app"></a>Aufgabe \#1: Erstellen einer Besuche-App (Visits)

1.  Navigieren Sie zu <https://make.powerapps.com>. Möglicherweise müssen Sie sich erneut authentifizieren. Klicken Sie dazu auf **Anmelden**, und folgen Sie den Anweisungen (falls erforderlich).

2.  Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung** sumgebung aus, falls diese noch nicht ausgewählt ist.

3.  Klicken Sie, falls erforderlich, auf das **Startseitensymbol** auf der linken Seite des Bildschirms. Wählen Sie im Abschnitt **Beginnen mit** die Option **Dataverse** aus.

4.  Wählen Sie Ihre Dataverse-Verbindung aus. 

    >   **HINWEIS:** *Wenn es keine Dataverse-Verbindung gibt:*
    >   -   Wählen Sie **Neue Verbindung** aus.
    >   -   Suchen Sie **Microsoft Dataverse**.
    >   -   Klicken Sie auf **Erstellen**

5.  Suchen Sie die Tabelle **Besuche**, die Sie im vorherigen Lab erstellt haben, und wählen Sie sie aus.

6.  Wählen Sie in der rechten unteren Ecke die Schaltfläche **Verbinden** aus.

7.  Nachdem Ihre App erstellt wurde, aktivieren Sie auf dem Bildschirm „Willkommen bei Power Apps Studio“ das Kontrollkästchen **Nicht mehr anzeigen**, und wählen Sie dann **Überspringen** aus.

8.  Nach Abschluss der Erstellung sollte es wie die Abbildung unten aussehen.

![Aus „Besuch“-Daten erstellte Canvas-App.](media/2-canvas-app-from-data.png)

9. Wählen Sie im App-Designer auf der Befehlsleiste die Schaltfläche **Vorschau Ihrer App** (Symbol „Wiedergeben“) aus. *(Sie können auch eine Vorschau der App anzeigen, indem Sie F5 auf Ihrer Tastatur drücken.)* Sehen Sie sich an, wie die App im Auslieferungszustand aussieht.

10. Schließen Sie die App-Vorschau, indem Sie rechts oben auf dem Bildschirm das **X** auswählen.

Glückwunsch, Sie haben erfolgreich eine Power App aus einer Dataverse-Tabelle erstellt. Der nächste Schritt im Prozess besteht darin, die App an das Branding Ihres Colleges anzupassen. Die nächste Reihe von Schritten führt Sie durch die Bereitstellung zusätzlicher Anpassungen an der App.

## <a name="task-2-modify-and-theme-the-newly-created-app"></a>Aufgabe \#2: Ändern der neu erstellten App, inklusive Design

In dieser Aufgabe passen Sie den Kopfzeilentext für jeden der drei Bildschirme Ihrer App an (Durchsuchen, Details und Bearbeiten) und ändern das App-Design.

1.  Sie befinden sich auf dem Bildschirm „Durchsuchen“. Wählen Sie die Bezeichnung **Besuche** auf dem Bildschirm aus.

3.  Aktualisieren Sie auf der rechten Seite des Bildschirms unter der Registerkarte „Eigenschaften“ die **Text**-Steuerelementeigenschaft zu **„Bellows College Visits“** (Bellows College-Besuche).

4. Ändern Sie in den Eigenschaften den **Schriftgrad** auf **24**.

4.  Klicken Sie auf den leeren Hintergrund, um den aktualisierten Text auf dem Bildschirm „Durchsuchen“ anzuzeigen.

5.  Wählen Sie links im Navigationsbereich die Option **DetailScreen1** aus.

5.  Wählen Sie die Bezeichnung **Besuche** auf dem Bildschirm aus.

6.  Aktualisieren Sie auf der rechten Seite des Bildschirms unter der Registerkarte „Eigenschaften“ die **Text**-Steuerelementeigenschaft zu **„Besuchsdetails“** .

7.  Klicken Sie auf den leeren Hintergrund, um den aktualisierten Text auf dem Bildschirm „Details“ anzuzeigen.

8.  Wählen Sie mithilfe der Navigation auf der linken Seite **EditScreen1** aus (möglicherweise müssen Sie nach unten scrollen, um die Option in der Strukturansicht anzuzeigen).

9.  Wählen Sie die Bezeichnung **Besuche** auf dem Bildschirm aus.

10.  Ersetzen Sie auf der rechten Seite des Bildschirms unter der Registerkarte „Eigenschaften“ den Text „Table1“ in der **Text**-Steuerelementeigenschaft durch **„Details bearbeiten“** .

11.  Klicken Sie auf den leeren Hintergrund, um den aktualisierten Text auf dem Bildschirm „Bearbeiten“ anzuzeigen.

12. Wählen Sie links im Navigationsbereich die Option **BrowseScreen1** aus.

13. Wählen Sie auf der Befehlssymbolleiste die Schaltfläche **Design** aus und dann aus der angezeigten Liste die Designfarbe **Rot**.

## <a name="task-3-test-your-visits-app"></a>Aufgabe \#3: Testen Ihrer Besuche-App (Visits)

In dieser Aufgabe testen Sie Ihre neue App.

1.  Wählen Sie bei im App-Designer geöffneter Anwendung **Datei** aus, aktualisieren Sie den Namen Ihrer App auf **Besuche-App** (Visits-App), und wählen Sie **Speichern** aus.

2.  Wählen Sie den Pfeil **Zurück** aus, um zur App zurückzukehren.

3.  Wählen Sie links im Navigationsbereich die Option **BrowseScreen1** aus.

4.  Wählen Sie im App-Designer auf der Befehlsleiste die Schaltfläche **Vorschau Ihrer App** (Symbol „Wiedergeben“) aus. *(Sie können auch eine Vorschau der App anzeigen, indem Sie F5 auf Ihrer Tastatur drücken.)*

4.  Nachdem die App geöffnet wurde, geben Sie in das Feld **Suchelemente** den Text **Maria** ein.
     *(Beachten Sie, wie die Elemente im Katalog gefiltert werden, basierend auf der Eingabe im Suchfeld.)*

5.  Wenn der Datensatz **Contoso Suites** für **Maria Campbell** angezeigt wird, klicken Sie auf die Zeile, um die Details für diesen Besuch zu öffnen. (**Hinweis**: *Wenn mehrere Contoso Suites-Datensätze für Maria Campbell angezeigt werden, wählen Sie einen beliebigen aus.* )

6.  Um den Datensatz zu bearbeiten, wählen Sie das **Bleistiftsymbol** oben rechts in der App aus.

7.  Sie können den Namen des Besuchs hier bearbeiten. Klicken Sie rechts oben auf das Häkchensymbol, um Ihre Änderungen zu speichern.

8.  Klicken Sie rechts oben auf dem Bildschirm auf das **X**, um zum Canvas-App-Editor zurückzukehren.

Herzlichen Glückwunsch! Sie haben Ihre erste Canvas-App erstellt und konfiguriert.

# <a name="challenges"></a>Herausforderungen

-   Fügen Sie den Formularen in „DetailScreen1“ und „EditScreen1“ die folgenden Spalten hinzu: Tatsächlicher Start, Tatsächliches Ende, Code, Geplanter Start und Geplantes Ende.
