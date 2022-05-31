---
lab:
  title: 'Lab 1: Datenmodellierung'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: c3ea362eebf9156f069a9ab8635859e6186c1626
ms.sourcegitcommit: 0118c25a230425d0ccba16e6c3922053ee07c183
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2022
ms.locfileid: "144810907"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Modul 2: Einführung in Microsoft Dataverse

# <a name="scenario"></a>Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab greifen Sie auf Ihre Umgebung zu, erstellen eine Microsoft Dataverse-Datenbank und eine Lösung zum Nachverfolgen Ihrer Änderungen. Sie erstellen auch ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

-   R1: Nachverfolgen von Informationen zu geplanten Campusbesuchen

-   R2 – Aufzeichnen der grundlegende Informationen, um die Besucher zu identifizieren und nachzuverfolgen

-   R3 – Planen, Aufzeichnen und Verwalten von Besuchen

Zum Abschluss importieren Sie Beispieldaten in Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

* eine Lösung und einen Herausgeber erstellen.
* sowohl neue als auch vorhandene Komponenten hinzufügen, die zur Erfüllung der Anwendungsanforderungen erforderlich sind. Beschreibungen zu den Metadaten (Tabellen und Beziehungen) finden Sie im [Datenmodelldokument](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png). Sie können die STRG-Taste gedrückt halten oder mit der rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.
* Erstellen der Tabelle „Visit“
* Besuchsdaten mithilfe eines Excel-Arbeitsblatts importieren

## <a name="prerequisites"></a>Voraussetzungen:

-   Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**

## <a name="things-to-consider-before-you-begin"></a>Bevor Sie beginnen, sollten Sie Folgendes berücksichtigen:

-   Benennungskonventionen – Namen sorgfältig eingeben.

# <a name="exercise-1-create-new-table"></a>Übung \#1: Erstellen einer neuen Tabelle

**Ziel**: In dieser Übung erstellen Sie eine neue benutzerdefinierte Tabelle für Besuche. 

## <a name="task--1-create-visit-table-and-columns"></a>Aufgabe \#1: Tabelle „Besuch“ und Spalten erstellen

Die Tabelle **Visit** wird Informationen zu den Campusbesuchen enthalten, einschließlich der Besucher*innen sowie des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs.

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

>   Wir verwenden **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs immer die Lokalzeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie aus einer anderen Zeitzone angezeigt wird.

1.  Melden Sie sich bei <https://make.powerapps.com> an (falls Sie nicht bereits angemeldet sind).

2.  Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung** sumgebung aus, falls diese noch nicht ausgewählt ist.

3.  Erweitern Sie mithilfe der Navigation auf der linken Seite Dataverse, und wählen Sie „Tabellen“ aus.

4.  Klicken Sie auf **Neue Tabelle**.

5.  Geben Sie **Besuch** als **Anzeigename** ein.

6.  Klicken Sie auf **Erstellen**. Dadurch wird die Tabelle im Hintergrund bereitgestellt, während Sie damit beginnen können, weitere Spalten hinzuzufügen.

7.  Spalte „Geplanter Start“ erstellen

    1.  Sie sollten sich auf der Seite „Spalten“ der Tabelle „Besuch“ befinden.

    2.  Stellen Sie sicher, dass die Registerkarte **Spalten** ausgewählt ist, und klicken Sie auf **Spalte hinzufügen**.

    3.  Geben Sie **Geplanter Start** als **Anzeigename** ein.

    4.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    5.  Wählen Sie unter **Erforderlich** die Option **Erforderlich** aus.

    6.  Erweitern Sie den Abschnitt **Erweiterte Optionen**.

    7.  Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.

    8.  Klicken Sie auf **Fertig**.

8.  Spalte „Geplantes Ende“ erstellen

    1.  Klicken Sie auf **Spalte hinzufügen**.

    2.  Geben Sie **Geplantes Ende** als **Anzeigename** ein.

    3.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    4.  Wählen Sie unter **Erforderlich** die Option **Erforderlich** aus.

    5.  Erweitern Sie den Abschnitt **Erweiterte Optionen**.

    6.  Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.

    7.  Klicken Sie auf **Fertig**.

9.  Spalte „Tatsächlicher Start“ erstellen

    1.  Klicken Sie auf **Spalte hinzufügen**.

    2.  Geben Sie **Tatsächlicher Start** als **Anzeigename** ein.

    3.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    4.  Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.

    5.  Erweitern Sie den Abschnitt **Erweiterte Optionen**.

    6.  Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.

    7.  Klicken Sie auf **Fertig**.

10. Spalte „Tatsächliches Ende“ erstellen

    1.  Klicken Sie auf **Spalte hinzufügen**.

    2.  Geben Sie **Tatsächliches Ende** als **Anzeigename** ein.

    3.  Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.

    4.  Behalten Sie unter **Erforderlich** die Einstellung **Optional** bei.

    5.  Erweitern Sie den Abschnitt **Erweiterte Optionen**.

    6.  Wählen Sie unter **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.

    7.  Klicken Sie auf **Fertig**.

11. Spalte „Code“ erstellen

    1.  Klicken Sie auf **Spalte hinzufügen**.

    2.  Geben Sie **Code** als **Anzeigename** ein.

    3.  Wählen Sie **AutoWert** als **Datentyp** aus.
    
    4.  Wählen Sie **Datumspräfixnummer** als **AutoWert-Typ** aus.

    5.  Klicken Sie auf **Fertig**.

12. Erstellen einer Nachschlagespalte für „Besucher“

    1.  Klicken Sie auf **Spalte hinzufügen**.

    2.  Geben Sie **Besuch** als **Anzeigename** ein.

    3.  Wählen Sie **Lookup** (Nachschlagen) als **Datentyp** aus.

    4.  Wählen Sie **Kontakt** für die **Verknüpfte Tabelle** aus.

    5.  Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    
    6.  Geben Sie **visitor_id** für **den Beziehungsnamen** ein.
    
    7.  Klicken Sie auf **Fertig**.

13. Klicken Sie unten rechts auf **Tabelle speichern**.

# <a name="exercise-2-import-data"></a>Übung \#2: Daten importieren

**Ziel**: In dieser Übung importieren Sie Beispieldaten in die Dataverse-Datenbank.

## <a name="task-1-import-the-visitsxls-file"></a>Aufgabe \#1: Importieren der Datei „Visits.xls“.

In dieser Aufgabe importieren Sie die „Visit“-Daten aus einer Excel-Datei. 

1.  Die Datei **Visits.xls** sollte auf Ihrem Desktop gespeichert sein. Laden Sie [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) herunter, wenn dies nicht der Fall ist.

2.  Wenn Sie noch nicht angemeldet sind, melden Sie sich bei <https://make.powerapps.com> an.

3.  Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung** sumgebung aus, falls diese noch nicht ausgewählt ist.

4.  Erweitern Sie mithilfe der Navigation auf der linken Seite **Dataverse**, und wählen Sie „Tabellen“ aus.
    >   Dies wird möglicherweise als Daten \> Tabellen auf Ihrem Bildschirm angezeigt. 

5.  Suchen und öffnen Sie die Tabelle **Visit**, die Sie in der vorherigen Übung erstellt haben.

6.  Wählen Sie mit dem Menü oben den Dropdownpfeil neben **Daten** aus, wählen Sie den Pfeil neben **Daten abrufen** aus, und wählen Sie dann **Daten aus Excel abrufen** aus.

7.  Wählen Sie in dem angezeigten Menü **Hochladen** aus.

8.  Suchen Sie die zuvor heruntergeladene Datei **Visits.xls**, und wählen Sie sie aus. *(Beachten Sie, dass der Upload ein bis zwei Minuten dauern kann. Machen Sie sich keine Sorgen, wenn Sie eine Meldung erhalten, dass Zuordnungsfehler vorhanden sind. Diese beheben wir als Nächstes.)*

9. Wählen Sie **Spalten zuordnen** aus.

10. Ordnen Sie die Spalten wie unten beschrieben zu:

    | Datenbankspalten von „Visit“ | Quellwerte   |
    |------------------|-----------------|
    | Tatsächliches Ende       | Tatsächliches Ende      |
    | Tatsächlicher Start     | Tatsächlicher Start    |
    | Code             | Code            |
    | Name             | Name            |
    | Geplantes Ende    | Geplantes Ende   |
    | Geplanter Start  | Geplanter Start |

11. Lassen Sie die restlichen Felder auf **Nicht festgelegt**.

12. Wählen Sie in der oberen rechten Ecke des Bildschirms **Änderungen speichern** aus.

13. Überprüfen Sie auf dem Bildschirm **Daten importieren**, ob der Zuordnungsstatus besagt, dass die Zuordnung erfolgreich war.

14. Wählen Sie in der oberen rechten Ecke **Importieren** aus, um den Datenimport abzuschließen.

**Hinweis:** *Es kann mehrere Minuten dauern, bis Ihre Daten in Ihre Tabelle importiert werden. Machen Sie sich keine Sorgen, wenn ein paar Fehler angezeigt werden. Das ist normal und hat keine Auswirkungen auf den Rest des Kurses.*

## <a name="task-2-verify-data-import"></a>Aufgabe \#2: Datenimport überprüfen

1.  Nachdem Ihre Daten importiert wurden, verwenden Sie die Navigation auf der linken Seite des Bildschirms, um die Tabelle **Besuch** erneut auszuwählen.

2.  Beachten Sie, dass viele Registerkarten für die „Visit“-Tabelle vorhanden sind. Dazu gehören beispielsweise „Cikynns“, Beziehungen, Geschäftsregeln und Ansichten. 

3.  Wählen Sie die Registerkarte **Daten** für die Tabelle „Visit“ aus. Diese befindet sich unter **Tabellen** \> **Visit**

3.  Stellen Sie sicher, dass Datensätze in Ihrer Tabelle vorhanden sind. Sie können die Ansicht ändern, indem Sie den Ansichtsnamen oben rechts auswählen und in **Alle Spalten** ändern. 

Glückwunsch, Sie haben erfolgreich eine neue Tabelle erstellt und Daten importiert.
