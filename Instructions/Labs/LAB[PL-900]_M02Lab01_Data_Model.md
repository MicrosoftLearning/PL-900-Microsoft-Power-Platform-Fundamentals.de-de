---
lab:
  title: 'Lab 1: Datenmodellierung'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# <a name="lab-1-data-modeling"></a>Lab 1: Datenmodellierung

## <a name="scenario"></a>Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab greifen Sie auf Ihre Umgebung zu, erstellen eine Microsoft Dataverse-Datenbank und eine Lösung zum Nachverfolgen Ihrer Änderungen. Sie erstellen auch ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

- R1: Nachverfolgen von Informationen zu geplanten Campusbesuchen

- R2 – Aufzeichnen der grundlegende Informationen, um die Besucher zu identifizieren und nachzuverfolgen

- R3 – Planen, Aufzeichnen und Verwalten von Besuchen

Zum Abschluss importieren Sie Beispieldaten in Microsoft Dataverse.

## <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

- Beschreibungen zu den Metadaten (Tabellen und Beziehungen) finden Sie im [Datenmodelldokument](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Sie können die STRG-Taste gedrückt halten oder mit der rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.
- Erstellen der Tabelle „Visit“
- Besuchsdaten mithilfe eines Excel-Arbeitsblatts importieren

## <a name="prerequisites"></a>Voraussetzungen

- Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**

## <a name="things-to-consider-before-you-begin"></a>Vor dem Beginn zu beachtende Dinge

- Benennungskonventionen – Namen sorgfältig eingeben.

## <a name="exercise-1-create-new-table"></a>Übung 1: Erstellen einer neuen Tabelle

**Ziel**: In dieser Übung erstellen Sie eine neue benutzerdefinierte Tabelle für Besuche.

### <a name="task-1-create-visit-table-and-columns"></a>Aufgabe \#1: Tabelle „Visit“ und Spalten erstellen

Die Tabelle **Visit** wird Informationen zu den Campusbesuchen enthalten, einschließlich der Besucher*innen sowie des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs.

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

> Wir nutzen **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs immer die Lokalzeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie aus einer anderen Zeitzone angezeigt wird.

1. Melden Sie sich bei [https://make.powerapps.com](https://make.powerapps.com/) an (falls Sie nicht bereits angemeldet sind).

1. Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

1. Erweitern Sie mithilfe der Navigation auf der linken Seite **Dataverse**, und wählen Sie **Tabellen** aus.

1. Klicken Sie auf **+ Neue Tabelle**.

1. Geben Sie **Besuch** als **Anzeigename** ein.

1. Klicken Sie auf **Speichern**.

1. Wählen Sie im Abschnitt **Schema** die Option **Spalten** aus.

1. Spalte „Geplanter Start“ erstellen

    - Wählen Sie **+ Neue Spalte** aus.

    - Geben Sie **Geplanter Start** als **Anzeigename** ein.

    - Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    - Wählen Sie für **Erforderlich** **Eingabe erforderlich** aus.

    - Erweitern Sie **Erweiterte Optionen**.

    - Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus.

    - Klicken Sie auf **Speichern**.

1. Spalte „Geplantes Ende“ erstellen

    - Klicken Sie auf **+ Neue Spalte**.

    - Geben Sie **Geplantes Ende** als **Anzeigename** ein.

    - Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    - Wählen Sie für **Erforderlich** **Eingabe erforderlich** aus.

    - Erweitern Sie **Erweiterte Optionen**.

    - Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus.

    - Klicken Sie auf **Speichern**.

1. Spalte „Tatsächlicher Start“ erstellen

    - Klicken Sie auf **+ Neue Spalte**.

    - Geben Sie **Tatsächlicher Start** als **Anzeigename** ein.

    - Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    - Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.

    - Erweitern Sie **Erweiterte Optionen**.

    - Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus.

    - Klicken Sie auf **Speichern**.

1. Spalte „Tatsächliches Ende“ erstellen

    - Klicken Sie auf **+ Neue Spalte**.

    - Geben Sie **Tatsächliches Ende** als **Anzeigename** ein.

    - Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    - Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.

    - Erweitern Sie **Erweiterte Optionen**.

    - Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus.

    - Klicken Sie auf **Speichern**.

1. Spalte „Code“ erstellen

    - Klicken Sie auf **+ Neue Spalte**.

    - Geben Sie **Code** als **Anzeigename** ein.

    - Wählen Sie **AutoWert** als **Datentyp** aus.

    - Wählen Sie **Datumspräfixnummer** als **AutoWert-Typ** aus.

    - Klicken Sie auf **Speichern**.

1. Erstellen einer Nachschlagespalte für „Besucher“

    - Klicken Sie auf **+ Neue Spalte**.

    - Geben Sie **Besuch** als **Anzeigename** ein.

    - Wählen Sie **Lookup** (Nachschlagen) als **Datentyp** aus.

    - Wählen Sie **Kontakt** für die **Verknüpfte Tabelle** aus.

    - Erweitern Sie **Erweiterte Optionen**.

    - Geben Sie **visitor_id** für **den Beziehungsnamen** ein.

    - Klicken Sie auf **Speichern**.

## <a name="exercise-2-import-data"></a>Übung 2: Daten importieren

**Ziel**: In dieser Übung importieren Sie Beispieldaten in die Dataverse-Datenbank.

### <a name="task-11-load-excel-file-to-onedrive"></a>Aufgabe 1.1: Laden einer Excel-Datei in OneDrive

1. Die Datei **Visits.xlsx** sollte auf Ihrem Desktop gespeichert sein. Laden Sie [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) herunter, wenn dies nicht der Fall ist.

2. Wenn Sie noch nicht angemeldet sind, melden Sie sich bei [https://make.powerapps.com](https://make.powerapps.com/) an.

3. Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

4. Klicken Sie in der oberen linken Ecke auf das Waffel-Menü, um die Anwendungen zu ändern, und wählen Sie **OneDrive** aus. (Es kann einen Moment dauern, bis OneDrive eingerichtet ist. Klicken Sie auf „Ihr OneDrive ist fertig.“, wenn die Meldung auf dem Bildschirm angezeigt wird.)

5. Klicken Sie im oberen Menü auf **Hochladen**, und wählen Sie **Dateien** aus.

6. Suchen Sie die Datei **Visits.xlsx**, und wählen Sie sie aus. Klicken Sie dann auf **Öffnen**.

 **Hinweis:** Diese Datei befindet sich im Ordner **Alle Dateien** auf Ihrem Computer.
 
### <a name="task-12-create-a-dataflow"></a>Aufgabe 1.2: Erstellen eines Dataflows

1. Wenn Sie noch nicht angemeldet sind, melden Sie sich bei [https://make.powerapps.com](https://make.powerapps.com/) an.

2. Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

3. Erweitern Sie mithilfe der Navigation auf der linken Seite **Dataverse**, und wählen Sie **Tabellen** aus.

4. Suchen und öffnen Sie die Tabelle **Visit**, die Sie in der vorherigen Übung erstellt haben.

5. Wählen Sie oben über das Menü den Dropdownpfeil neben **Importieren** die Option **Daten importieren** aus.

6. Wählen Sie im Dialogfeld **Datenquelle auswählen** die Option **Excel-Arbeitsmappe** aus.

7. Wählen Sie die Option **Mit Datei verknüpfen** aus. Klicken Sie auf **OneDrive durchsuchen**. Melden Sie sich bei der entsprechenden Aufforderung mit Ihren Microsoft 365-Anmeldeinformationen an.

8. Wählen Sie die **Visits.xlsx**-Datei aus, die in OneDrive hochgeladen wurde, und klicken Sie auf **Auswählen**.

9. Klicken Sie auf **Weiter**.

10. Aktivieren Sie unter **Daten auswählen** das Kontrollkästchen neben der Excel-Arbeitsmappe **Visits**.

11. Klicken Sie auf **Weiter**. Navigieren Sie nicht von dieser Seite weg.

12. Klicken Sie auf **Weiter**.

13. Wählen Sie im Abschnitt **Tabellen zuordnen** unter **Einstellungen laden** die Option **In vorhandene Tabelle laden** aus.

14. Wählen Sie im Dropdownmenü **Zieltabelle** den Tabellennamen aus, der mit **crXXX_visit** beginnt (wobei XXX eine zufällige Gruppe von Buchstaben und Zahlen ist).

15. Auf der Seite **Column mapping**: Ordnen Sie die Spalten den entsprechenden Zielspalten zu.

| Zielspalten| Quellwerte |
| - | - |
| crxxx_ActualEnd| tatsächliches Ende |
| crxxx_ActualStart| tatsächlicher Start |
| crxxx_Code| code |
| crxxx_Name| name |
| crxxx_ScheduledEnd| geplantes Ende |
| crxxx_ScheduledStart| geplanter Start |

16. Klicken Sie auf **Weiter**.

17. Wählen Sie **Manuell aktualisieren** aus.

18. Klicken Sie auf **Veröffentlichen**.

**Hinweis:** Es kann mehrere Minuten dauern, bis Ihre Daten in Ihre Tabelle importiert werden. Machen Sie sich keine Sorgen, wenn ein paar Fehler angezeigt werden. Das ist normal und hat keine Auswirkungen auf den Rest des Kurses.

### <a name="task-3-verify-data-import"></a>Aufgabe 3: Datenimport überprüfen

1. Nachdem Ihre Daten importiert wurden, verwenden Sie die Navigation auf der linken Seite des Bildschirms, um die Tabelle **Besuch** erneut auszuwählen.

2. Stellen Sie sicher, dass die importierten Daten im Abschnitt **Ansehen von Spalten und Daten** angezeigt werden.

Glückwunsch, Sie haben erfolgreich eine neue Tabelle erstellt und Daten importiert.
