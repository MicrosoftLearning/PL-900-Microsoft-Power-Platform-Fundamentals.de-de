---
lab:
  title: 'Bonus Lab: Erstellen einer Canvas-App mit Copilot'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Bonus Lab: Erstellen einer Canvas-App mit Copilot

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Tenant ist ein Testtenant; er kann nach Abschluss des Kurses nicht verwendet oder aufgerufen werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

In dieser Übung verwenden Sie Copilot, um eine neue Canvas-Anwendung für die Protokollierung von Besuchen zu erstellen. 

## Weiterführende Schritte des Lab

Wir werden uns beim Entwerfen der App an nachstehende Gliederung halten:

- Beschreiben der App, die Sie erstellen möchten

- Verwenden von Copilot zum Ändern der unterstützenden Tabellenstruktur

 ## Voraussetzungen

- Beendigung von **Modul 1 Lab 0 – Lab-Umgebung überprüfen**

## Übung 1: Verwenden Sie Copilot, um eine Anwendung für Universitätsbesuche zu erstellen.

**Ziel**: In dieser Übung erstellen Sie eine Canvas-App, indem Sie eine Verbindung mit einer Tabelle „Campus visits“ herstellen.

### Aufgabe \#1: Erstellen der ursprünglichen Anwendung

1. Navigieren Sie zu https://make.powerapps.com.

2. Möglicherweise müssen Sie sich erneut authentifizieren. Wählen Sie dazu **Anmelden** aus, und befolgen Sie die Anweisungen, falls erforderlich.

3. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

4. Geben Sie den folgenden Text in das Feld **Beschreiben Sie die Anwendung, die Sie erstellen möchten** ein. Erstellen Sie eine Anwendung, die Besuche auf einem Universitätscampus protokolliert. 

5. Wählen Sie die Schaltfläche **Los** aus.

Copilot beginnt mit der Erstellung einer Tabellenstruktur zur Unterstützung Ihrer Anwendung. 

> **WICHTIG:** Wenn Sie generative KI verwenden, erhalten Sie nicht immer dieselben genauen Ergebnisse. Es ist möglich, dass Ihre Tabelle nicht genau mit der Tabelle übereinstimmt, die für einen anderen Kursteilnehmer erstellt wurde. 

6. Geben Sie in das Feld **Beschreiben Sie, was geändert werden soll** den Text ein: Fügen Sie zwei Spalten hinzu, „Time in“ und „Time out“. Beide sollten Datums- und Uhrzeitfelder sein.  

7. Klicken Sie auf die Schaltfläche **Los** oder drücken Sie die **EINGABETASTE**. 

8. Scrollen Sie zur Seite der Tabelle, und überprüfen Sie, ob die Spalten **Time in** und **Time out** erstellt wurden. 

Da wir die Zeit des Zutritts und Verlassens der Besucher protokollieren, benötigen wir keine anderen Datumsfelder für Besuche mehr. 

9. Suchen Sie das Feld **Besuchsdatum** (oder ähnliches Feld) und geben Sie im Feld **Beschreiben Sie, was geändert werden soll**den Text „Feld für Besuchsdatum entfernen“ ein. 

10. Wählen Sie die Schaltfläche **Los** aus. 

11. Entfernen Sie alle zusätzlichen Datumsfelder, die möglicherweise zusätzlich zu **Time in** und **Time out** vorhanden sind. 

Zunächst wurde ein Feld wie das Feld **Zweck** mit einem Textdatentyp formatiert. Wir lassen es von Copilot in ein Dropdownmenü (Auswahl) ändern. 

12. Geben Sie in das Feld **Beschreiben Sie, was geändert werden soll** folgenden Text ein: Ändern Sie das Feld „Zweck“ in ein Auswahlmenü mit den folgenden Optionen: Campus-Tour, Karrieremesse, Treffen mit Professor, Studienberatung, Sonstiges. 

13. Wählen Sie die Schaltfläche **Los** aus. 

14. Da wir auch die Gebäudenummer erfassen möchten, geben Sie im Feld **Beschreiben Sie, was sie geändert werden soll** Folgendes ein: Fügen Sie eine Gebäudespalte hinzu. 

15. Wählen Sie die Schaltfläche **Los** aus. 

16. Sobald Sie mit Ihrer Tabelle zufrieden sind, wählen Sie die Schaltfläche **App erstellen** aus. 

17. Bei Bedarf wählen Sie auf dem Bildschirm **Willkommen bei Power Apps Studio** **Nicht mehr anzeigen**, und wählen Sie dann **Überspringen** aus. 

![Screenshot der soeben erstellten App](media/bonus-lab-copilot-01.png)

Herzlichen Glückwunsch, Sie haben Copilot zum Erstellen einer neuen App verwendet. 
