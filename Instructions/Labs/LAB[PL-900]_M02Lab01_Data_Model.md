---
lab:
  title: 'Lab 1: Datenmodellierung'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 05d0f0656ae0d93f5666f7c14602c3976a9a9ac9
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898891"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Modul 2: Einführung in Microsoft Dataverse

# <a name="scenario"></a>Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab greifen Sie auf Ihre Umgebung zu, erstellen eine Microsoft Dataverse-Datenbank und eine Lösung zum Nachverfolgen Ihrer Änderungen. Sie erstellen auch ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

-   R1 – Verfolgen Sie Standorte (Gebäude) der Campusbesuche
-   R2 – Aufzeichnen der grundlegende Informationen, um die Besucher zu identifizieren und nachzuverfolgen 
-   R3 – Planen, Aufzeichnen und Verwalten von Besuchen 

Zum Abschluss importieren Sie Beispieldaten in Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

* eine Lösung und einen Herausgeber erstellen.
* sowohl neue als auch vorhandene Komponenten hinzufügen, die zur Erfüllung der Anwendungsanforderungen erforderlich sind. Beschreibungen zu den Metadaten (Tabellen und Beziehungen) finden Sie im [Datenmodelldokument](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Sie können die STRG-Taste gedrückt halten oder mit der rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.

Nach Abschluss aller Anpassungen wird Ihre Lösung mehrere Tabellen enthalten:

-   Contact
-   Erstellen
-   Navigieren Sie zu folgendem Pfad.

## <a name="prerequisites"></a>Voraussetzungen:

* Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**

## <a name="things-to-consider-before-you-begin"></a>Bevor Sie beginnen, sollten Sie Folgendes berücksichtigen:

* Benennungskonvention

* Datentypen, Einschränkungen (z. B. maximale Länge eines Namens)

* Datetime-Formatierung zur Unterstützung einer einfachen Lokalisierung

# <a name="exercise-1-create-solution"></a>Übung 1: Lösung erstellen

## <a name="task-1-create-solution-and-publisher"></a>Aufgabe 1: Lösung und Publisher erstellen

1.  Projektmappe erstellen

    -   Navigieren Sie zu <https://make.powerapps.com>. Möglicherweise müssen Sie sich erneut authentifizieren. Klicken Sie dazu auf **Anmelden**, und folgen Sie den Anweisungen (falls erforderlich).

    -   Wählen Sie Ihre Umgebung aus. Klicken Sie dazu in der oberen rechten Ecke des Bildschirms auf **Umgebung**, und wählen Sie im Dropdownmenü Ihre Umgebung aus.

    -   Wählen Sie **Lösungen** aus dem linken Menü aus, und klicken Sie auf **Neue Lösung**.

    -   Geben Sie **[Ihr Nachname] Campusverwaltung** als **Anzeigename** ein.

2.  Herausgeber erstellen

    -   Wählen Sie im Abschnitt **Herausgeber** die Option **+ Herausgeber** aus.

    -   Geben Sie in dem Fenster, das daraufhin eingeblendet wird, **Bellows College** als **Anzeigename** ein. 

    -   Geben Sie **BellowsCollege** als **Namen** ein.
    
    -   Geben Sie **bc** als **Präfix** ein.

    -   Klicken Sie unten auf der Seite auf **Speichern**.
    
    -   Klicken Sie im Popupfenster auf **Fertig**.

3.  Schließen Sie die Lösungserstellung ab.

    -   Klicken Sie nun auf die Dropdownliste **Herausgeber**, und wählen Sie den Herausgeber **Bellows College** aus, den Sie soeben erstellt haben.

    -   Vergewissern Sie sich, dass **Version** auf **1.0.0.0** gesetzt ist. 
    
    -   Klicken Sie auf **Erstellen**.

# <a name="exercise-2-add-existing-and-create-new-tables"></a>Übung 2: Vorhandene Tabellen hinzufügen und neue erstellen

**Ziel**: In dieser Übung fügen Sie die Standardtabelle „Kontakt“ hinzu und erstellen neue benutzerdefinierte Tabellen für Gebäude und Besuche in der Lösung. 

## <a name="task-1-add-existing-table"></a>Aufgabe 1: Vorhandene Tabelle hinzufügen

1.  Klicken Sie, um Ihre **Campusverwaltung**-Lösung, die Sie gerade erstellt haben, zu öffnen.

2.  Klicken Sie auf **Vorhandene hinzufügen**, und wählen Sie **Tabelle** aus.

3.  Suchen Sie **Kontakt**, und wählen Sie diese Option aus.

4.  Klicken Sie auf **Weiter**.

5.  Klicken Sie unter „Kontakt“ auf **Komponenten auswählen**.

6.  Wählen Sie die Registerkarte **Ansichten** aus, und wählen Sie die Ansicht **Aktive Kontakte** aus. Klicken Sie auf **Hinzufügen**.
    
7.  Klicken Sie erneut auf **Komponenten auswählen**.

8.  Wählen Sie die Registerkarte **Formulare** aus, und wählen Sie das Formular **Kontakt** aus.
    
9.  Klicken Sie auf **Hinzufügen**.

    > Sie sollten **1 Ansicht** und **1 Formular** ausgewählt haben. 
    
10.  Klicken Sie noch einmal auf **Hinzufügen**. Dadurch wird der neu erstellten Lösung die Tabelle „Kontakt“ mit der ausgewählten Ansicht und dem ausgewählten Formular hinzugefügt.

> Ihre Lösung sollte jetzt eine Tabelle enthalten: Kontakt.
    
## <a name="task-2-create-building-table"></a>Aufgabe Nr. 2: Tabelle „Gebäude“ erstellen

1.  In Ihrem Browser sollte weiterhin Ihre Campusverwaltung-Lösung geöffnet sein. Öffnen Sie andernfalls die Lösung wie folgt:

    * Melden Sie sich bei <https://make.powerapps.com> an (falls Sie nicht bereits angemeldet sind).
    
    * Wählen Sie **Lösungen** aus, und klicken Sie auf die Lösung **[Ihr Nachname] Campusverwaltung**, die Sie soeben erstellt haben, um sie zu öffnen.
          
2.  Tabelle „Gebäude“ erstellen

    -   Klicken Sie auf **Neu**, und wählen Sie **Tabelle** aus.
    
    -   Geben Sie **Gebäude** als **Anzeigename** ein. 
    
    -   Klicken Sie auf **Speichern**. Dadurch wird die Tabelle im Hintergrund bereitgestellt, während Sie damit beginnen können, weitere Tabellen und Spalten hinzuzufügen.

## <a name="task-3-create-visit-table-and-columns"></a>Aufgabe 3: Tabelle „Besuch“ und Spalten erstellen

Die Tabelle **Besuch** wird Informationen zu den Campusbesuchen enthalten, einschließlich des Gebäudes, des Besuchers und des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs. 

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

> Wir verwenden **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs immer die Ortszeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie in einer anderen Zeitzone angezeigt wird. 

1.  In Ihrem Browser sollte weiterhin Ihre Campusverwaltung-Lösung geöffnet sein. Öffnen Sie andernfalls die Lösung wie folgt:

    * Melden Sie sich bei <https://make.powerapps.com> an (falls Sie nicht bereits angemeldet sind).
    
    * Wählen Sie **Lösungen** aus, und klicken Sie auf die Lösung **[Ihr Nachname] Campusverwaltung**, die Sie soeben erstellt haben, um sie zu öffnen.

2. Tabelle „Besuch“ erstellen

   * Klicken Sie auf **Neu**, und wählen Sie **Tabelle** aus.
   
   * Geben Sie **Besuch** als **Anzeigename** ein. 
   
   * Klicken Sie auf **Speichern**. Dadurch wird die Tabelle im Hintergrund bereitgestellt, während Sie damit beginnen können, weitere Spalten hinzuzufügen.

3. Spalte „Geplanter Start“ erstellen

   * Wählen Sie die Tabelle **Besuch** aus.

   * Stellen Sie sicher, dass die Registerkarte **Spalten** ausgewählt ist, und klicken Sie auf **Spalte hinzufügen**.
   
   * Geben Sie **Geplanter Start** als **Anzeigename** ein.
   
   * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
   
   * Wählen Sie unter **Erforderlich** die Option **Erforderlich** aus.
   
   * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
   
   * Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
   
   * Klicken Sie auf **Fertig**.

4.  Spalte „Geplantes Ende“ erstellen

    * Klicken Sie auf **Spalte hinzufügen**.
    
    * Geben Sie **Geplantes Ende** als **Anzeigename** ein.
    
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    
    * Wählen Sie unter **Erforderlich** die Option **Erforderlich** aus.
    
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    
    * Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
    
    * Klicken Sie auf **Fertig**.
    
5.  Spalte „Tatsächlicher Start“ erstellen

    * Klicken Sie auf **Spalte hinzufügen**.
    
    * Geben Sie **Tatsächlicher Start** als **Anzeigename** ein.
    
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    
    * Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.
    
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    
    * Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
    
    * Klicken Sie auf **Fertig**.
    
6.  Spalte „Tatsächliches Ende“ erstellen

    * Klicken Sie auf **Spalte hinzufügen**.
    
    * Geben Sie **Tatsächliches Ende** als **Anzeigename** ein.
    
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    
    * Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.
    
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    
    * Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
    
    * Klicken Sie auf **Fertig**.
    
7.  Spalte „Code“ erstellen

    * Klicken Sie auf **Spalte hinzufügen**.
    
    * Geben Sie **Code** als **Anzeigename** ein.
    
    * Wählen Sie **AutoWert** als **Datentyp** aus.
    
    * Wählen Sie **Datumspräfixnummer** als **AutoWert-Typ** aus.
    
    * Klicken Sie auf **Fertig**.
    
8.  Klicken Sie auf **Tabelle speichern**.

# <a name="exercise-3-create-relationships"></a>Übung 3: Beziehungen erstellen

**Ziel**: In dieser Übung fügen Sie Beziehungen zwischen Tabellen hinzu.

## <a name="task-1-create-relationships"></a>Aufgabe Nr. 1: Beziehungen erstellen

1.  Vergewissern Sie sich, dass weiterhin die Tabelle **Besuch** der Lösung **Campusverwaltung** angezeigt wird. Navigieren Sie andernfalls dorthin.

2.  Erstellen der Beziehung „Besuch zu Kontakt“

    * Wählen Sie die Registerkarte **Beziehungen** aus.
    
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    
    * Wählen Sie **Kontakt** als **Verknüpft (Eins)** aus. 
    
    * Geben Sie **Besucher** als **Anzeigename der Nachschlagespalte** ein. 
    
    * Klicken Sie auf **Fertig**.
    
3.  Erstellen Sie die Beziehung „Besuch in Gebäude“

    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    
    * Wählen Sie **Gebäude** als **Verknüpft (Eins)** aus. 
    
    * Klicken Sie auf **Fertig**.
    
4.  Klicken Sie auf **Tabelle speichern**.

5.  Wählen Sie oben links **Zurück zu Lösungen** aus.

6.  Wählen Sie **Alle Anpassungen veröffentlichen** aus.

# <a name="exercise-4-import-data"></a>Übung 4: Daten importieren

**Ziel**: In dieser Übung importieren Sie Beispieldaten in die Dataverse-Datenbank.

## <a name="task-1-import-solution"></a>Aufgabe Nr. 1: Lösung importieren

In dieser Aufgabe importieren Sie eine Lösung, die den Power Automate-Flow enthält, der erforderlich ist, um den Datenimport abzuschließen.

1. Die Datei **DataImport_managed.zip** sollte auf Ihrem Desktop gespeichert sein. Laden Sie soweit noch nicht geschehen die [Datenimportlösung](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/DataImport_managed.zip?raw=true) herunter.

2. Melden Sie sich bei <https://make.powerapps.com> an.

3. Wählen Sie oben rechts Ihre Umgebung **[Ihre Initialen] Übung** aus, falls diese noch nicht ausgewählt ist.

4. Wählen Sie im linken Navigationsbereich **Lösungen** aus.

5. Klicken Sie auf **Importieren**, und klicken Sie dann auf **Durchsuchen**. Navigieren Sie zur Datei **DataImport_managed.zip** auf Ihrem Desktop, wählen Sie sie aus, und klicken Sie dann auf **Weiter**.

>   Möglicherweise wird die folgende Meldung angezeigt:
>
>   Es fehlen Abhängigkeiten. Installieren Sie die folgenden Lösungen, bevor Sie diese installieren...
>
>   Diese Meldung bedeutet entweder, dass das Datenmodell nicht vollständig ist, das Herausgeberpräfix nicht **bc** lautet oder für die Tabelle **Gebäude** und **Besuch** andere Namen als in den vorherigen Schritten angegeben sind.

6. Klicken Sie auf **Weiter**. Sie sollten aufgefordert werden, Verbindungen neu herzustellen. 

7. Erweitern Sie die Dropdownliste **Wählen Sie eine Verbindung aus**, und wählen Sie **+Neue Verbindung** aus.

8. Es wird ein neues Browserfenster oder eine neue Browserregisterkarte geöffnet. Wählen Sie **Erstellen** aus, wenn Sie aufgefordert werden, eine Verbindung herzustellen. Falls erforderlich, melden Sie sich an, um das Erstellen der Verbindung abzuschließen.

9. Schließen Sie die aktuelle Registerkarte, sodass Sie sich wieder auf der vorherigen Registerkarte **Lösung importieren** befinden.

10. Vergewissern Sie sich, dass die Verbindung, die Sie gerade erstellt haben, ausgewählt ist. Wenn diese Verbindung nicht angezeigt wird, klicken Sie auf **Aktualisieren**, um die Liste der Verbindungen zu aktualisieren. 

11. Klicken Sie auf **Import** (Importieren).

12. Warten Sie, bis der Importvorgang abgeschlossen ist.

## <a name="task-2-import-data"></a>Aufgabe Nr. 2: Daten importieren  

1. Öffnen Sie die **Datenimport**-Lösung.

2. Überprüfen Sie den **Status** des Flows **Daten importieren**.

3. Wenn **Status** auf **Aus** gesetzt ist, klicken Sie auf die Schaltfläche **[...]** neben **Daten importieren**, und wählen Sie dann **Einschalten** aus.

   > **Wichtig:** Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie, ob die von Ihnen erstellten Tabellen und Spalten mit den obigen Anweisungen übereinstimmen.

4. Öffnen Sie die Komponente **Daten importieren**. Power Automate wird auf einer neuen Registerkarte geöffnet. 

5. Klicken Sie auf **Los geht's**, wenn ein Popupfenster eingeblendet wird. 

6. Klicken Sie auf **Ausführen**, und klicken Sie dann auf **Flow ausführen**, wenn Sie dazu aufgefordert werden.

7. Klicken Sie auf **Fertig**.

8. Warten Sie, bis die Ausführung der Flow-Instanz abgeschlossen ist. Sie können die Tabelle **28-tägiger Ausführungsverlauf** aktualisieren, um zu sehen, wann der Flow ausgeführt wurde. 

    > Der Zweck dieses Flows bestand darin, Beispieldaten für die nächsten Labs zu generieren. In der nächsten Aufgabe werden Sie überprüfen, ob der Datenimport erfolgreich war. 

## <a name="task-3-verify-data-import"></a>Aufgabe 3: Datenimport überprüfen

1. Navigieren Sie zurück zur vorherigen Power Apps-Registerkarte. Klicken Sie in dem Popupfenster auf **Fertig**. 

2. Wählen Sie in der linken Navigationsleiste **Lösungen** aus, und öffnen Sie Ihre **Campusverwaltung**-Lösung.

2. Klicken Sie, um die Tabelle **Besuch** zu öffnen, und wählen Sie dann die Registerkarte **Daten** aus.

3. Klicken Sie oben rechts auf **Aktive Besuche**, um die Ansichtsauswahl anzuzeigen, und wählen Sie dann **Alle Spalten** aus. Dadurch wird die Ansicht geändert, die zum Anzeigen der Besuchsdaten verwendet wird. 

    > Wenn Sie aufgrund geringerer Auflösung **Aktive Besuche** nicht sehen, sollte an derselben Stelle ein Augensymbol angezeigt werden.

    > Wenn der Import erfolgreich war, sollte eine Liste der Besuchszeilen angezeigt werden.

4. Klicken Sie auf einen beliebigen Wert in der Spalte **Gebäude**, und überzeugen Sie sich, dass in einem separaten Fenster das Gebäudeformular geöffnet wird. 

5. Schließen Sie das kürzlich gestartete Fenster.

6. Klicken Sie auf einen beliebigen Wert in der Spalte **Besucher** (möglicherweise müssen Sie dazu nach rechts scrollen), und überzeugen Sie sich, dass in einem separaten Fenster das Kontaktformular geöffnet wird.

7. Schließen Sie das kürzlich gestartete Fenster.

# <a name="challenges"></a>Herausforderungen

* Würden Sie in Betracht ziehen, die *Termin*-Aktivität als Teil der Lösung zu verwenden? Was würde sich ändern?
* Wie lässt sich erzwingen, dass das geplante Ende hinter dem geplanten Start liegt? 
* Wie lässt sich Unterstützung für mehrere Meetings während eines einzelnen Besuchs hinzufügen?
* Wie lässt sich der Gebäudezugang nicht nur für externe Kontakte, sondern auch für interne Mitarbeiter absichern?
* Wie lässt sich für Besuche in bestimmten Gebäude vorgeben, dass dazu eine Genehmigung der Verwaltung erforderlich ist? Was würde der Genehmigungsprozess im Datenmodell ändern?

