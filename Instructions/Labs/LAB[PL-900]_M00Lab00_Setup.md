---
lab:
    title: 'Lab: Lab-Umgebung überprüfen'
    module: 'Modul 0: Einführung in den Kurs'
---

Modul 0: Einführung in den Kurs
=================================

Szenario
--------

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Modul-0-Lab werden Sie einen Power Platform-Testmandanten erhalten und auf das Power Platform Admin Center zugreifen. Im Admin Center erstellen Sie dann Ihre **Übungsumgebung**, in der Sie den größten Teil Ihrer Lab-Arbeiten erledigen werden.

## Übung 1 – Einrichtung

### Aufgabe 1 – Beziehen Ihres Microsoft Power Platform-Testmandanten

1. Kopieren Sie Ihre **Microsoft 365-Anmeldeinformationen** vom autorisierten Lab-Hoster.

2. Navigieren Sie zu <https://powerapps.microsoft.com>, und klicken Sie auf **Kostenlos einsteigen**.

3. Geben Sie unter **Los geht's** die E-Mail-Adresse aus Ihren Microsoft 365-Anmeldeinformationen in das Textfeld mit der entsprechenden Aufschrift ein (**Geben Sie Ihre geschäftliche E-Mail-Adresse ein**).

4. Eine Meldung wird eingeblendet, die besagt, dass Sie über ein Konto bei Microsoft verfügen. Wählen Sie **Anmelden** aus.

5. Geben Sie das Kennwort ein, dass Sie vom autorisierten Lab-Hoster erhalten haben. 

6. Wählen Sie **Ja** aus, um angemeldet zu bleiben.

7. Geben Sie Ihre vollständigen Kontoinformationen ein und wählen Sie **Erste Schritte**, um sich für Ihre Testversion von Microsoft Power Platform anzumelden.  

### Aufgabe 2 – Erstellen der Umgebung

1. Greifen Sie auf <https://admin.powerplatform.microsoft.com> zu, und melden Sie sich mit Ihren Microsoft 365-Anmeldeinformationen an, falls Sie erneut dazu aufgefordert werden.

2. Wählen Sie **Umgebungen** aus, und klicken Sie auf **+Neu**.

    - Geben Sie als **Name** Folgendes ein: **[Meine Initialen] Übung**. (Beispiel: AJ Übung).
    
    - Wählen Sie als **Typ** die Option **Testversion** aus (Achtung: Wählen Sie nicht die Option „Testversion (abonnementbasiert)“ aus!).
    
    - Stellen Sie den Umschalter **Datenbank für diese Umgebung erstellen?** auf **Ja**.
    
    - Lassen Sie alle anderen Auswahlmöglichkeiten auf ihren Standardwerten, und klicken Sie auf **Weiter**.
    
    - Lassen Sie auf der nächsten Registerkarte alle Auswahlmöglichkeiten auf ihren Standardwerten, und klicken Sie auf **Speichern**.

3. Ihre **Übungsumgebung** sollte nun in der Liste der Umgebungen angezeigt werden. 

    > Ihre Umgebung kann einige Minuten zur Bereitstellung benötigen. Falls erforderlich, aktualisieren Sie die Seite.

# Übung Nr. 2: Ein Power Apps-Portal bereitstellen

**Ziel:** Das Bereitstellen eines Power Apps-Portals kann einige Zeit dauern. In dieser Übung erstellen Sie Ihr Power Apps-Portal in Ihrer Umgebung, damit der Bereitstellungsprozess gestartet werden kann. Sie verwenden dieses Portal in einem späteren Lab.

## Aufgabe 1: Erstellen des Power Apps-Portals

1.  Anmelden bei <https://make.powerapps.com>

2.  Wenn die oben rechts angezeigte **Umgebung** nicht Ihre Übungsumgebung ist, klicken Sie, um Ihre Umgebung auszuwählen.

3.  Klicken Sie auf der Startseite unter **Eigene App erstellen** auf das Panel **Portal aus leerer Vorlage**

    > Wenn diese Option nicht angezeigt wird, versuchen Sie, die Ansicht zu verkleinern.

4.  Geben Sie neue Portaldetails an

    -   Geben Sie **```Bellows College Visitors```** als **Name** des Portals ein.

    -   Geben Sie eine eindeutige URL an; **etwas**.powerappsportals.com (wenn der Name bereits verwendet wird, wählen Sie einen anderen)

    -   Wählen Sie eine **Sprache** für das Basisportal aus

    -   Klicken Sie auf **Erstellen**.

    > Der Portal-Bereitstellungsprozess dauert zwischen 30 und 45 Minuten. Sie müssen nicht warten, da dieser Vorgang fortgesetzt wird, während Sie mit dem nächsten Modul fortfahren.
