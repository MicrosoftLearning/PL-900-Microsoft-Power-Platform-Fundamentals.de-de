---
lab:
  title: "Lab\_2: Eine Canvas-App erstellen"
  module: 'Module 3: Get started with Power Apps'
---

# Lab 2: Eine Canvas-App erstellen

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Mandant ist ein Testmandant; er kann nach Abschluss des Kurses nicht verwendet oder erreicht werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Derzeit nutzt die Campusverwaltung eine Excel-Kalkulationstabelle, um die Besucherregistrierung nachzuverfolgen. Sie möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.


## Weiterführende Schritte des Lab

Wir werden uns beim Entwerfen der App an nachstehende Gliederung halten:

- Erstellen einer Canvas-App aus Daten in der Tabelle „Besuch“

- Konfigurieren, wie die Besuche im Bildschirm „Durchsuchen“ angezeigt werden

- Vornehmen einiger einfacher Änderungen an der App

- Testen der App-Funktionalität

## Voraussetzungen

- Beendigung von **Modul 1 Lab 0 – Lab-Umgebung überprüfen**
- Abschluss von **Modul 2 Lab 1: Datenmodellierung**


## Übung 1: Erstellen einer Canvas-App für Besuche

**Ziel:** In dieser Übung erstellen Sie eine Canvas-App, indem Sie die Tabelle „Visits“ (Besuche) verbinden, die Sie zuvor erstellt haben.


### Aufgabe \#1: Erstellen der „Visits“-App

1.  Navigieren Sie zu `https://make.powerapps.com`.

2.  Möglicherweise müssen Sie sich erneut authentifizieren. Wählen Sie dazu **Anmelden** aus, und befolgen Sie die Anweisungen, falls erforderlich.

3.  Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

4.  Wählen Sie **+ Erstellen** im linken Navigationsbereich des Bildschirms aus. Wählen Sie im Abschnitt **Beginnen mit** die Option **Dataverse** aus.

5.  Wählen Sie Ihre Dataverse-Verbindung aus.

    > **Hinweis:**  *Tun Sie Folgendes, falls keine Dataverse-Verbindung vorhanden ist:*
    > - Wählen Sie **+ Neue Verbindung** aus.
    > - Suchen Sie **Microsoft Dataverse**.
    > - Klicken Sie auf **Erstellen**
    > - **Melden Sie sich an**, und wählen Sie **Zugriff zulassen** aus.

6.  Suchen Sie die Tabelle **Besuche**, die Sie im vorherigen Lab erstellt haben, und wählen Sie sie aus.

7.  Wählen Sie in der rechten unteren Ecke die Schaltfläche **Verbinden** aus.

8.  Nachdem Ihre App erstellt wurde, aktivieren Sie auf dem Bildschirm „Willkommen bei Power Apps Studio“ **Nicht mehr anzeigen**, und wählen Sie dann **Überspringen** aus.

9.  Nach Abschluss der Erstellung sollte die Canvas-App wie die Abbildung unten aussehen:

    ![Aus „Besuch“-Daten erstellte Canvas-App.](media/2-canvas-app-from-data.png)

10.  Wählen Sie im App-Designer auf der Befehlsleiste die Schaltfläche **Vorschau der App** (Symbol „Wiedergeben“) aus. *(Sie können auch eine Vorschau der App anzeigen, indem Sie F5 drücken.)* Sehen Sie sich an, wie Ihre App nach der Installation aussieht.

11. Schließen Sie die App-Vorschau, indem Sie rechts oben auf dem Bildschirm das **X** auswählen.

Glückwunsch, Sie haben erfolgreich eine Power App aus einer Dataverse-Tabelle erstellt. Im nächsten Schritt möchten Sie die App an das Branding von Bellows College anpassen. Die nächste Reihe von Schritten führt Sie durch die Bereitstellung zusätzlicher Anpassungen an der App.


### Aufgabe \#2: Ändern der neu erstellten App, inklusive Design

In dieser Aufgabe passen Sie den Kopfzeilentext für jeden der drei Bildschirme Ihrer App an (Durchsuchen, Details und Bearbeiten) und ändern das App-Design. 

1.  Sie befinden sich auf dem Bildschirm „Durchsuchen“. Wählen Sie die Bezeichnung **Besuche** auf dem Bildschirm aus.

1.  Aktualisieren Sie auf der rechten Seite des Bildschirms auf der Registerkarte „Eigenschaften“ die **Text**-Steuerelementeigenschaft zu `Bellows College Visits`.

1.  Ändern Sie auf der Registerkarte **Eigenschaften** den **Schriftgrad** in **24**. 

1.  Wählen Sie den leeren Bildschirmhintergrund aus, um den aktualisierten Text auf dem Bildschirm „Durchsuchen“ anzuzeigen. 

1.  Wählen Sie über die **Strukturansicht** in der linken Navigationsleiste **DetailScreen1** aus. 

1.  Wählen Sie die Bezeichnung **Besuche** auf dem Bildschirm aus.

1.  Aktualisieren Sie auf der rechten Seite des Bildschirms auf der Registerkarte **Eigenschaften** die **Text**-Steuerelementeigenschaft in `Visit Details`.

1.  Klicken Sie auf den leeren Bildschirmhintergrund, um den aktualisierten Text auf dem Bildschirm „Details “ anzuzeigen.

1.  Wählen Sie mithilfe der **Strukturansicht** in der linken Navigationsleiste **EditScreen1** aus (möglicherweise müssen Sie nach unten scrollen, um die Option in der Strukturansicht anzuzeigen).

1.  Wählen Sie die Bezeichnung **Besuche** auf dem Bildschirm aus.

1.  Ersetzen Sie auf der rechten Seite des Bildschirms auf der Registerkarte **Eigenschaften** den Text in der **Text**-Steuerelementeigenschaft durch `Edit Details`.

1.  Klicken Sie auf den leeren Bildschirmhintergrund, um den aktualisierten Text auf dem Bildschirm „Bearbeiten“ anzuzeigen.

1.  Wählen Sie über die **Strukturansicht** in der linken Navigationsleiste **BrowseScreen1** aus.

1.  Wählen Sie auf der Befehlssymbolleiste die Schaltfläche **Design** aus und dann aus der angezeigten Liste die Designfarbe **Rot**.


### Aufgabe \#3: Testen Ihrer Besuche-App (Visits)

In dieser Aufgabe testen Sie Ihre neue App.

1.  Wenn Ihre Anwendung im App-Designer geöffnet ist, wählen Sie **Einstellungen** aus, aktualisieren Sie im Abschnitt **Allgemein** den Namen Ihrer App in `Visits App`, klicken Sie auf das **X**, um den Einstellungsbildschirm zu schließen, und dann auf **Speichern**.

2.  Wählen Sie links im Navigationsbereich die Option **BrowseScreen1** aus.

3.  Wählen Sie im App-Designer auf der Befehlsleiste die Schaltfläche **Vorschau der App** (Symbol „Wiedergeben“) aus. *(Sie können auch eine Vorschau der App anzeigen, indem Sie F5 drücken.)*

4.  Nachdem die App geöffnet wurde, geben Sie in das Feld **Suchelemente** den Text `Maria`
    * ein. (Beachten Sie, wie die Elemente im Katalog anhand der Eingabe im Suchfeld gefiltert werden).*

5.  Wenn der Datensatz **Contoso Suites** für **Maria Campbell** angezeigt wird, klicken Sie auf die Zeile, und öffnen Sie Details für diesen Besuch. (**Hinweis**: *Wenn mehrere Contoso Suites-Datensätze für Maria Campbell angezeigt werden, wählen Sie einen beliebigen aus.* )

6.  Um den Datensatz zu bearbeiten, wählen Sie das **Bleistiftsymbol** oben rechts in der App aus.

7.  Sie können den **Namen des Besuchs** hier bearbeiten. Klicken Sie rechts oben auf das **Häkchensymbol**, um Ihre Änderungen zu speichern.

8.  Klicken Sie rechts oben auf dem Bildschirm auf das **X**, um den Vorschaumodus zu schließen und zum Canvas-App-Editor zurückzukehren.

Herzlichen Glückwunsch! Sie haben Ihre erste Canvas-App erstellt und konfiguriert.

