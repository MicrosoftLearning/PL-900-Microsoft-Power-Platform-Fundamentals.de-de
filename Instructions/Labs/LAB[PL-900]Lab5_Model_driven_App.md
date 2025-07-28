---
lab:
  title: "Lab\_5: Eine modellgesteuerte App erstellen"
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
  module: 'Module 3: Build a model-driven app'
---
## Lernziel

In dieser Übung erstellen Lernende eine modellgesteuerte App in Power Apps mit Copilot. Sie definieren das Datenmodell, ändern Formulare und Ansichten und erstellen die Anwendung.

**Nach erfolgreichem Abschluss dieses Labs können Sie Folgendes:**

-   Eine modellgesteuerte Anwendung erstellen
-   Formulare und Ansichten in der Anwendung so ändern, dass sie Ihren Anforderungen am besten entsprechen
-   Durch eine modellgesteuerte Anwendung navigieren

### Szenario

Contoso Consulting ist eine professionelle Dienstleistungsorganisation, die sich auf IT- und KI-Beratungsdienste spezialisiert hat. Im Laufe des Jahres veranstalten sie viele verschiedene Events für ihre Kunden. Einige davon sind Events im Stil von Messen, bei denen viele Partner anwesend sind und Informationen zu neuen Produkten, Markttrends und Dienstleistungen bereitstellen. Andere finden das ganze Jahr über statt und sind kurze Webinare, in denen Details zu einzelnen Produkten vorgestellt werden.

Contoso möchte Power Platform verwenden, um eine Eventverwaltungslösung zu erstellen, mit der das Unternehmen die verschiedenen Events verwalten kann, die es im Laufe des Jahres veranstaltet.

In dieser Übung erstellen Sie eine modellgesteuerte Anwendung zum Verwalten von Events von Contoso. Die modellgesteuerte Anwendung basiert auf einem vorhandenen Datenmodell und umfasst Ereignisse, Ereignissitzungen und Sitzungsregistrierungen.

### Labdetails:

Bevor Sie mit dieser Übung beginnen, empfiehlt es sich, Folgendes abgeschlossen zu haben:

-   **Lab 1: Erstellen einer Lösung**
-   **Lab 2: Erstellen eines Datenmodells**

Die geschätzte Dauer dieser Übung beträgt **20 bis 30** Minuten.

## Aufgabe 1: Erstellen eines Datenmodells zur Unterstützung Ihrer neuen modellgesteuerten Anwendung

Contoso speichert derzeit Kontaktinformationen in der Dataverse-Instanz, und das Unternehmen möchte Dataverse verwenden, um Kurse und Kursregistrierungen nachzuverfolgen. Sie müssen die erforderlichen Tabellen erstellen, um die Anwendung zu unterstützen und eine modellgesteuerte Anwendung basierend auf diesem Datenmodell erstellen.

1.  Öffnen Sie bei Bedarf einen Webbrowser, navigieren Sie zum [Power Apps](https://make.powerapps.com/) Maker Portal, und melden Sie sich mit Ihren Microsoft-Kontoanmeldeinformationen an.
2.  Wählen Sie links im Navigationsbereich die Option **Lösungen** aus.
3.  Öffnen Sie die Lösung **Ereignisverwaltung**, die Sie zuvor erstellt haben.
4.  Wählen Sie in der **Befehlsleiste** die Optionen **Neu** \> **App** \> **Modellgesteuerte App** aus.
5.  Wählen Sie den Abschnitt **Erstellen** aus.
    -   **Name:** Contoso-Ereignisverwaltung
    -   **Beschreibung:** Wird zum Verwalten von Ereignissen und Ereignissitzungen verwendet.
6.  Wählen Sie die Schaltfläche **Erstellen** aus **.**
7.  Wählen Sie die Schaltfläche **Seite hinzufügen** und dann **Dataverse-Tabelle** aus.
8.  Wählen Sie die folgenden Tabellen aus:
    -   Kontakt
    -   Ereignis
    -   Eventsitzung
    -   Sitzungsregistrierung
9.  Stellen Sie sicher, dass **Im Navigationsbereich anzeigen** ausgewählt ist.

![Screenshot mit dem Dialogfeld „Tabelle auswählen“](media/bb46dc856d2939af9c55bdc0303b8a27.png)

10. Wählen Sie die Schaltfläche **Hinzufügen** aus.

> **Hinweis:** Manchmal werden Sie aufgefordert, sich anzumelden, während Sie mit dem Designer arbeiten. Wählen Sie das X aus, um den Anmeldebildschirm abzubrechen.

## Aufgabe 2: Bearbeiten der modellgesteuerten Anwendung entsprechend Ihren Anforderungen

Nachdem die App erstellt wurde, nehmen wir einige Änderungen an der Darstellung der Anwendung vor. Wir möchten zwei unterschiedliche Gruppen haben: Personen und Ereignisse. Wir möchten die Tabelle „Kontakte“ in der Gruppe „Personen“ und alle Ereignistabellen in der Gruppe „Ereignisse“ haben.

1.  Wählen Sie auf der linken Seite des Bildschirm unter **Navigation** die Option **Neue Gruppe** aus.
2.  Erweitern Sie auf der rechten Seite der Anwendung den Bereich **Eigenschaften**.
3.  Ändern Sie den **Titel** von **Neue Gruppe** in **Personen**.

    ![Screenshot, der das Ändern eines Gruppennamens zeigt ](media/82b6d0cdc4fdbaf4a9eaf2d1f82e972f.png)

4.  Wählen Sie die **Auslassungspunkte** in der Gruppe **Personen** aus.
5.  Wählen Sie **Neue Gruppe** aus.
6.  Ändern Sie im Bereich **Eigenschaften** den Namen der Gruppe von **Neue Gruppe** in **Ereignisse**.
7.  Zeigen Sie mit dem Mauszeiger auf die Ansicht **Sitzungsregistrierungen** auf der linken Seite, wählen Sie die **Auslassungspunkte** und anschließend **Nach unten**, um **Sitzungsregistrierungen** in die Gruppe **Ereignisse** zu verschieben.
8.  Zeigen Sie mit dem Mauszeiger auf die Ansicht **Ereignissitzungen** auf der linken Seite, wählen Sie die **Auslassungspunkte** und anschließend **Nach unten**, um **Ereignissitzungen** in die Gruppe **Ereignisse** zu verschieben.
9.  Zeigen Sie mit dem Mauszeiger auf die Ansicht **Ereignisse** auf der linken Seite, wählen Sie die **Auslassungspunkte** und anschließend **Nach unten**, um **Ereignisse** in die Gruppe **Ereignisse** zu verschieben.

Ihre App sollte dem Bild ähneln:

![Screenshot mit aktualisierter Sitemap](media/ff039cad105533933959854cec4ec95e.png)

## Aufgabe 3: Bearbeiten der verschiedenen Formulare und Ansichten in Ihrer modellgesteuerten Anwendung

Die modellgesteuerte Anwendung verwendet Formulare und Ansichten, um Benutzenden auf der Benutzeroberfläche Daten zu präsentieren. Wir werden einige Änderungen an diesen Elementen vornehmen.

1.  Stellen Sie sicher, dass Ihre **Contoso-Ereignisverwaltung**-App im Designer geöffnet ist.
2.  Zeigen Sie auf der linken Seite des Bildschirms unter der Gruppe **Personen** auf das **Kontaktformular**, und wählen Sie **Bearbeiten** aus.

    Wenn Sie aufgefordert werden, Ihre Änderungen zu speichern, wählen Sie **Speichern und fortfahren** aus.

3.  Wählen Sie unter **Tabellenspalten** auf der linken Seite **Neue Tabellenspalte** aus.
4.  Konfigurieren Sie die Tabellenspalte wie folgt:
    -   **Anzeigename**: Kontakttyp
    -   **Datentyp:** Auswahl
    -   **Mit globaler Auswahl synchronisieren:** Nr.
5.  Legen Sie die **Bezeichnung** der ersten Wahl auf **Sprecher** fest.
6.  Wählen Sie **+ Neue Auswahl** aus, und legen Sie die Bezeichnung auf **Teilnehmer** fest.
7.  Wählen Sie **+ Neue Auswahl** aus, und legen Sie die Bezeichnung auf **Supportpersonal** fest.

![Screenshot der Spalte „Kontakttyp“](media/b1982b779d91cf134b41b6f445b8f07c.png)

8.  Wählen Sie die Schaltfläche **Speichern** aus.
9.  Wählen Sie mit der Maus den Text **Neuer Kontakt** aus, um den Formularkopf auszuwählen. *(Ein violettes Rechteck sollte um die Kopfzeile herum angezeigt werden)*
10. Geben Sie unter **Tabellenspalten** im Feld **Suche** **Kontakt** ein.
11. Wählen Sie die soeben erstellte Tabellenspalte **Kontakttyp** aus.
12. Der **Kontakttyp** sollte nun in der **Kopfzeile** angezeigt werden.

![Screenshot des Kontakttypfelds in einem Formular](media/4debe7a09e460f79c1cb05a6824dad66.png)

13. Wählen Sie auf der **Befehlsleiste** des Formulars die Schaltfläche **Speichern und veröffentlichen** aus.
14. Wählen Sie den **Zurück-Pfeil** aus, um zum Designer für die modellgesteuerte Anwendung zurückzukehren.
15. Zeigen Sie unter **Navigation** links mit dem Mauszeiger auf die Ansicht **Kontakte**, und wählen Sie das Symbol **Bearbeiten** aus. (Wenn Sie zum Speichern aufgefordert werden, wählen Sie **Speichern und fortfahren** aus.)
16. Wählen Sie **+ Sichtspalte** aus.
17. Suchen Sie nach der Spalte **Kontakttyp**, und fügen Sie sie der Ansicht hinzu.
18. Wählen Sie die Schaltfläche **Speichern und veröffentlichen** aus.
19. Wählen Sie die Schaltfläche **Pfeil „Zurück“** aus, um zum Designer für die modellgesteuerte Anwendung zurückzukehren.

Als Nächstes nehmen wir die erforderlichen Änderungen an den verbleibenden Formularen vor.

20.  Wählen Sie unter **Navigation** die **Ereignisansicht** aus.
    
Beachten Sie, dass möglicherweise eine Spalte namens **EventDetails1** vorhanden ist. Wenn ja, entfernen wir sie aus der Ansicht. *(Wenn die Spalte nicht vorhanden ist, können Sie mit **Vorgang 4: Speichern und veröffentlichen** fortfahren).*

21.  Zeigen Sie mit dem Mauszeiger auf die **Ereignisansicht**, und wählen Sie die Schaltfläche **Bearbeiten** aus.

Wenn Sie zum **Speichern** von Änderungen aufgefordert werden, wählen Sie **Speichern und fortfahren** aus.

22.  Wählen Sie in der **Ansicht** den Pfeil neben **EventDetails1** aus, und wählen Sie im daraufhin angezeigten Menü **Entfernen** aus.

![Screenshot, der zeigt, wie Sie eine zusätzliche Spalte aus einer Ansicht entfernen](media/f0f1484a4f3a679abc18cdb1cd5c04da.png)

23.  Wählen Sie die Schaltfläche **Speichern und veröffentlichen** aus.
24.  Wählen Sie den **Pfeil „Zurück“** aus, um zum App-Designer zurückzukehren.
25.  Zeigen Sie unter **Navigation** mit dem Mauszeiger auf das **Formular** **Ereignisse**, und wählen Sie **Bearbeiten** aus.

Wenn Sie zum Speichern von Änderungen aufgefordert werden, wählen Sie **Speichern und fortfahren** aus.

26.  Wählen Sie das Feld **Event Details1** aus, und drücken Sie die Taste **ENTF** auf Ihrer Tastatur.

Ihr Formular sollte dem Bild ähneln:

![Screenshot des aktualisierten Ereignisformulars, nachdem eine zusätzliche Spalte entfernt wurde ](media/d9e8903c79b01e85e32c6ef5279a2ad5.png)

Wenn es nicht genau übereinstimmt, ist dies in Ordnung, solange alle Felder im Bild vorhanden sind.  

27.  Wählen Sie die Schaltfläche **Speichern und veröffentlichen**.
28.  Wählen Sie den **Pfeil „Zurück“** aus, um zum App-Designer zurückzukehren.

## Aufgabe 4: Speichern und Veröffentlichen (Wenn Sie das Feld „EventDetail1“ nicht auf dem Formular haben, fahren Sie hier fort.)

1.  Wählen Sie auf der **Befehlsleiste** der App die Schaltfläche **Speichern und veröffentlichen** aus.
2.  Wählen Sie die Schaltfläche **Zurück** aus, um zur Projektmappe **Ereignisverwaltung** zurückzukehren.
3.  Wählen Sie den Pfeil **Zurück zu Projektmappen** aus, um zum **Power Apps Maker** Portal zurückzukehren.
4.  Wählen Sie den Pfeil **Zurück** aus, um zum Hauptbildschirm von **Power Apps** zurückzukehren.

## Aufgabe 5: Testen Ihrer neuen Anwendung

Nachdem Ihre modellgesteuerte Anwendung erstellt wurde, testen wir ihre Funktionalität.

Zunächst werden wir ein paar Kontakte hinzufügen.

1.  Wählen Sie links im Navigationsbereich die Option **Apps** aus.
2.  Ändern Sie die angezeigten Apps von **Meine Apps** in **Alle**.
3.  Zeigen Sie auf die soeben erstellte Anwendung **Ereignisverwaltung**, und wählen Sie das Symbol **Wiedergeben** aus.
4.  Wählen Sie links im Navigationsbereich die Option **Kontakte** aus.
5.  Wählen Sie auf der **Befehlsleiste** die Schaltfläche **+ Neu** aus.
6.  Konfigurieren Sie im Bildschirm **Neuer Kontakt** wie folgt:
    -   **Vorname:** Suzanne
    -   **Nachname:** Diaz
    -   **Position:** Techniker
7.  Wählen Sie in der Formularkopfzeile den Abwärtspfeil neben **Kontakttyp** aus.
8.  Legen Sie den **Kontakttyp** auf **Sprecher** fest.

![Screenshot, der zeigt, wie das Feld „Kontakttyp“ in einem Formular festgelegt wird](media/0860116a9b7df096c14728212b9977b1.png)

9.  Wählen Sie die Schaltfläche **Speichern** aus, um den Kontakt zu speichern, und lassen Sie ihn geöffnet.
10. Wählen Sie die Schaltfläche **+ Neu** aus.
11. Konfigurieren Sie im Bildschirm **Neuer Kontakt** wie folgt:
    -   **Vorname:** Edgar
    -   **Nachname:** Swenson
    -   **Position:** architekt
    -   **E-Mail-Adresse:** Geben Sie Ihre E-Mail-Adresse ein (Stellen Sie sicher, dass Sie **Ihre** E-Mail-Adresse hinzufügen).
12. Wählen Sie in der Formularkopfzeile den Abwärtspfeil neben **Kontakttyp** aus.
13. Legen Sie den **Kontakttyp** auf **Teilnehmer** fest.
14. Wählen Sie die Schaltfläche **Speichern und schließen** aus.

Als Nächstes fügen wir ein neues Ereignis hinzu.

15.  Wählen Sie links im Navigationsbereich die Option **Ereignisse** aus.
16.  Wählen Sie auf der Befehlsleiste die Schaltfläche **+ Neu** aus.
17.  Konfigurieren Sie im Bildschirm **Neues Ereignis** wie folgt:
- **Ereignisname:** Frühlingskonferenz
- **Ereignisdatum:** Datum von morgen
- **Maximale Teilnehmeranzahl:** 500
- **Ereignisdetails:** Frühlingskonferenz zur Vorstellung von Produktneuheiten und Services von unseren unterstützten Lieferanten
- **Ereignistyp:** Konferenz
- **Standort:** Seattle
- **Registrierung erforderlich:** Ja/Wahr

![Screenshot des ausgefüllten Ereignisformulars ](media/802f68c4c34c635eeff620a23d42acd8.png)

18.  Wählen Sie die Schaltfläche **Speichern und schließen** aus.

Als Nächstes fügen wir eine neue Sitzung für das Ereignis hinzu.

19.  Wählen Sie links im Navigationsbereich die Option **Ereignissitzungen** aus.
20.  Wählen Sie die Schaltfläche **+ Neu** aus.
21.  Konfigurieren Sie die **Ereignissitzung** wie folgt:
- **Sitzungsname:** Verantwortungsbewusste künstliche Intelligenz
- **Sitzungsdatum:** Datum von morgen
- **Dauer:** 1,5 Stunden
- **Sitzungsbeschreibung:** Mit allen neuen KI-Lösungen ist es wichtig, verantwortungsbewusst zu handeln. Wir werden die Herausforderungen diskutieren.
- **Referentin:** Suzanne Diaz
- **Ereignis:** Frühlingskonferenz

![Screenshot des ausgefüllten Ereignissitzungsformulars ](media/6e509e4a29e6f253b5db3b4c9f82e42e.png)

22.  Wählen Sie **Speichern und schließen** aus.

Schließlich erstellen wir eine **Sitzungsregistrierung**.

23.  Wählen Sie mit der Navigation auf der linken Seite **Sitzungsregistrierungen** aus.
24.  Wählen Sie auf der **Befehlsleiste** **+ Neu** aus.
25.  Führen Sie die Sitzungsregistrierung wie folgt aus:
- **Registrierungsname:** E, Swenson Registration.
- **Besitzer**: Nehmen Sie keine Änderung vor.
- **Registrierungsdatum:** Heutiges Datum
- **Spezielle Anweisungen:** Kein Gluten
- **Teilnehmer:** Edgar Swenson
- **Ereignissitzung:** Verantwortungsbewusste künstliche Intelligenz

![Screenshot des ausgefüllten Sitzungsregistrierungsformulars  ](media/Session-registration-form.png)

26.  Wählen Sie **Speichern und schließen** aus.
