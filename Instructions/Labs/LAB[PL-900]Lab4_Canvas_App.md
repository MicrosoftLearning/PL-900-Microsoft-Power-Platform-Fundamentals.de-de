---
lab:
  title: "Lab\_4: Eine Canvas-App erstellen"
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
  module: 'Module 2: Build a canvas app'
---
## Lernziel

In dieser Übung verwenden Sie Copilot, um eine Canvasanwendung zu erstellen, die Mitarbeitende zum Anfordern und Verwalten von Anträgen für Abwesenheit und Arbeitsmittel verwenden können. Nachdem die App erstellt wurde, verwenden Sie Copilot und den Power Apps-Designer, um die App anzupassen.

Nach erfolgreichem Abschluss dieses Labs können Sie Folgendes:

- Verwenden Sie Copilot, um Ihnen beim Erstellen eines Datenmodells für Ihre App zu helfen.
- Ändern Sie eine Canvasanwendung.

### Szenario

Contoso Consulting ist eine professionelle Dienstleistungsorganisation, die sich auf IT- und KI-Beratungsdienste spezialisiert hat. Sie möchten eine Anwendung erstellen, die Mitarbeiter verwenden können, um Abwesenheit zu beantragen.

### Details zum Lab

Bevor Sie mit dieser Übung beginnen, müssen Sie das folgende Lab abgeschlossen haben:

- **Lab 2: Erstellen eines Datenmodells**

> **Wichtig** Dieses Lab verwendet KI, um die Komponenten zu erstellen. Da KI-Ergebnisse variieren können, sind Ihre Ergebnisse möglicherweise unterschiedlich (aber ähnlich) mit den im Lab definierten Ergebnissen. Die grundlegenden Konzepte, die im Lab beschrieben werden, sind identisch, unabhängig davon, was erstellt wurde oder wie es benannt wurde. Wenn die Tabellen und Spalten nicht exakt übereinstimmen, müssen Sie sich möglicherweise an das, was für Sie erstellt wurde, anpassen.*

Die geschätzte Dauer dieser Übung beträgt **60 bis 75** Minuten.

## Aufgabe 1: Anmeldung bei Power Apps und Erkunden der Benutzeroberfläche

1.  Öffnen Sie einen Webbrowser, und navigieren Sie zum [Power Apps](https://make.powerapps.com/) Maker Portal.
2.  Wählen Sie mit der Navigation auf der linken Seite **Erstellen** aus.
3.  Wählen Sie unter **Apps erstellen** **Mit Copilot starten** aus.
4.  Geben Sie auf dem Bildschirm **Beschreiben Sie die Tabellen, die Copilot erstellen soll** Folgendes ein: „Ich möchte Abwesenheitsanträge speichern, die von Mitarbeitenden gesendet werden. Die Tabelle sollte die Start- und Endzeit des Antrags enthalten.“
5.  Wählen Sie die Schaltfläche **Tabellenoptionen** aus. Wählen Sie im daraufhin angezeigten Menü **Eine Tabelle** aus.

![Screenshot des Bildschirms „Erste Schritte mit Copilot“](media/60a2ec72988f48c91df7c370532cb331.png)

6.  Wählen Sie die Schaltfläche **Generieren** aus.

Copilot sollte eine **Tabelle** „Abwesenheitsanforderung“ erstellt haben. Als Nächstes fügen wir der Tabelle weitere Spalten hinzu.

7.  Geben Sie im Bereich **Copilot** Folgendes ein: „*Füge eine Spalte namens ‚Abwesenheitsgrund‘ hinzu.*“
8.  Fügen Sie im Bereich **Copilot** die folgenden Prompts einzeln hinzu.
    - „*Füge eine Auswahlspalte namens ‚Art der Abwesenheit‘ hinzu.*“
    - „*Füge eine Datenspalte namens ‚Einreichungsdatum‘ hinzu.*“
    - „*Füge eine Auswahlspalte namens ‚Genehmigungsstatus‘ zur Tabelle ‚Abwesenheitsanforderung‘ hinzu.*“
    - „*Füge eine mehrzeilige Textspalte namens ‚Antragsdetails‘ hinzu.*“

    Die Abwesenheitstabelle sollte dem Bild ähneln:

![Screenshot der fertigen Tabelle „Abwesenheitsanforderung“ ](media/2ac256daafe1853e5367852467690c76.png)

Als Nächstes fügen wir die Benutzertabelle zum Datenmodell hinzu, damit wir Abwesenheitsanforderungen bestimmten Benutzenden zuordnen können.

9.  Wählen Sie auf der **Befehlsleiste** **+ Vorhandene Tabelle** aus.
10.  Wechseln Sie von **Empfohlen** zu **Alle Tabellen**.
11.  Geben Sie im Feld **Suche** **Benutzer** ein.
12.  Wählen Sie die Tabelle **Benutzer** aus, und klicken Sie auf die Schaltfläche **Ausgewählte hinzufügen**.
13.  Wählen Sie auf der **Befehlsleiste** **Beziehungen erstellen** aus.
14.  Konfigurieren Sie die Beziehung wie folgt:

-   **1:** User (Benutzer)
-   **n:** Anforderung für arbeitsfreie Zeit
-   **Anzeigename**: Antragstellender Mitarbeiter
  
15.  Wählen Sie **Fertig** aus.

Das fertige Datenmodell sollte dem Bild ähneln:

![Screenshot des fertigen Datenmodells ](media/daa74d51e2ceada8e1e8b004cae9942a.png)

16.  Wählen Sie die Schaltfläche **App speichern und öffnen** aus.

> [!NOTE]
> Es kann mehrere Minuten dauern, bis Ihre neue App erstellt wird.

## Aufgabe 2: Personalisieren Ihrer neuen App

Nachdem Ihre neue App erstellt wurde, werden wir einige Änderungen daran vornehmen, um unseren Anforderungen bestmöglich gerecht zu werden. Wir beginnen, indem wir einige Änderungen an der Willkommensseite vornehmen.

1.  Wählen Sie in der geöffneten neuen App den Platzhalter **Bild** oberhalb des Texts **Abwesenheitsanträge** aus **.**
2.  Wählen Sie im angezeigten Menü die Option **Bearbeiten** \> **Hochladen** aus.
3.  Wählen Sie im Ordner für Klassendateien das Bild **Time off** und dann **Öffnen** aus.
4.  Wählen Sie als Nächstes den Platzhalter **Bild** über **Benutzer** aus.
5.  Wählen Sie im angezeigten Menü die Option **Bearbeiten** \> **Hochladen** aus.
6.  Wählen Sie im Ordner für Klassendateien das Bild **Employee** und dann **Öffnen** aus.

Als Nächstes werden wir die Größe der Bilder anpassen, damit sie leichter erkennbar sind. Darüber hinaus werden wir den Text anpassen, der für jedes Element angezeigt wird.

7.  Wählen Sie auf der **Befehlsleiste** die Schaltfläche **Eigenschaften** aus. (*Sie befindet sich direkt rechts neben der Bearbeitungsschaltfläche.*)
8.  Wählen Sie das Bild **Time off** aus, das Sie zuvor hinzugefügt haben.
9.  Konfigurieren Sie im Panel **Eigenschaften** das Bild wie folgt:
    
    -   **Bildposition:** Ausfüllen
    -   **Breite:** 300
    -   **Höhe:** 300
      
11.  Wiederholen Sie den vorherigen Schritt, um die **Höhe** und **Breite** des Bilds **Employee** auf **300** × **300** festzulegen.
12.  Wählen Sie den Text unter **Abwesenheitsanträge** aus.
13.  Wählen Sie im Panel **Eigenschaften** das Feld **Text** aus, und ändern Sie den Text in: „*Abwesenheitsanträge erstellen, anzeigen und verwalten*“
14.  Wählen Sie den Text **Willkommensbildschirm** im **Header** aus.
15.  Wählen Sie im Bereich **Eigenschaften** rechts das Feld **Logo** aus.
16.  Wählen Sie im daraufhin angezeigten Menü **Hochladen** aus.
17. Wählen Sie **Contoso logo** aus Ihren Klassendateien aus, und wählen Sie **Öffnen** aus.
18. Wählen Sie im Bereich **Eigenschaften** unter **Formatvorlage** und „Designgruppe“ das Symbol **Füllung** für die Farbe aus.
19. Wählen Sie die Registerkarte **Benutzerdefiniert** aus.
20. Ändern Sie die **Hex**-Farbe in: **101E2B**
21. Stellen Sie sicher, dass der **Header** weiterhin ausgewählt ist, und ändern Sie den **Titel** in **Contoso Employee Hub**.
22. Wählen Sie auf der **Befehlsleiste** die Schaltfläche **Speichern** aus, um die App zu speichern.
23. Legen Sie im Bildschirm **Speichern** den **Namen** auf **Contoso Employee Hub** fest, und wählen Sie **Speichern** aus.

Ihre App ähnelt dem Bild.

![Screenshot der Willkommensseite der Canvas-App.](media/533c80cc861941b6a353b56bfc0dbc0f.png)

## Aufgabe 3: Fügen Sie Ihrer App einen neuen Bildschirm hinzu.

Während Sie die App erstellen, erreicht einer Ihrer Vorgesetzten Sie zu Ihnen und fragt sich, ob Mitarbeiter diese App auch zum Ausleihen von Arbeitsmitteln verwenden könnten. Contoso speichert bereits Informationen zum Ausleihen von Arbeitsmitteln in Dataverse, sodass es nur darum geht, die Informationen in der App verfügbar zu machen.

1.  Erweitern Sie bei geöffneter App den Bereich **Copilot** (falls erforderlich). Geben Sie in Copilot Folgendes ein: „*Füge einen neuen Bildschirm namens ‚Arbeitsmittel ausleihen‘ hinzu.*
2.  Wählen Sie **Send** (Senden) aus.
3.  Wählen Sie die Schaltfläche **Übernehmen** aus, um den Bildschirm zu übernehmen.
4.  Der App wird ein neuer Bildschirm mit dem Namen **Arbeitsmittel ausleihen** hinzugefügt.
5.  Klicken Sie auf dem Bildschirm **Arbeitsmittel ausleihen** auf **Layout**, und wählen Sie das **Randleistenlayout** aus.
6.  Erweitern Sie die verschiedenen Container, bis **SideBarContainer** sichtbar ist.

![Screenshot der Strukturansicht ](media/cde6257402b7a8786e679ab64ee0f882.png)

7.  Klicken Sie mit der rechten Maustaste auf **SidebarContainer**, und benennen Sie ihn in **EquipContainer1** um.
8.  Klicken Sie, während der **EquipContainer1** Container ausgewählt ist, auf die Schaltfläche **Einfügemenü öffnen**.
9.  Geben Sie im Fenster **Suche** **Katalog** ein, und wählen Sie **Vertikaler Katalog** aus.
10.  Wenn Sie aufgefordert werden, eine Datenquelle in dem angezeigten Feld **Suche** anzugeben, geben Sie **Arbeitsmittel** ein, und wählen Sie die Tabelle **Arbeitsmittel** aus.
11. Wählen Sie in der **Strukturansicht** auf der linken Seite des Bildschirms das **Gallery1**-Steuerelement aus, das Sie soeben hinzugefügt haben.
12. Klicken Sie mit der rechten Maustaste auf den Katalognamen, wählen Sie **Umbenennen** aus, und benennen Sie ihn in **Arbeitsmittelliste** um.
13. Zeigen Sie auf den Katalog **Arbeitsmittelliste**, und wählen Sie auf der Symbolleiste, die oberhalb des Katalogs angezeigt wird, **Layout** aus.
14. Wählen Sie die Option **Titel- und Untertitellayout** aus.
15. Konfigurieren Sie im Bereich **Eigenschaften** im ausgewählten Katalog **Arbeitsmittelliste** Folgendes:

    -   **Breite:** 360
    -   **Flexible Höhe:** Aktiviert
    -   **Mindesthöhe:** 287

Als Nächstes fügen wir dem Container **EquipmentContiner1** einen zusätzlichen Container hinzu, um ein Suchsteuerelement zu speichern, mit dem wir den Inhalt des Katalogs **Arbeitsmittelliste** filtern.

16.  Wählen Sie in der **Strukturansicht** **EquipContainer1** aus.
17.  Zeigen Sie auf den Container, und wählen Sie das Symbol **Copilot** aus.
18.  Geben Sie folgenden Text ein: „*Füge einen horizontalen Container ein.*“

![Screenshot: Einfügen eines Katalogs in einen Container](media/b9b784ea5625469c8785650b977f32d1.png)

19.  Wählen Sie die Schaltfläche **Übernehmen** aus.
20.  Am unteren Rand des Containers **EquipContainer1** wird ein neuer Container hinzugefügt.
21.  Klicken Sie in der **Strukturansicht** auf den neuen Container, halten Sie ihn gedrückt, ziehen Sie ihn, und platzieren Sie ihn über dem Katalog **Arbeitsmittelliste**.
22.  Benennen Sie den Container in **EquipSearchContainer** um.
23.  Wenn **EquipSearchContainer** ausgewählt ist, konfigurieren Sie im Bereich **Eigenschaften** Folgendes:
    
 -   **Mindestbreite:** 0
 -   **Flexible Höhe:** Deaktiviert
 -   **Höhe:** 44
   
24.  Wenn **EquipSearchContainer** ausgewählt ist, wählen Sie Schaltfläche **Einfügemenü öffnen** aus.
25. Geben Sie im Feld **Suche** **Text** ein, und wählen Sie **Texteingabe** aus.
26. Benennen Sie das Feld **Texteingabe** in **EquipSearchInput** um.
27. Wenn **EquipSearchInput** ausgewählt ist, konfigurieren Sie im Bereich **Eigenschaften** Folgendes:

    -   **Standardwert:** Leer (nichts)
    -   **Hinweistext:** Search
    -   **Schriftart:** Open Sans
    -   **Schriftgrad:** 14
    -   **Abstand** (Die folgenden Werte sind möglicherweise bereits vorhanden.)
        -   **Oben:** 5
        -   **Unten:** 5
        -   **Links:** 12
        -   **Rechts:** 5
    -   **Höhe:** 44
    -   **Flexible Breite:** Aktiviert
    -   **Mindestbreite:** 0

        ![Screenshot der Sucheingabeeigenschaften.](media/b0e092b4795edf58dad1153209639051.png)

28. Wählen Sie in **Strukturansicht** den **EquipSearchContainer** aus.
29. Zeigen Sie auf den Container, wählen Sie das Symbol **Copilot** aus, und geben Sie *Suchsymbol hinzufügen* ein.
30. Wählen Sie **Keep it** aus.

> **Hinweis:** Wenn Coplot das falsche Symbol hinzufügt, entfernen Sie es, und fügen Sie die Lupe manuell ein.

31. Wenn das Symbol **Suche** ausgewählt ist, konfigurieren Sie das Steuerelement im Bereich **Eigenschaften** wie folgt:

    -   **Auffüllen**
        -   **Oben:** 10
        -   **Unten:** 10
        -   **Links:** 10
        -   **Rechts:** 10
    -   **Höhe:** 44
    -   **Breite:** 44

![Screenshot der Eigenschaften des Suchsymbols](media/cb3305731a09bca0bbf166d55d9822a4.png)

32. Wählen Sie in der **Strukturansicht** auf der linken Seite den **EquipSearchContainer** aus.
33. Konfigurieren Sie im Bereich **Eigenschaften** den Container wie folgt:

    -   **Mindestbreite:** 0
    -   **Höhe:** 44

Abschließend konfigurieren wir den Katalog **Arbeitsmittelliste** so, dass die Daten basierend auf dem im Suchsteuerelementfeld eingegebenen Text aufgefüllt werden.

34.  Wählen Sie den Katalog **Arbeitsmittelliste** aus, den Sie zuvor erstellt haben.
35.  Geben Sie in der Eigenschaft **Items** die folgende Formel ein: Search([@'Arbeitsmittel'], *EquipSearchInput*.Text, 'Name des Arbeitsmittels',Category)

![Screenshot: PowerFx-Formel für „Items“](media/powerfx-formula.png)

36. Wählen Sie auf der **Befehlsleiste** die Schaltfläche **Speichern** aus, um Ihre App zu speichern.

> **Wichtig:** Wenn Sie die Formel kopiert und in die Bearbeitungsleiste eingefügt haben, ist es möglich, dass die Angaben in '' für Arbeitsmittel und Name des Arbeitsmittels falsch sind. Wenn Sie einen Formelfehler erhalten, versuchen Sie, sie zu entfernen und erneut einzugeben.

## Aufgabe 4: Erstellen eines Containers, um Datensatzvorgänge anzuzeigen

Wenn ein Benutzer einen Datensatz in der Arbeitsmittelliste auswählt, sollte der Datensatz in einem anderen Container geöffnet werden, damit er den ausgewählten Datensatz bearbeiten kann.

1.  Wählen Sie den **MainContainer** aus, und benennen Sie ihn in **DetailsContainer** um.
2.  Wählen Sie in **DetailsContainer** die Schaltfläche **Einfügen** aus.
3.  Geben Sie im Feld **Suche** **Container** ein, und wählen Sie **Vertikaler Container** aus.
4.  Klicken Sie mit der rechten Maustaste, und **ändern Sie den Namen** des Containers in **RecordDetails**.
5.  Wählen Sie im Container **RecordDetails** die Schaltfläche **Einfügen** aus.
6.  Wählen Sie im Menü **Einfügen** **Formular bearbeiten** aus.
7.  Wählen Sie auf dem Bildschirm „Datenquelle auswählen“ **Arbeitsmittel** aus. *(Es kann bis zu 30 Sekunden dauern, bis die Daten aufgefüllt werden.)*
8.  Klicken Sie mit der rechten Maustaste auf das Formular, das Sie gerade hinzugefügt haben, und **ändern Sie den Namen** in **EquipmentForm**.
9.  Wählen Sie im Bereich **Eigenschaften** die Registerkarte **Erweitert** aus, und legen Sie die Eigenschaft **Item** auf Folgendes fest: *'Arbeitsmittelliste'*.Selected. *(Dadurch wird das Formular mit dem aktuell ausgewählten Datensatz aufgefüllt.)*
10. Wählen Sie die Registerkarte **Anzeige** aus, und konfigurieren Sie das Formular wie folgt:

    -   **Spalten:** 2
    -   **Standardmodus:** Bearbeiten

Nun fügen wir einen weiteren Container hinzu, der zum Steuern der Vorgänge im Formular verwendet wird.

11.  Stellen Sie sicher, dass Sie **DetailsContainer** ausgewählt haben.
12.  Wählen Sie das angezeigte **Copilot**-Symbol aus. Geben Sie Folgendes ein: *„Füge einen horizontalen Container ein.“*
13.  Wählen Sie **Keep it** aus.
14.  Klicken Sie mit der rechten Maustaste auf den Container, und **ändern Sie den Namen** in **SelectedRecord1**.
15.  Verschieben Sie mit der **Strukturansicht** den Container **SelectedRecord1** über den Container **RecordDetails**.
16.  Konfigurieren Sie den Container **SelectedRecord1** wie folgt:
    
-   **Mindestbreite:** 250
-   **Flexible Höhe:** Deaktiviert
-   **Height**: 50
    
18.  Wählen Sie bei ausgewähltem Container **SelectedRecord1** die Schaltfläche **Einfügen** aus.
19.  Wählen Sie **Beschriftung** aus.
20.  Benennen Sie die Bezeichnung in **SelectedRecordTitle** um.
21. Konfigurieren Sie **SelectedRecordTitle** wie folgt:

    1.  **Auffüllen**
        1.  **Oben:** 5
        2.  **Unten:** 5
        3.  **Links:** 30
        4.  **Höhe:** 40
    2.  **Flexible Breite:** Aktiviert
    3.  **Mindestbreite:** 150
       
23. Wählen Sie den **SecondRecord1**-Container aus, und klicken Sie auf die Schaltfläche **Einfügen**.
24. Geben Sie im Feld **Suche** **Speichern** ein, und wählen Sie das Symbol **Speichern** aus.
25. Konfigurieren Sie die Schaltfläche **Speichern** wie folgt:

    -   **Höhe:** 40
    -   **Width**: 40
      
27. Wählen Sie die **OnSelect**-Eigenschaft aus, und geben Sie die folgende Formel ein: SubmitForm(EquipmentForm).

![Screenshot: PowerFx-Formel für „OnSelect“](media/e5b22c91a437e6918269d65e2616afc8.png)

## Aufgabe 5: Ändern des Headers auf der Seite

Der letzte Schritt beim Erstellen dieses Bildschirms besteht darin, den Readercontainer mit Daten aufzufüllen.

1.  Wählen Sie oben in der App den **HeaderContainer** aus.
2.  Klicken Sie auf die Schaltfläche **Einfügen**.
3.  **Textbeschriftung** auswählen.
4.  Konfigurieren Sie das Steuerelement **Textbeschriftung** wie folgt:
   
    -   **Text:** Arbeitsmittel ausleihen
    -   **Schriftart:** Open Sans
    -   **Schriftgrad:** 16
    -   **Schriftbreite:** Halbfett
        -   **Abstand:** 16
        -   **Unten:** 16
        -   **Links:** 16
        -   **Rechts:** 16
    -   **Höhe:** 40
    -   **Flexible Breite:** Aktiviert

        ![Screenshot der Textbeschriftungseigenschaften](media/088cafeec651b099fa49ac1f151cd228.png)

6.  Wählen Sie den **HeaderContainer**, dann **Einfügen** und dann das **Startsymbol** aus.
7.  Legen Sie die Eigenschaft **OnSelect** für die Startschaltfläche fest auf: Back()

![Screenshot des Navigationsbefehls „Zurück“](media/38d0e5367ee41da58ac9902f8056b1af.png)

## Aufgabe 6: Fertigstellen der Konfiguration des Willkommensbildschirms

Bei der Überprüfung haben wir entschieden, dass wir nicht in der Lage sein müssen, Benutzer in dieser App zu erstellen. Daher ändern wir den Willkommensbildschirm so, dass Sie auf die Seite zum Ausleihen von Arbeitsmitteln zugreifen können.

7.  Wählen Sie in der **Strukturansicht** den **Willkommensbildschirm** aus.
8.  Wählen Sie das **Bild** über **Benutzer** aus.
9.  Wählen Sie im angezeigten Menü **Bearbeiten** und dann **Hochladen** aus.
10.  Suchen Sie das Bild **Equipment** in Ihrem student-Ordner, und wählen Sie **Öffnen** aus.
11.  Legen Sie die Eigenschaft **OnSelect** für das Bild auf Folgendes fest: Navigate(*'Arbeitsmittel ausleihen'*)
12.  Wählen Sie den Text **Users** aus, und legen Sie die Eigenschaft **Text** auf **Arbeitsmittel** fest.
13.  Wählen Sie den **Text** unter **Arbeitsmittel** aus, und ändern Sie die Eigenschaft **Text** in: Arbeitsmittel ausleihen und Anmeldungen bearbeiten

![Ein Screenshot eines Computers, KI-generierter Inhalt kann fehlerhaft sein.](media/561d1e8cd023541761b6523138c2fde8.png)

14. Klicken Sie auf **Speichern**, um Ihre App zu speichern.

## Aufgabe 7: Testen Ihrer Anwendung

1.  Wählen Sie auf der **Befehlsleiste** die Schaltfläche **Wiedergeben** aus.
2.  Wählen Sie das Bild **Equipment** aus.
3.  Geben Sie im Feld **Suche** **Elektronik** ein. (*Beachten Sie, wie die Liste filtert.*)
4.  Wählen Sie den **Laptop**-Datensatz aus.
5.  Ändern Sie die **Kategorie** in **Möbel**.
6.  Wählen Sie die Schaltfläche **Speichern** aus.
7.  Beachten Sie, dass sich die Kategorie von **Laptop** in **Möbel** ändert.
8.  Wählen Sie die Schaltfläche **Home** aus.
9.  Wählen Sie das **violette X** aus, um den **Vorschaumodus** zu verlassen.

## Aufgabe 8: Speichern und Veröffentlichen der App

**Ziel:** Speichern und veröffentlichen Sie die App, um sie über Webbrowser, mobile Geräte oder eingebettete Plattformen wie SharePoint oder Teams zugänglich zu machen.

1.  Wählen Sie in Power Apps Studio die Schaltfläche **Speichern** aus.
2.  Wählen Sie die Schaltfläche **Veröffentlichen** aus.
3.  Wählen Sie **Diese Version veröffentlichen** aus.
