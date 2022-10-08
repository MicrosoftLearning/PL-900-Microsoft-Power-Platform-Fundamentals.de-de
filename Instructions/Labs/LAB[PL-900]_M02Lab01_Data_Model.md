---
lab:
  title: 'Lab 1: Datenmodellierung'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# <a name="lab-1-data-modeling"></a>Lab 1: Datenmodellierung

## <a name="scenario"></a>Szenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In this lab you will access your environment, create a Microsoft Dataverse database, and create a solution to track your changes. You will also create a data model to support the following requirements:

- R1: Nachverfolgen von Informationen zu geplanten Campusbesuchen

- R2 – Aufzeichnen der grundlegende Informationen, um die Besucher zu identifizieren und nachzuverfolgen

- R3 – Planen, Aufzeichnen und Verwalten von Besuchen

Zum Abschluss importieren Sie Beispieldaten in Microsoft Dataverse.

## <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

- Refer to the <bpt id="p1">[</bpt>data model document<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png)</ept> for the metadata description (tables and relationships). You can hold CTRL+click or right click the link to open the data model document in a new window.
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

### <a name="task-1-import-the-visitsxlsx-file"></a>Aufgabe \#1: Importieren der Datei „Visits.xlsx“

In dieser Aufgabe importieren Sie die „Visit“-Daten aus einer Excel-Datei.

1. You should have the <bpt id="p1">**</bpt>Visits.xlsx<ept id="p1">**</ept> file stored on your Desktop. Download <bpt id="p1">[</bpt>Visits.xlsx<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx)</ept> if you do not.

2. Wenn Sie noch nicht angemeldet sind, melden Sie sich bei [https://make.powerapps.com](https://make.powerapps.com/) an.

3. Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

4. Erweitern Sie mithilfe der Navigation auf der linken Seite **Dataverse**, und wählen Sie **Tabellen** aus.

5. Suchen und öffnen Sie die Tabelle **Visit**, die Sie in der vorherigen Übung erstellt haben.

6. Wählen Sie oben über das Menü den Dropdownpfeil neben **Importieren** die Option **Daten aus Excel importieren** aus.

7. Wählen Sie in dem angezeigten Menü **Hochladen** aus.

8. Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus.

9. Klicken Sie auf **Spalten zuordnen** (Hinweis: Vielleicht müssen Sie nach rechts scrollen, um die Option „Spalten zuordnen“ anzuzeigen).

10. Ordnen Sie die Spalten wie unten beschrieben zu:

| Visit-Spalten| Quellwerte |
| - | - |
| Tatsächliches Ende| tatsächliches Ende |
| Tatsächlicher Start| tatsächlicher Start |
| Code| code |
| Name| name |
| Geplantes Ende| geplantes Ende |
| Geplanter Start| geplanter Start |

11. Lassen Sie die restlichen Felder auf **Nicht festgelegt**.

12. Klicken Sie in der oberen rechten Ecke des Bildschirms auf **Änderungen speichern**.

13. Überprüfen Sie auf dem Bildschirm **Daten importieren**, ob der Zuordnungsstatus besagt, dass die Zuordnung erfolgreich war („Die Zuordnung war erfolgreich“).

14. Klicken Sie in der oberen rechten Ecke auf **Importieren**, um den Datenimport abzuschließen.

Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet.

15. Klicken Sie auf **X**, um das Dialogfeld zum Importieren von Daten zu schließen.

### <a name="task-2-verify-data-import"></a>Aufgabe \#2: Datenimport überprüfen

1. Nachdem Ihre Daten importiert wurden, verwenden Sie die Navigation auf der linken Seite des Bildschirms, um die Tabelle **Besuch** erneut auszuwählen.

2. Stellen Sie sicher, dass die importierten Daten im Abschnitt **Ansehen von Spalten und Daten** angezeigt werden.

Glückwunsch, Sie haben erfolgreich eine neue Tabelle erstellt und Daten importiert.