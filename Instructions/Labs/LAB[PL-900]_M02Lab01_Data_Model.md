---
lab:
  title: 'Lab 1: Datenmodellierung'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Lab 1: Datenmodellierung

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Tenant ist ein Testtenant; er kann nach Abschluss des Kurses nicht verwendet oder aufgerufen werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Campusgebäuden. Viele der Lehrer und Administratoren am Bellow College müssen an Veranstaltungen teilnehmen und Artikel kaufen. Historisch gesehen war die Nachverfolgung dieser Ausgaben eine Herausforderung. 

Die Campusverwaltung möchte ihr Spesenabrechnungssystem modernisieren, indem den Mitarbeitern eine digitale Möglichkeit zum Melden von Ausgaben an die Hand gegeben wird. 

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit die Mitarbeiter des Bellows College Ausgaben verwalten können.

In diesem Lab erstellen Sie ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

- R1: Nachverfolgen von Informationen zu geplanten Campusbesuchen

- R2: Aufzeichnen der grundlegenden Informationen, um die Besucher*innen zu identifizieren und nachzuverfolgen

- R3: Planen, Aufzeichnen und Verwalten von Besuchen

Zum Abschluss importieren Sie Beispieldaten in Microsoft Dataverse.

## Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

- Beschreibungen zu den Metadaten (Tabellen und Beziehungen) finden Sie im [Datenmodelldokument](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus Management.png). Sie können die STRG-Taste gedrückt halten und mit der linken oder rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.

- Spesentabelle erstellen

- Fügen Sie einige Beispieldaten hinzu. 

### Voraussetzungen

- Beendigung von **Modul 1 Lab 0 – Lab-Umgebung überprüfen**

Vor dem Beginn zu beachtende Dinge

- Namenskonventionen: Geben Sie Namen sorgfältig ein.

## Übung 1: Erstellen einer neuen Tabelle

**Ziel**: In dieser Übung erstellen Sie eine neue benutzerdefinierte Tabelle für Ausgaben.

### Aufgabe Nr. 1: Kostentabelle und Spalten erstellen

Die **Tabelle "Ausgaben** " enthält Informationen zu einzelnen Ausgaben, die ein Mitarbeiter übermitteln kann, einschließlich Grund, Typ, Datum und Betrag.

1. Melden Sie sich bei https://make.powerapps.com an, falls Sie nicht bereits angemeldet sind.

1. Vergewissern Sie sich im Menü **Umgebung** oben rechts, dass Ihre Übungsumgebung **Dev One** ausgewählt ist.

1. Wählen Sie links im Navigationsbereich die Option **Tabellen** aus.

1. Wählen Sie **+ Neue Tabelle** aus und wählen Sie **Erweiterte Eigenschaften festlegen** aus.

1. Geben Sie "Ausgabe" für **den Anzeigenamen**ein.

1. Wählen Sie **Speichern**.

1. Wählen Sie im Abschnitt **Schema** die Option **Spalten** aus.

### Spalte "Spesendatum erstellen"

1. Wählen Sie **+ Neue Spalte** aus.

1. Geben Sie das Spesendatum für **den Anzeigenamen**ein.

1. Wählen Sie **"Datum nur** für **Datentyp**" aus.

1. Ändern Sie **Erforderlich** in **Eingabe erforderlich**.

1. Erweitern Sie **Erweiterte Optionen**.

1. Wählen Sie in **der Zeitzonenanpassung**"Nur **Datum"** aus.

    >**Hinweis:** Wir verwenden **das Datumsverhalten nur** , um Datumsinformationen aufzuzeichnen, da sich das Datum des Besuchs nicht ändern sollte, wenn er aus einer anderen Zeitzone angezeigt wird.

1. Wählen Sie **Speichern**.

### Spalte "Spesentyp erstellen"

1. Wählen Sie **+ Neue Spalte** aus.

1. Geben Sie den Spesentyp für **den Anzeigenamen**ein.

1. Wählen Sie **"Auswahl** " für **"Datentyp**" aus.

1. Wählen Sie in **"Erforderlich**" die Option "Optional" **aus**.

1. Festlegen der **Synchronisierung mit globaler Auswahl** auf **"Ja" (empfohlen)**

1. **Wählen Sie in "Diese Option synchronisieren" mit** dem Feld "Spesentyp" ** aus**.

1. Stellen Sie das Feld " **Standardauswahl** " auf **"Keine"** ein.

1. Wählen Sie **Speichern**.

### Spalte "Spesenzweck erstellen"

1. Wählen Sie **+ Neue Spalte** aus.

1. Geben Sie "Spesenzweck" für **den Anzeigenamen ein**.

1. Wählen Sie **"Auswahl** " für **"Datentyp**" aus.

1. Wählen Sie in **"Erforderlich**" die Option "Optional" **aus**.

1. Festlegen der **Synchronisierung mit globaler Auswahl** auf **"Ja" (empfohlen)**

1. **Wählen Sie in "Diese Option synchronisieren" mit** dem **Feld "Spesenzweck" aus**.

1. Legen Sie das **Feld "Standard** " auf **"Keine"** fest.

1. Wählen Sie **Speichern**.

### Spalte "Elementbeschreibung erstellen"

1. Wählen Sie **+ Neue Spalte** aus.

1. Geben Sie die Elementbeschreibung für **den Anzeigenamen ein**.

1. Wählen Sie **für den Datentyp &gt; "Nur-Text** **" mehrere Textzeilen**aus.

1. Wählen Sie **Speichern**.

### Spalte "Spesenbetrag erstellen"

1. Wählen Sie **+ Neue Spalte** aus.

1. Geben Sie den Spesenbetrag für **den Anzeigenamen**ein.

1. Wählen Sie **"Währung** " für **den Datentyp**aus.

1. Wählen Sie **Speichern**.

 
## Übung 2: Daten eingeben

**Ziel**: In dieser Übung geben Sie einige Beispieldaten manuell in die neue Tabelle ein. 

### Aufgabe Nr. 1: Ändern Sie die angezeigten Spalten

1. Wenn Sie noch nicht angemeldet sind, melden Sie sich bei https://make.powerapps.com an.

1. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

1. Wählen Sie links im Navigationsbereich die Option **Tabellen** aus.

1. Öffnen Sie die Tabelle **Ausgabe**, die Sie in der vorherigen Übung erstellt haben.

1. Wählen Sie neben der **Spalte "Name** " **+26 weitere **aus.

1. Wählen Sie im daraufhin angezeigten Menü die folgenden Spalten aus.

    1. Spesendatum

    2. Spesenzweck 

    3. Spesentyp

    4. Ausgabenbetrag

    5. Item Description

1. Wählen Sie die Schaltfläche **Speichern** aus.

## Aufgabe Nr. 2: Fügen Sie einen Beispieldatensatz hinzu.

1. Wählen Sie den **Pfeil** neben **"Bearbeiten"** aus. Wählen Sie im nun angezeigten Menü " **Bearbeiten" auf der neuen Registerkarte**aus.

1. Geben Sie in der **Spalte "Name** " **John Doe** ein.

1. Geben Sie in der **Spalte "Spesendatum** " **"xxx"** ein.

1. Wählen Sie im **Spesenzweck** **"Konferenz "** aus.

1. Wählen Sie in der Spalte **"Spesentyp"** die **Option "Reise" **aus.

1. Geben Sie in der **Spalte "Spesenbetrag** " **750,00** ein.

1. Geben Sie in der **Elementbeschreibung**eine kurze Beschreibung ein.

1. Drücken Sie die Tabulatorschaltfläche, um zur nächsten Zeile zu wechseln und **den Datensatz zu speichern** .

Glückwunsch, Sie haben erfolgreich eine neue Tabelle erstellt und Daten importiert.


