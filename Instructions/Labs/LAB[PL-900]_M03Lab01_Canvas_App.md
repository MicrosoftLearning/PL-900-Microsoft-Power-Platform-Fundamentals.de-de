---
lab:
  title: "Lab\_2: Eine Canvas-App erstellen"
  module: 'Module 3: Get started with Power Apps'
---

# Lab 2: Eine Canvas-App erstellen

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Tenant ist ein Testtenant; er kann nach Abschluss des Kurses nicht verwendet oder aufgerufen werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Campusgebäuden. Viele der Lehrer und Administratoren am Bellow College müssen an Veranstaltungen teilnehmen und Artikel kaufen. Historisch gesehen war die Nachverfolgung dieser Ausgaben eine Herausforderung. 

Die Campusverwaltung möchte ihr Spesenabrechnungssystem modernisieren, indem den Mitarbeitern eine digitale Möglichkeit zum Melden von Ausgaben an die Hand gegeben wird. 

Während dieses Kurses erstellen Sie Anwendungen und führen Automatisierung durch, damit die Mitarbeitenden des Bellows College Ausgaben verwalten können. 


## Weiterführende Schritte des Lab

Wir werden uns beim Entwerfen der App an nachstehende Gliederung halten:

- Erstellen einer Canvas-App für Spesenabrechnungen 

- Konfigurieren, wie Spesenabrechnungen auf dem Suchbildschirm angezeigt werden

- Vornehmen einiger einfacher Änderungen an der App

- Testen der App-Funktionalität

## Voraussetzungen

- Beendigung von **Modul 1 Lab 0 – Lab-Umgebung überprüfen**

## Übung 1: Erstellen einer Canvas-Anwendung für Spesenabrechnungen

### Zielsetzung: In dieser Übung erstellen Sie eine Canvas-App, indem Sie eine Verbindung mit einer Tabelle „Expense Reports“ herstellen.

### Aufgabe Nr. 1: Erstellen der Spesenabrechnungs-App

1. Navigieren Sie zu https://make.powerapps.com.

1. Möglicherweise müssen Sie sich erneut authentifizieren. Wählen Sie dazu **Anmelden** aus, und befolgen Sie die Anweisungen, falls erforderlich.

1. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

1. Wählen Sie **+ Erstellen** im linken Navigationsbereich des Bildschirms aus. Wählen Sie im Abschnitt **Beginnen mit** die Option **Dataverse** aus.

1. Wählen Sie Ihre Dataverse-Verbindung aus.

    >**Hinweis:** Wenn es keine Dataverse-Verbindung gibt:

    >   - Wählen Sie **+ Neue Verbindung** aus.

    >   - Suchen Sie **Microsoft Dataverse**.

    >   - Klicken Sie auf **Erstellen**

    >   - **Melden Sie sich an**, und wählen Sie **Zugriff zulassen** aus.

1. Suchen und wählen Sie die Tabelle **Spesenabrechnungen** aus.

1. Wählen Sie in der rechten unteren Ecke die Schaltfläche **Verbinden** aus.

1. Nachdem Ihre App erstellt wurde, aktivieren Sie auf dem Bildschirm „Willkommen bei Power Apps Studio“ **Nicht mehr anzeigen**, und wählen Sie dann **Überspringen** aus.

1. Wählen Sie im App-Designer auf der Befehlsleiste die Schaltfläche **Vorschau der App** (Symbol „Wiedergeben“) aus. (Sie können auch eine Vorschau der App anzeigen, indem Sie F5 drücken.) Sehen Sie sich an, wie Ihre App nach der Installation aussieht.

1. Schließen Sie die App-Vorschau, indem Sie rechts oben auf dem Bildschirm das **X** auswählen.

Glückwunsch, Sie haben erfolgreich eine Power App aus einer Dataverse-Tabelle erstellt. Der nächste Schritt im Prozess ist die Anpassung der Anwendung an das Branding Ihres Organisation. Die nächste Reihe von Schritten führt Sie durch die Bereitstellung zusätzlicher Anpassungen an der App.

### Aufgabe #2: Ändern und Gestalten der neu erstellten App

In dieser Aufgabe passen Sie den Kopfzeilentext für jeden der drei Bildschirme Ihrer App an (Durchsuchen, Details und Bearbeiten) und ändern das App-Design.

1. Sie befinden sich auf dem Bildschirm „Durchsuchen“. Wählen Sie die Bezeichnung **Spesenabrechnungen** auf dem Bildschirm aus.

1. Aktualisieren Sie auf der rechten Seite des Bildschirms auf der Registerkarte Eigenschaften die Eigenschaft des Steuerelements **Text** auf „Meine Ausgabenberichte“

1. Ändern Sie auf der Registerkarte **Eigenschaften** den **Schriftgrad** in **24**.

1. Wählen Sie den leeren Bildschirmhintergrund aus, um den aktualisierten Text auf dem Bildschirm „Durchsuchen“ anzuzeigen.

1. Wählen Sie über die **Strukturansicht** in der linken Navigationsleiste **DetailScreen1** aus.

1. Wählen Sie die Bezeichnung **Spesenabrechnungen** auf dem Bildschirm aus.

1. Aktualisieren Sie auf der rechten Seite des Bildschirms auf der Registerkarte **Eigenschaften** die Eigenschaft des Steuerelements **Text** auf „Berichtsdetails“

1. Klicken Sie auf den leeren Bildschirmhintergrund, um den aktualisierten Text auf dem Bildschirm „Details “ anzuzeigen.

1. Wählen Sie mithilfe der **Strukturansicht** in der linken Navigationsleiste **EditScreen1** aus (möglicherweise müssen Sie nach unten scrollen, um die Option in der Strukturansicht anzuzeigen).

1. Wählen Sie die Bezeichnung **Spesenabrechnungen** auf dem Bildschirm aus.

1. Ersetzen Sie auf der rechten Seite des Bildschirms auf der Registerkarte **Eigenschaften** den Text in der Eigenschaft des Steuerelements **Text** durch „Details bearbeiten“

1. Klicken Sie auf den leeren Bildschirmhintergrund, um den aktualisierten Text auf dem Bildschirm „Bearbeiten“ anzuzeigen.

1. Wählen Sie über die **Strukturansicht** in der linken Navigationsleiste **BrowseScreen1** aus.

1. Wählen Sie auf der Befehlssymbolleiste die Schaltfläche **Design** aus und dann aus der angezeigten Liste die Designfarbe **Rot**.

### Aufgabe 3: Testen Ihrer Spesenabrechnungs-App

In dieser Aufgabe testen Sie Ihre neue App.

1. Wenn Ihre Anwendung im App-Designer geöffnet ist, wählen Sie **Einstellungen** aus (Möglicherweise müssen Sie wählen ... damit das Einstellungssymbol angezeigt wird), aktualisieren Sie im Abschnitt **Allgemein** den Namen Ihrer Anwendung auf „Expense Report App“, wählen Sie das **X**, um den Einstellungsbildschirm zu schließen und wählen Sie dann **Speichern**.

1. Wählen Sie links im Navigationsbereich die Option **BrowseScreen1** aus.

1. Wählen Sie im App-Designer auf der Befehlsleiste die Schaltfläche **Vorschau der App** (Symbol „Wiedergeben“) aus. (Sie können auch eine Vorschau der App anzeigen, indem Sie F5 drücken.)

1. Sobald die App geöffnet ist, geben Sie in das Feld **Elemente suchen** den Text Trip ein (Beachten Sie, dass die Elemente in der Galerie nach dem gefiltert werden, was in das Suchfeld eingegeben wird).

1. Sobald der Datensatz **Reise zur Power Platform-Konferenz** angezeigt wird, wählen Sie eine Zeile aus, um zu navigieren und den Bildschirm „Details“ für diese Spesen zu öffnen.
 
    >**Hinweis:** Wenn mehr als ein Eintrag für die Reise zur Power Platform-Konferenz angezeigt wird, wählen Sie einen davon aus.

1. Um den Datensatz zu bearbeiten, wählen Sie das **Bleistiftsymbol** oben rechts in der App aus.

1. Sie können den **Berichtsnamen** hier bearbeiten und das **Häkchensymbol** oben rechts auswählen, um die Änderung zu speichern.

1. Klicken Sie rechts oben auf dem Bildschirm auf das **X**, um den Vorschaumodus zu schließen und zum Canvas-App-Editor zurückzukehren.

Herzlichen Glückwunsch! Sie haben Ihre erste Canvas-App erstellt und konfiguriert.

 
