---
lab:
  title: 'Lab 1: Datenmodellierung'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Lab 1: Datenmodellierung

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Mandant ist ein Testmandant; er kann nach Abschluss des Kurses nicht verwendet oder aufgerufen werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab erstellen Sie ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

- R1: Nachverfolgen von Informationen zu geplanten Campusbesuchen

- R2: Aufzeichnen der grundlegenden Informationen, um die Besucher*innen zu identifizieren und nachzuverfolgen

- R3: Planen, Aufzeichnen und Verwalten von Besuchen

Zum Abschluss importieren Sie Beispieldaten in Microsoft Dataverse.

Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

- Beschreibungen zu den Metadaten (Tabellen und Beziehungen) finden Sie im [Datenmodelldokument](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Sie können die STRG-Taste gedrückt halten und mit der linken oder rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.
- Tabelle „Besuch“ erstellen
- Importieren von Besuchsdaten mithilfe eines Excel-Arbeitsblatts


## Voraussetzungen

- Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**

Vor dem Beginn zu beachtende Dinge

- Benennungskonventionen – Namen sorgfältig eingeben.

Übung 1: Erstellen einer neuen Tabelle

**Ziel**: In dieser Übung erstellen Sie eine neue benutzerdefinierte Tabelle für Besuche.

Aufgabe #1: Tabelle „Visit“ und Spalten erstellen

Die Tabelle **Visit** wird Informationen zu den Campusbesuchen enthalten, einschließlich der Besucher*innen sowie des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs.

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

1.  Melden Sie sich bei <https://make.powerapps.com> an, falls Sie nicht bereits angemeldet sind. 

1.  Stellen Sie im Menü **Umgebung** oben rechts sicher, dass Ihre **Übungsumgebung** ausgewählt ist. 

1.  Wählen Sie links im Navigationsbereich die Option **Tabellen** aus.

1.  Wählen Sie **+ Neue Tabelle** und dann **+ Neue Tabelle** aus. 

1.  Geben Sie für **Anzeigename** `Visit` ein.

1.  Wählen Sie **Speichern** aus. 

1.  Wählen Sie im Abschnitt **Schema** die Option **Spalten** aus. 

# Spalte „Geplanter Start“ erstellen

1.  Wählen Sie **+ Neue Spalte** aus. 

1.  Geben Sie für **Anzeigename** `Scheduled Start` ein. 

1.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus. 

1.  Ändern Sie **Erforderlich** in **Eingabe erforderlich**. 

1.  Erweitern Sie **Erweiterte Optionen**. 

1.  Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus. 

    > **Hinweis:** Wir nutzen **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs immer die Lokalzeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie aus einer anderen Zeitzone angezeigt wird. 

1.  Wählen Sie **Speichern** aus. 

# Spalte „Geplantes Ende“ erstellen

1.  Wählen Sie **+ Neue Spalte** aus. 

1.  Geben Sie für **Anzeigename** `Scheduled End` ein.

1.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

1.  Wählen Sie für **Erforderlich** **Eingabe erforderlich** aus.

1.  Erweitern Sie **Erweiterte Optionen**.

1.  Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus.

1.  Wählen Sie **Speichern** aus. 

# Spalte „Tatsächlicher Start“ erstellen

1.  Wählen Sie **+ Neue Spalte** aus. 

1.  Geben Sie für **Anzeigename** `Actual Start` ein.

1.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

1.  Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.

1.  Erweitern Sie **Erweiterte Optionen**.

1.  Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus. 

1.  Wählen Sie **Speichern** aus. 

# Spalte „Tatsächliches Ende“ erstellen

1.  Wählen Sie **+ Neue Spalte** aus.

1.  Geben Sie **Tatsächliches Ende** als **Anzeigename** ein.

1.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

1.  Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.

1.  Erweitern Sie **Erweiterte Optionen**.

1.  Wählen Sie in der **Zeitzonenanpassung** die Option **Zeitzonenunabhängig** aus.

1.  Wählen Sie **Speichern** aus.

# Spalte „Code“ erstellen

1.  Wählen Sie **+ Neue Spalte** aus.

1.  Geben Sie für **Anzeigename** `Code` ein.

1.  Wählen Sie **AutoWert** als **Datentyp** aus.

1.  Wählen Sie **Datumspräfixnummer** als **AutoWert-Typ** aus.

1.  Wählen Sie **Speichern** aus. 

# Erstellen einer Nachschlagespalte für „Besucher“

1.  Wählen Sie **+ Neue Spalte** aus.

1.  Geben Sie für **Anzeigename** `Visitor` ein.

1.  Wählen Sie **Lookup** (Nachschlagen) als **Datentyp** aus. 

1.  Wählen Sie **Kontakt** für die **Verknüpfte Tabelle** aus. 

1.  Erweitern Sie **Erweiterte Optionen**. 

1.  Geben Sie `visitor_id` für **den Beziehungsnamen** ein. 

1.  Wählen Sie **Speichern** aus.


Übung 2: Daten importieren

**Ziel**: In dieser Übung importieren Sie Beispieldaten in die Dataverse-Datenbank.

### Aufgabe \#1: Laden einer Excel-Datei in OneDrive

1.  Die Datei **Visits.xlsx** sollte auf Ihrem virtuellen Computer unter **C:/LabFiles** gespeichert sein. Laden Sie [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) herunter, wenn dies nicht der Fall ist.

2.  Wenn Sie noch nicht angemeldet sind, melden Sie sich bei [https://make.powerapps.com](https://make.powerapps.com/) an. 

3.  Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

4.  Klicken Sie in der oberen linken Ecke auf das Waffel-Menü, um die Anwendungen zu ändern, und wählen Sie **OneDrive** aus. (Es kann einen Moment dauern, bis OneDrive eingerichtet ist. Wählen Sie **Ihr OneDrive ist fertig** aus, wenn die Meldung auf dem Bildschirm angezeigt wird.)

5.  Klicken Sie im oberen Menü auf **Hochladen**, und wählen Sie **Dateien** aus.

6.  Suchen Sie die Datei **Visits.xlsx**, und wählen Sie sie aus. Klicken Sie dann auf **Öffnen**.

    > **Hinweis:** Diese Datei befindet sich im Ordner **Alle Dateien** auf Ihrem Computer.


### Aufgabe \#2: Erstellen eines Dataflows

1.  Melden Sie sich bei <https://make.powerapps.com> an, falls Sie nicht bereits angemeldet sind. 

2.  Stellen Sie im Menü **Umgebung** oben rechts sicher, dass Ihre **Übungsumgebung** ausgewählt ist. 

3.  Wählen Sie links im Navigationsbereich die Option **Tabellen** aus. 

4.  Öffnen Sie die Tabelle **Visit**, die Sie in der vorherigen Übung erstellt haben. 

5.  Wählen Sie oben im Menü **Importieren** > **Daten importieren** aus.

6.  Wählen Sie im Dialogfeld **Datenquelle auswählen** die Option **Excel-Arbeitsmappe** aus.

7.  Wählen Sie die Option **Mit Datei verknüpfen** aus. Wählen Sie **OneDrive durchsuchen** aus. Melden Sie sich bei der entsprechenden Aufforderung mit Ihren Microsoft 365-Anmeldeinformationen an. Konfigurieren Sie den Browser so, dass Popupelemente immer zugelassen werden. 

8.  Wählen Sie die Datei **Visits.xlsx** aus, die in der vorherigen Aufgabe auf OneDrive hochgeladen wurde. 

9.  Wählen Sie **Weiter** aus. 

10. Aktivieren Sie auf dem Bildschirm **Power Query** > **Daten auswählen** die Excel-Arbeitsmappe **Visits** (Besuche). 

11. Wählen Sie **Weiter** aus. Navigieren Sie nicht von dieser Seite weg.

12. Wählen Sie **Weiter** aus. 

13. Wählen Sie im Abschnitt **Zuordnen von Tabellen** unter **Einstellungen laden** die Option **In vorhandene Tabelle laden** aus. 

14. Wählen Sie im Dropdownmenü **Zieltabelle** den Tabellennamen **crXXX_visit** aus (wobei XXX eine zufällige Gruppe von Buchstaben und Zahlen ist).

15. Ordnen Sie die Spalten im Abschnitt **Spaltenzuordnung** den entsprechenden Zielspalten zu:

    | Zielspalten  | Quellwerte   |
    |:---------------------|:----------------|
    | crxxx_ActualEnd      | tatsächliches Ende      |
    | crxxx_ActualStart    | tatsächlicher Start    |
    | crxxx_Code           | code            |
    | crxxx_Name           | name            |
    | crxxx_ScheduledEnd   | geplantes Ende   |
    | crxxx_ScheduledStart | geplanter Start |

16. Wählen Sie **Weiter** aus. 

17. Wählen Sie **Manuell aktualisieren** aus. 

18. Klicken Sie auf **Veröffentlichen**. 

    > **Hinweis:** Es kann mehrere Minuten dauern, bis Ihre Daten in Ihre Tabelle importiert werden. Machen Sie sich keine Sorgen, wenn ein paar Fehler angezeigt werden. Das ist normal und hat keine Auswirkungen auf den Rest des Kurses.


Aufgabe 3: Datenimport überprüfen

1.  Nachdem Ihre Daten importiert wurden, verwenden Sie die Navigation auf der linken Seite des Bildschirms, um **Tabellen** auszuwählen und die Tabelle **Visit** zu öffnen.

2.  Stellen Sie sicher, dass die importierten Daten im Abschnitt **Ansehen von Spalten und Daten** angezeigt werden.

Glückwunsch, Sie haben erfolgreich eine neue Tabelle erstellt und Daten importiert.

