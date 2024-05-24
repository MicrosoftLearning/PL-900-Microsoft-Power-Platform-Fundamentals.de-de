---
lab:
  title: "Lab\_4: Erstellen einer automatisierten Lösung"
  module: 'Module 4: Get Started with Power Automate'
---

# Lab 4: Erstellen einer automatisierten Lösung

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Tenant ist ein Testtenant; er kann nach Abschluss des Kurses nicht verwendet oder aufgerufen werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Campusgebäuden. Viele der Lehrer und Administratoren am Bellow College müssen an Veranstaltungen teilnehmen und Artikel kaufen. Historisch gesehen war die Nachverfolgung dieser Ausgaben eine Herausforderung. 

Die Campusverwaltung möchte ihr Spesenabrechnungssystem modernisieren, indem den Mitarbeitern eine digitale Möglichkeit zum Melden von Ausgaben an die Hand gegeben wird. 

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit die Mitarbeiter des Bellows College Ausgaben verwalten können. 

In dieser Übung erstellen Sie einen Power Automate-Flow, um eine Kopie der Spesenabrechnung per E-Mail zu senden, wenn sie eine neue Spesenabrechnung erstellen.

## Weiterführende Schritte des Lab

Sie müssen die folgenden Anforderungen implementieren, um das Projekt abzuschließen.

- Mitarbeiter müssen eine E-Mail erhalten, wenn eine Spesenabrechnung übermittelt wird. 

### Voraussetzungen

- Beendigung von **Modul 1 Lab 0 – Lab-Umgebung überprüfen**

## Übung 1: Erstellen des Benachrichtigungsflows "Spesenabrechnung"

**Ziel**: In dieser Übung erstellen Sie einen Power Automate-Flow, der die Anforderung implementiert. 

### Aufgabe Nr. 1: Erstellen eines Flows

1. Navigieren Sie zu https://make.powerapps.com.

1. Möglicherweise müssen Sie sich erneut authentifizieren. Wählen Sie dazu **Anmelden** aus, und befolgen Sie die Anweisungen, falls erforderlich.

1. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

1. Wählen Sie im linken Navigationsbereich **Flows** aus.

1. Wenn Sie dazu aufgefordert werden, wählen Sie **Erste Schritte** aus.

1. Wählen Sie **+ Neuer Flow** und dann **Automatisierter Cloud-Flow** aus.

1. Geben Sie die Spesenbenachrichtigung für **den Namen des Flow **ein.

1. Suchen Sie unter **Flowtrigger auswählen** nach Dataverse

1. Wählen Sie den Trigger, **wenn eine Zeile hinzugefügt, geändert oder gelöscht wird**, und dann **Erstellen** aus.

1. Füllen Sie die Triggerbedingungen für den Flow auf:

    1. Wählen Sie **Hinzugefügt** für **Änderungstyp** aus.
    
    1. Spesenabrechnungen **für** Tabellennamen auswählen ****

    1. Wählen Sie im **Bereich** **Organisation** aus

    1. Klicken Sie im Triggerschritt auf die Schaltfläche mit den Auslassungspunkten ( **...** ), und wählen Sie **Umbenennen** aus. Umbenennen des Triggerschritts `When an Expense Report is added` 

Dies ist eine gute Vorgehensweise, damit Sie und andere Flow-Editoren den Zweck des Schritts erkennen können, ohne tiefer in die Details gehen zu müssen.

### Aufgabe Nr. 2: Erstellen eines Schritts zum Abrufen der Zeile "Spesenabrechnung"

1. Wählen Sie **+ Neuer Schritt**aus. In diesem Schritt werden Spesenabrechnungsinformationen abgerufen, einschließlich der E-Mail-Adresse.

1. Suchen Sie nach Dataverse

1. Wählen Sie die Aktion **Zeile nach ID abrufen** aus.

1. **Benutzer **als** Tabellenname auswählen **

1. Wählen Sie das Feld **Zeilen-ID** aus. Beachten Sie, dass ein Fenster geöffnet wird, in dem Sie **dynamische Inhalte** oder **Ausdrücke** auswählen können.

1. Fügen Sie im Feld **Zeilen-ID** den Eintrag **Besitzer (Wert)** in der Liste für **dynamische Inhalte** aus. In diesem Schritt suchen Sie den Besitzer für die Zeile "Spesenabrechnung", die erstellt wurde, um diesen Flow auszulösen. 

1. Wählen Sie in der Aktion **Zeile nach ID abrufen** die Auslassungspunkte ( **...** ) aus, und wählen Sie dann **Umbenennen** aus. Benennen Sie diese Aktion in „Den Besitzer abrufen“ um

Dies ist eine gute Vorgehensweise, damit Sie und andere Flow-Editoren den Zweck des Schritts erkennen können, ohne tiefer in die Details gehen zu müssen.

### Aufgabe 3: Erstellen eines Schritts zum Senden einer E-Mail zur Bestätigung der Übermittlung einer Spesenabrechnung

1. Wählen Sie **+ Neuer Schritt**aus. Dies ist der Schritt, der eine E-Mail an die Person sendet, die eine Spesenabrechnung übermittelt hat.

1. Suchen Sie nach einem Mail, wählen Sie die Aktion **„ein E-Mail verschicken“ (V2)** aus** dem **Office 365 Outlook-Connector aus.

1. Wenn Sie aufgefordert werden, die „Nutzungsbedingungen für diese Aktion zu akzeptieren“, klicken Sie auf **Ich stimme zu**.

1. Wählen Sie das Feld **bis** aus und geben Sie Ihre persönliche E-Mail-Adresse ein. (Es gibt viele Möglichkeiten, wie wir eine E-Mail-Adresse dynamisch auffüllen können, wobei wir sie aber für diese Übung manuell zuweisen werden.)  

1. Geben Sie im **Feld "Betreff** " wurde Ihre Spesenabrechnung eingestellt.

1. Geben Sie den folgenden Text in **E-Mail-Text** ein:

Dynamischer Inhalt muss dort platziert werden, wo Feldnamen in Klammern angegeben sind. Es wird empfohlen, zuerst den gesamten Text zu kopieren und einzufügen und dann dynamischen Inhalt an den richtigen Stellen hinzuzufügen.

    Dear {First Name},
    
    Thank you for submitting your expense report for the total amount of {Report Total Amount} with a due date of {Report Due Date}.
    
     
    Best regards,
    Campus Administration
    Bellows College

1. Markieren Sie den Text **{First Name}** (Vorname). Ersetzen Sie es durch das Feld **Vorname** aus dem Schritt **Besitzer abrufen**.

1. Markieren Sie den **Text {Gesamtbetrag eingeben}** . Ersetzen Sie ihn durch das Feld **Gesamtbetrag melden** aus dem Schritt **wenn ein Spesenabrechnungsschritt übermittelt wird**.

1. Markieren Sie den **Text {Fälligkeitsdatum eingeben**). Ersetzen Sie ihn durch das Feld **Fälligkeitsdatum melden** aus dem Schritt **Senden einer Spesenabrechnung**.

1. Wählen Sie **Speichern**.

Lassen Sie die Registerkarte dieses Flows für die nächste Aufgabe geöffnet. Die Datei sollte folgendermaßen aussehen:

![Screenshot des gerade erstellten Flows](media/lab-4-create-an-automated-solution-01.png)

### Aufgabe Nr. 4: Flow überprüfen und aktivieren

1. Öffnen Sie im Browser eine neue Registerkarte, und navigieren Sie zu https://make.powerapps.com.

1. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

1. Wählen Sie **Apps**aus, und öffnen Sie die **Spesenverfolgungs-App**.

1. Lassen Sie diese Browserregisterkarte geöffnet, und navigieren Sie wieder zurück zu der vorherigen Registerkarte mit Ihrem Flow.

1. Wählen Sie in der Befehlsleiste **Test** aus. Wählen Sie **Manuell** aus, und wählen Sie dann **Testen** aus.

1. Navigieren Sie zur Browserregisterkarte mit geöffneter modellgesteuerter App.

1. Wählen Sie links in der Webseitennavigation die Option **Spesenabrechnung** aus.

1. Wählen Sie die **Schaltfläche +Neu** aus, um einen neuen **Spesenabrechnungsdatensatz** hinzuzufügen.

1. Füllen Sie den **Spesenabrechnungseintrag** wie folgt aus:

    - **Berichtsname:** Testbericht

    - **Fälligkeitsdatum melden:** Morgen 

1. Wählen Sie die Schaltfläche **Speichern und schließen** aus.

1. Navigieren Sie zur Browserregisterkarte, auf der Ihr Flowtest ausgeführt wird. Nach einer kurzen Verzögerung sollte der Flow ausgeführt werden. Hier können Sie alle Probleme im Flow abfangen oder bestätigen, dass er erfolgreich ausgeführt wurde.

Nach kurzer Verzögerung sollte eine E-Mail in Ihrem Posteingang angezeigt werden. 

>**Hinweis:** Beachten Sie, dass sie möglicherweise in Ihrem Junk-E-Mail-Ordner landen kann.
