---
lab:
  title: "Lab\_3: So erstellen Sie eine modellgesteuerte App"
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Lab 3: So erstellen Sie eine modellgesteuerte App

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Tenant ist ein Testtenant; er kann nach Abschluss des Kurses nicht verwendet oder aufgerufen werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Campusgebäuden. Viele der Lehrer und Administratoren am Bellow College müssen an Veranstaltungen teilnehmen und Artikel kaufen. Historisch gesehen war die Nachverfolgung dieser Ausgaben eine Herausforderung.

Die Campusverwaltung möchte ihr Spesenabrechnungssystem modernisieren, indem den Mitarbeitern eine digitale Möglichkeit zum Melden von Ausgaben an die Hand gegeben wird.

Während dieses Kurses erstellen Sie Anwendungen und führen Automatisierung durch, damit die Mitarbeitenden des Bellows College Ausgaben verwalten können.

## Weiterführende Schritte des Lab

Im Rahmen der Erstellung der modellgesteuerten App führen Sie Folgendes aus:

- Erstellen Sie eine neue modellgesteuerte App mit dem Namen Ausgabenverwaltung einer mitarbeitenden Person.

- Bearbeiten der App-Navigation, um auf die erforderlichen Tabellen zu verweisen.

- Anpassen der Formulare und Ansichten der erforderlichen Tabellen für die App.

Wir werden mit folgenden Komponenten arbeiten:

- **Ansichten**: Mithilfe von Ansichten kann der Benutzer die vorhandenen Daten in Form einer Tabelle anzeigen.

- **Formulare**: Hier erstellt bzw. aktualisiert der Benutzer neue Zeilen in den Tabellen.

Beide werden für eine bessere Benutzererfahrung in die modellgesteuerte App integriert.

### Voraussetzungen

- Beendigung von **Modul 1 Lab 0 – Lab-Umgebung überprüfen**

**Bevor Sie beginnen, sollten Sie Folgendes berücksichtigen**

- Welche Änderungen sollten wir vornehmen, um die Benutzererfahrung zu verbessern?

- Was sollten wir auf der Grundlage des von uns erstellten Datenmodells in eine modellgesteuerte App aufnehmen?

- Welche Anpassungen können an der Seitenübersicht einer modellgesteuerten App vorgenommen werden?

## Übung 1: Ansichten und Formulare anpassen

**Ziel**: In dieser Übung passen Sie Ansichten und Formulare der benutzerdefinierten erstellten Tabellen an, die in der modellgesteuerten App verwendet werden.

### Aufgabe Nr. 1: Bearbeiten des Spesenabrechnungsformulars

1. Wenn Sie noch nicht angemeldet sind, melden Sie sich bei https://make.powerapps.com an.

1. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

1. Wählen Sie im linken Navigationsbereich **Tabellen** aus, und öffnen Sie die Tabelle **Expense Report** (Spesenabrechnung).

    >Wenn die Tabelle „Expense Report“ bzw. „Spesenabrechnung“ nicht angezeigt wird, stellen Sie sicher, dass Sie die richtige Umgebung ausgewählt haben (Schritt 2).

1. Wählen Sie im Abschnitt **Datenfunktionen** die Option **Formulare** aus, und öffnen Sie das Formular **Informationen** mit dem Formulartyp **Main** (Haupt). (**Wichtig:** Stellen Sie sicher, dass Sie das Formular mit dem Formulartyp **Main** (Haupt) auswählen.)

    >**WICHTIG:** Da alle Formulare standardmäßig „Information“ heißen, müssen Sie unbedingt überprüfen, ob das von Ihnen ausgewählte Formular den Formulartyp **Haupt** hat, und nicht einen anderen. Standardmäßig hat das Formular zwei Felder: „Name“ und „Besitzer“.

1. Wählen Sie auf der rechten Seite des Bildschirms im Bereich **Eigenschaften** das Feld **Anzeigename** aus und ändern Sie es in `Report Information`.

1. Wählen Sie **Tabellenspalten** im linken Navigationsbereich aus, und fügen Sie die folgenden Felder unter dem Feld **Owner** (Besitzer) hinzu, indem Sie Spalten in das Formular ziehen oder einfach auf die Spaltennamen klicken:

    - **Beschreibung**

    - **Berichtszweck**

    - **Berichtsfälligkeitsdatum**

    - **Gesamtbetrag des Berichts**

1. Ziehen Sie die Spalte **Statusgrund**, und legen Sie sie auf der Kopfzeile des Formulars ab.

    >Die Kopfzeile ist der obere rechte Bereich des Formulars. Möglicherweise müssen Sie das Eigenschaftenpanel auf der rechten Seite des Bildschirms zuklappen, um das Feld im Formular anzuzeigen.

1. Wählen Sie das Feld **Besitzer** aus. Ändern Sie auf dem Eigenschaftspanel die **Bezeichnung** in `Requestor`.

1. Wählen Sie oben rechts **Speichern und Veröffentlichen** aus, und warten Sie, bis der Speicher- und Veröffentlichungsvorgang abgeschlossen ist.

1. Wenn die Bearbeitungsansicht auf einer neuen Browserregisterkarte oder in einem neuen Fenster geöffnet wurde, schließen Sie sie. Wählen Sie andernfalls oben links im Bildschirm **🡠 Zurück** aus. Sie sollten sich nun wieder im Formular für die Tabelle **Expense Report** (Spesenabrechnung) befinden.

1. Sie verwenden die Breadcrumbs oben links (**Tabellen** > **Expense Report (Spesenabrechnung)** > **Formulare**). Wählen Sie **Spesenabrechnung** aus, um zum Eigenschaftendialogfeld der Tabelle **Spesenabrechnung** zurückzukehren.

## Aufgabe Nr. 2: Bearbeiten der Ansicht „Inaktive Spesenabrechnungen“

In dieser Aufgabe ändern wir die Standardansicht „Aktive Spesenabrechnungen“ und erstellen eine neue Ansicht für die heute fälligen Spesenabrechnungen.

1. Wählen Sie im Abschnitt **Datenfunktionen** die Option **Ansichten** aus, und öffnen Sie die Ansicht **Active Expense Reports** (Aktive Spesenabrechnungen).

1. Fügen Sie der Ansicht die folgenden Felder hinzu, indem Sie entweder auf die Felder klicken oder sie ziehen und ablegen:

    - **Berichtszweck**

    - **Berichtsfälligkeitsdatum**

    - **Gesamtbetrag des Berichts**

1. Wählen Sie das Dropdownmenü in der Spalte **Erstellt am** und dann **Entfernen** aus. Das Feld **Erstellt am** wird nun aus der Ansicht entfernt.

1. Passen Sie die Größe der einzelnen Spaltenbreiten an die Daten an.

1. Wählen Sie unter **Sortieren nach …** Wählen Sie das X, um **Berichtsname** zu entfernen, und wählen Sie stattdessen **Berichtsgesamtbetrag**.

1. Wählen Sie **Berichtsgesamtbetrag** aus, um die Sortierreihenfolge in **Absteigend** zu ändern.

1. Wählen Sie oben rechts **Speichern und Veröffentlichen** aus, und warten Sie, bis der Veröffentlichungsvorgang abgeschlossen wurde.

### Aufgabe 3: Erstellen einer neuen Ansicht für heute fällige Berichte

Jetzt werden wir die Ansicht klonen, um eine neue Ansicht für die heute fälligen Berichte zu erstellen.

>    **WICHTIG:** Stellen Sie sicher, dass Sie die Ansicht „Active Expense Reports“ (Aktive Spesenabrechnungen) nicht schließen, da wir sie nutzen werden, um die neue Ansicht der heute fälligen Berichte zu erstellen.

1. Wählen Sie **Speichern unter** aus.

1. Ändern Sie den **Status** in `Expense Reports Due Today`, und wählen Sie **Speichern** aus.

1. Wählen Sie **Filter bearbeiten** im Eigenschaftenpanel aus.

1. Klicken Sie auf **+ Hinzufügen**, und wählen Sie **Zeile hinzufügen** aus.

1. Wählen Sie **Berichtsfälligkeitsdatum** als Feld aus, und ändern Sie dann die Bedingung **Ist gleich** in der Dropdownliste in **Heute**.

1. Wählen Sie **...** **Weitere Befehle** in der Zeile **Status** und dann **Löschen** aus, um diese Filterbedingung zu löschen.

1. Wählen Sie **OK** aus, um die Bedingung zu speichern. Die Ansicht wird jetzt gefiltert, sodass nur Datensätze angezeigt werden, bei denen das **Berichtsfälligkeitsdatum** heute ist.

1. Fügen Sie der Ansicht das Feld **Erstattungsbetrag** hinzu.

1. Wählen Sie oben rechts **Speichern und Veröffentlichen** aus, und warten Sie, bis der Veröffentlichungsvorgang abgeschlossen wurde.

## Übung 2: Erstellen einer modellgesteuerten App

**Ziel**: In dieser Übung erstellen Sie eine modellgesteuerte App, passen die Siteübersicht an und testen die App.

Der Einfachheit halber und aus Zeitgründen gehen wir in diesem Lab nicht auf alle Spalten der Spesenabrechnung ein.

### Aufgabe 1: Erstellen der App

1. Wenn Sie noch nicht angemeldet sind, melden Sie sich bei https://make.powerapps.com an.

1. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

1. Wählen Sie links in der Navigation **Lösungen** aus.

1. Öffnen Sie Lösung **Ausgabenverwaltung** .

1. Wählen Sie **+Neu**, wählen Sie **APP** und wählen Sie dann **Modellgesteuerte App**.

1. Geben Sie `Employee Expense Management` als **Name** ein, und wählen Sie **Erstellen** aus.

1. Nachdem Ihre neue modellgesteuerte Anwendung geladen wurde, wählen Sie die Schaltfläche **+ Seite hinzufügen** aus.

1. Auf dem Bildschirm **Seite hinzufügen** wählen Sie **Dataverse-Tabelle**.

1. Wählen Sie die folgenden Tabellen aus:

    - Spesenabrechnung

    - Contact

1. Wenn Sie über beide Tabellen verfügen, wählen Sie **Hinzufügen** aus.

1. Wählen Sie mithilfe der Navigationssymbole auf der linken Seite des Bildschirms **Navigation** aus.

1. Wählen Sie im Navigationsbereich unterhalb der Bezeichnung „Navigation“ die Option **Neue Gruppe** aus. Möglicherweise müssen Sie das Menü links erweitern.

1. Auf der rechten Seite des Bildschirms, im Abschnitt **Anzeigeoptionen**, ändern Sie die Eigenschaft **Titel** in `Reports`.

1. Klicken Sie auf **Speichern**, und warten Sie, bis die Änderungen gespeichert sind.

1. Nachdem der **Speicher**vorgang abgeschlossen wurde, wählen Sie die Schaltfläche **Veröffentlichen** aus, um Ihre Änderungen zu veröffentlichen. Warten Sie darauf, bis die Veröffentlichung abgeschlossen ist.

## Aufgabe 2: Testen der App

**Starten der Anwendung**

1. Wählen Sie die Schaltfläche **Wiedergeben** aus. Die modellgesteuerte App wird auf einer neuen Registerkarte geladen.

**Erstellen eines neuen Kontakts**

1. Die App sollte in der Ansicht **Meine aktiven Kontakte** geöffnet werden. Wenn dies nicht der Fall ist, wählen Sie in der Navigationsleiste links **Kontakte** aus.

1. Wählen Sie in der Befehlsleiste **+ Neu** aus.

1. Geben Sie als **Vorname** „`John`“ und als **Nachname** „`Doe`“ ein.

1. Geben Sie unter **E-Mail** Ihre persönliche E-Mail-Adresse an. Sie wird in einem zukünftigen Lab verwendet, in dem Sie eine E-Mail erhalten.

1. Wählen Sie **Speichern &amp; Schließen**.

1. Sie sollten nun den erstellten Kontakt in der Ansicht **Meine aktiven Kontakte** sehen.

**Erstellen einer neuen Spesenabrechnung**

1. Wählen Sie in der linken Navigationsleiste (auch „Siteübersicht“ genannt) **Expense Reports** (Spesenabrechnungen) aus.

1. Wählen Sie **+ Neu** aus.

1. Füllen Sie die Felder wie folgt aus:

    - **Berichtsname**: `New Test Report`

    - **Berichtszweck**: Wählen Sie **Konferenz** aus.

    - **Berichtsfälligkeitsdatum**: Wählen Sie das heutige Datum aus.

1. Wählen Sie **Speichern &amp; Schließen**. Dadurch wird der neue Testbericht erstellt, und Sie sollten ihn in der Ansicht **Aktive Spesenabrechnungen** anzeigen können.

1. Ändern Sie die Ansicht in **Heute fällige Spesenabrechnungen** über die Dropdownliste neben **Aktive Spesenabrechnungen**. 

1. Sie können weitere Testdatensätze hinzufügen.

Ihre modellgesteuerte App sollte ungefähr folgendermaßen aussehen:

![Screenshot der gerade erstellten modellgesteuerte App.](media/lab-3-create-a-model-app-01.png)

Herzlichen Glückwunsch! Sie haben Ihre erste modellgesteuerte App erstellt und konfiguriert.
