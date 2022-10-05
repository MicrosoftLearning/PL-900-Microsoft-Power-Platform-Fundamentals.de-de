---
lab:
  title: "Lab\_3: So erstellen Sie eine modellgesteuerte App"
  module: 'Module 3: Get started with Power Apps'
---

# <a name="lab-3-how-to-build-a-model-driven-app"></a>Lab 3: So erstellen Sie eine modellgesteuerte App

## <a name="scenario"></a>Szenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab erstellen Sie eine modellgesteuerte Power Apps-App, mit der die Campus-Mitarbeiter im Backoffice die Besuchsdatensätze für den gesamten Campus verwalten können.

Weiterführende Schritte des Lab

Im Rahmen der Erstellung der modellgesteuerten App führen Sie Folgendes aus:

- Das Erstellen einer neuen modellgesteuerten App mit dem Namen „Campus Management“

- Bearbeiten der App-Navigation, um auf die erforderlichen Tabellen zu verweisen

- Anpassen der Formulare und Ansichten der erforderlichen Tabellen für die App

Wir werden mit folgenden Komponenten arbeiten:

- **Ansichten**: Mithilfe von Ansichten kann der Benutzer die vorhandenen Daten in Form einer Tabelle anzeigen.

- **Formulare**: Hier erstellt bzw. aktualisiert der Benutzer neue Zeilen in den Tabellen.

Beide werden für eine bessere Benutzererfahrung in die modellgesteuerte App integriert.

Voraussetzungen

- Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**
- Abschluss von **Modul 2 Lab 1: Datenmodellierung**

Vor dem Beginn zu beachtende Dinge

- Welche Änderungen sollten wir vornehmen, um die Benutzererfahrung zu verbessern?
- Was sollten wir auf der Grundlage des von uns erstellten Datenmodells in eine modellgesteuerte App aufnehmen?
- Welche Anpassungen können an der Seitenübersicht einer modellgesteuerten App vorgenommen werden?

## <a name="exercise-1-customize-views-and-forms"></a>Übung 1: Ansichten und Formulare anpassen

**Ziel**: In dieser Übung passen Sie Ansichten und Formulare der benutzerdefinierten erstellten Tabellen an, die in der modellgesteuerten App verwendet werden.

### <a name="task-1-edit-visit-form"></a>Aufgabe 1: Formular „Besuch bearbeiten“

1. Melden Sie sich bei [https://make.powerapps.com](https://make.powerapps.com/) an (falls Sie nicht bereits angemeldet sind).

2. Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

3. Erweitern Sie im linken Navigationsbereich **Dataverse**, wählen Sie **Tabellen** aus, und klicken Sie auf Ihre Tabelle **Besuch**, um sie zu öffnen.

Wenn die Tabelle „Besuch“ nicht angezeigt wird, stellen Sie sicher, dass Sie sich in der richtigen Umgebung befinden (Schritt 2).

4. Wählen Sie im Abschnitt **Datenfunktionen** die Option **Formulare** aus, und klicken Sie, um das Formular „Informationen“ mit dem Formulartyp **Haupt** zu öffnen.

<bpt id="p1">**</bpt>IMPORTANT:<ept id="p1">**</ept> Since by default all forms are named Information, make sure to verify that the form you select has a Form Type of <bpt id="p2">**</bpt>Main<ept id="p2">**</ept> and not something else. By default, the form has two fields: Name and Owner.

5. Wählen Sie auf der rechten Seite des Bildschirms im Eigenschaftenpanel das Feld **Anzeigename** aus, und ändern Sie es in **Hauptinformation**.

6. Wählen Sie über das Menü am oberen Bildschirmrand **+ Formularfeld** aus, und fügen Sie unter dem Feld **Besitzer** die folgenden Felder hinzu, indem Sie Spalten in das Formular ziehen oder einfach auf Spaltennamen klicken:

    1. **Besucher**

    1. **Geplanter Start**

    1. **Geplantes Ende**

    1. **Actual Start (Tatsächlicher Start)**

    1. **Actual End (Tatsächliches Ende)**

7. Ziehen Sie die Spalte **Code**, und legen Sie sie im Formularkopf ab.

The header is the top right area of the form. You may need to collapse the Properties panel on the right side of the screen to see the field on the form.

8. Aktivieren Sie bei weiterhin ausgewähltem Feld **Code** das Kontrollkästchen für **Schreibgeschützt** im Eigenschaftenpanel auf der rechten Seite.

9. Select <bpt id="p1">**</bpt>Owner<ept id="p1">**</ept> field. In the Properties panel, change the <bpt id="p1">**</bpt>Label<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Host<ept id="p2">**</ept>

10. Klicken Sie oben rechts auf **Speichern**, und warten Sie, bis der Speichervorgang abgeschlossen ist.

11. Klicken Sie oben rechts auf **Veröffentlichen**, und warten Sie, bis die Veröffentlichung abgeschlossen ist.

12. Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus.

13. Campusbesucher werden derzeit auf Papier erfasst.

### <a name="task-2-edit-active-visits-view"></a>Aufgabe \#2: Bearbeiten der Ansicht „Aktive Besuche“

In dieser Aufgabe ändern wir die Standardansicht „Aktive Besuche“ und erstellen eine neue Ansicht für die heutigen Besuche.

1. Wählen Sie im Abschnitt **Datenfunktionen** die Option **Ansichten** aus, und klicken Sie, um die Ansicht **Aktive Besuche** zu öffnen.

2. Fügen Sie der Ansicht die folgenden Felder hinzu, indem Sie entweder auf die Felder klicken oder sie ziehen und ablegen:

    1. **Code**

    2. **Besucher**

    3. **Geplanter Start**

    4. **Geplantes Ende**

3. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

4. Passen Sie die Größe der einzelnen Spaltenbreiten an die Daten an.

5. Klicken Sie auf **Speichern** und warten Sie, bis die Änderungen gespeichert sind.

6. Klicken Sie auf **Veröffentlichen** und warten Sie, bis die Veröffentlichung abgeschlossen ist.

### <a name="task-3-create-new-view-for-todays-visits"></a>Aufgabe 3: Erstellen einer neuen Ansicht für heutige Besuche

Jetzt werden wir die Ansicht klonen, um eine neue Ansicht für die heutigen Besuche zu erstellen.

WICHTIG: Stellen Sie sicher, dass Sie die Ansicht „Aktive Besuche“ nicht schließen, da wir sie nutzen werden, um die neue Ansicht der heutigen Besuche zu erstellen.

1. Klicken Sie auf den **Dropdownpfeil** neben der Schaltfläche „Speichern“ (achten Sie darauf, dass Sie nicht auf die Schaltfläche selbst klicken), und wählen Sie **Speichern unter** aus.

2. Ändern Sie den Namen in **Heutige Besuche**, und wählen Sie **Speichern** aus.

3. Klicken Sie im Eigenschaftenpanel auf den Link **Filter bearbeiten**.

4. Klicken Sie auf **Hinzufügen**, und wählen Sie **Zeile hinzufügen** aus.

5. Wählen Sie **Geplanter Start** als Feld aus, und wählen Sie dann im Dropdownmenü **Heute** als Bedingung aus.

6. Click the <bpt id="p1">**</bpt>…<ept id="p1">**</ept> on the <bpt id="p1">**</bpt>Status<ept id="p1">**</ept> row and click <bpt id="p2">**</bpt>Delete<ept id="p2">**</ept> to delete that filter condition.

7. Press <bpt id="p1">**</bpt>Ok<ept id="p1">**</ept> to save the condition. The view is now filtered to show only records where the Scheduled Start date is today.

8. Fügen Sie der Ansicht die Felder **Tatsächlicher Start** und **Tatsächliches Ende** hinzu.

<bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> Since we no longer filter on the view status, we will get all today’s visits including completed ones. These fields will help to differentiate completed visits and visits in progress.

1. Klicken Sie auf **Speichern**.

2. Klicken Sie auf **Veröffentlichen** und warten Sie, bis die Veröffentlichung abgeschlossen ist.

## <a name="exercise-2-create-model-driven-app"></a>Übung 2: Eine modellgesteuerte App erstellen

**Ziel**: In dieser Übung erstellen Sie eine modellgesteuerte App, passen die Siteübersicht an und testen die App.

Zur Vereinfachung und Kürzung behandeln wir einige der „Besuch“-Spalten in diesem Lab nicht.

### <a name="task-1-create-app"></a>Aufgabe \#1: App erstellen

1. Melden Sie sich bei [https://make.powerapps.com](https://make.powerapps.com/) an (falls Sie nicht bereits angemeldet sind).

2. Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

3.  Klicken Sie, falls erforderlich, auf das **Startseitensymbol** auf der linken Seite des Bildschirms.

3. Erstellen der modellgesteuerten Anwendung:

    1. Wählen Sie **Leere App** im Abschnitt **Beginnen mit** des Startbildschirms aus.

    1. Wählen Sie unter **Leere App basierend auf Dataverse** die Option **Erstellen** aus.

    1. Geben Sie **Bellows Campusverwaltung** als „Name“ ein, und wählen Sie **Erstellen** aus.

4. Nachdem Ihre neue modellgesteuerte Anwendung geladen wurde, wählen Sie die Schaltfläche **Seite hinzufügen** aus.

5. Wählen Sie im Bildschirm „Seite hinzufügen“ die Option **Tabellenbasierte Ansicht und Formular** aus, und wählen Sie dann die Schaltfläche **Weiter** aus.

6. Fügen Sie die folgenden Tabellen hinzu:

    1. Navigieren Sie zu folgendem Pfad.

    1. Contact

7. Nachdem Sie die 2 Tabellen ausgewählt haben, wählen Sie **Hinzufügen** aus.

8. Wählen Sie mithilfe der Navigationssymbole auf der linken Seite des Bildschirms **Navigation** aus.

9. Wählen Sie im Navigationsbereich unterhalb der Bezeichnung „Navigationsleiste“ den Text **Gruppe 1** aus.

10. Ändern Sie auf der rechten Seite des Bildschirms im Abschnitt **Anzeigeoptionen** die Eigenschaft **Titel** in **Sicherheit**.

### <a name="task-2-edit-your-app"></a>Aufgabe Nr. 2: Bearbeiten Ihrer App

Nachdem wir nun Ihrer modellgesteuerten Anwendung alle erforderlichen Komponenten hinzugefügt haben, organisieren wir nun Elemente.

1. Wählen Sie im Navigationsbereich unter der Gruppe „Sicherheit“ **SubArea1** aus.

2. Wählen Sie die **Auslassungspunkte** aus, und wählen Sie im angezeigten Menü **SubArea1 entfernen** aus.

3. Wählen Sie in der Navigation auf der linken Seite des Bildschirms **Seiten** aus.

4. Suchen und erweitern Sie **Besuch** im Bereich „Seiten“.

5. Wählen Sie **Besuchsformular** aus.

6. Wählen Sie auf der rechten Seite des Bildschirms **Formular hinzufügen** aus.

7. Wählen Sie das Formular **Hauptinformationen** aus.

8. Wählen Sie unter **Besuch** im Bereich „Seiten“ die Option **Besuchsansicht** aus.

9. Wählen Sie auf der rechten Seite des Bildschirms **Ansicht hinzufügen** aus.

10. Wählen Sie die Ansicht **Heutige Besuche** aus.

11. Wählen Sie erneut **Ansicht hinzufügen** aus. 

12. Wählen Sie die Ansicht **Aktive Besuche** aus. 

13. Wählen Sie **Speichern** aus.

14. Nachdem der **Speicher**vorgang abgeschlossen wurde, wählen Sie die Schaltfläche **Veröffentlichen** aus, um Ihre Änderungen zu veröffentlichen.

### <a name="task-3-test-application"></a>Aufgabe 3: Testanwendung

1. Starten der Anwendung

    1. Wählen Sie **Wiedergeben** aus, um Ihre App in einem neuen Fenster zu öffnen.

2. Erstellen Sie einen neuen Kontakt.

    1. The app should open to the <bpt id="p1">**</bpt>My Active Contacts<ept id="p1">**</ept> view. If it does not, select Contacts on the left-hand navigation.

    1. Klicken Sie im oberen Menü auf **Neu**.

    1. Geben Sie als **Vornamen** Herbert und als Nachnamen **Dorner** an.

    1. Provide your personal email as <bpt id="p1">**</bpt>Email<ept id="p1">**</ept>. This will be used in a future lab where you will receive an email.

    1. Klicken Sie auf **Speichern und schließen**.

    1. Sie sollten nun den erstellten Kontakt in der Ansicht **Meine aktiven Kontakte** sehen.

3. Erstellen Sie einen neuen Besuch.

    1. Wählen Sie **Besuche** in der linken Navigationsleiste der Siteübersicht aus.

    1. Klicken Sie auf **+ NEU**.

    1. Füllen Sie die Felder folgendermaßen aus:

        1. **Name:** Neuer Testbesuch

        1. **Besucher**: Wählen Sie Max Mustermann aus

        1. **Geplanter Start**: Wählen Sie das morgige Datum und 14:00 Uhr als Startzeit aus

        1. **Geplantes Ende**: Wählen Sie das morgige Datum und 15:30 Uhr als Endzeit aus

- Click <bpt id="p1">**</bpt>Save &amp; Close<ept id="p1">**</ept>. This will create the Visit and you should be able to see it on the Active Visits View.

- Change view to <bpt id="p1">**</bpt>Today’s Visits<ept id="p1">**</ept>. You should no longer see the new visit in the view, since it is scheduled for tomorrow.

4. Sie können weitere Testdatensätze hinzufügen.

Ihre ausgeführte App sollte ungefähr so aussehen:

![](media/3-model-driven-app.png)

Congratulations! You have created and configured your first model-driven app.

## <a name="challenges"></a>Herausforderungen

- Auswählen spezifischer Ansichten und Formulare für Kontakte