---
lab:
  title: "Lab\_4: Erstellen einer automatisierten Lösung"
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>Lab 4: Erstellen einer automatisierten Lösung

## <a name="scenario"></a>Szenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab erstellen Sie einen Power Automate-Flow, um einem Besucher per E-Mail mitzuteilen, wenn ein Besuch geplant ist.

## <a name="high-level-lab-steps"></a>Weiterführende Schritte des Lab

Sie müssen die folgenden Anforderungen implementieren, um das Projekt abzuschließen.

- Kontakte müssen per E-Mail benachrichtigt werden, wenn ein Besuch geplant ist.

## <a name="prerequisites"></a>Voraussetzungen

- Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**
- Abschluss von **Modul 2 Lab 1: Datenmodellierung**
- Abschluss von **Modul 2 Lab 3: Erstellen einer modellgesteuerten App**
- Der Kontakt „John Doe“ wurde mit einer aufgefüllten persönlichen E-Mail-Adresse erstellt.

## <a name="exercise-1-create-visit-notification-flow"></a>Übung 1: Einen Besuchsbenachrichtigungsfluss erstellen

<bpt id="p1">**</bpt>Objective:<ept id="p1">**</ept> In this exercise, you will create a Power Automate flow that implements the requirement. The visitor should be sent an email that includes the unique code assigned to the visit when a visit is created.

### <a name="task-1-create-a-flow"></a>Aufgabe \#1: Erstellen eines Flows

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

3.  Wählen Sie im linken Navigationsbereich **Flows** aus.

4.  Wenn Sie dazu aufgefordert werden, wählen Sie **Erste Schritte** aus.

5.  Klicken Sie auf **Neuer Flow**, und wählen Sie **Automatisierter Cloud-Flow** aus.

6.  Geben Sie „Visit Notification“ (Besuchsbenachrichtigung) als **Flownamen** ein.

7.  Suchen Sie unter **Flowtrigger auswählen** nach **Dataverse**.

8.  Wählen Sie den Trigger **Wenn eine Zeile hinzugefügt, geändert oder gelöscht wird** aus, und klicken Sie dann auf **Erstellen**.

9.  Füllen Sie die Triggerbedingungen für den Flow auf:

    1.  Wählen Sie **Hinzugefügt** für **Änderungstyp** aus.

    2.  Wählen Sie **Besuche** als **Tabellenname** aus.

    3.  Wählen Sie im **Bereich** **Organisation** aus

    4.  On the trigger step, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>. Rename this trigger <bpt id="p1">**</bpt>"When a visit is added"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Aufgabe \#2: Erstellen eines Schritts zum Abrufen der Besucherzeile

1.  Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus.

2.  Suchen Sie nach **Dataverse**.

3.  Wählen Sie die Aktion **Zeile nach ID abrufen** aus.

4.  Wählen Sie **Kontakte** als **Tabellenname** aus.

5.  Campusbesucher werden derzeit auf Papier erfasst.

6.  Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

7.  On this action, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>.
        Rename this action <bpt id="p1">**</bpt>"Get the Visitor"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Aufgabe \#3: Erstellen eines Schritts zum Senden einer E-Mail an den Besucher

1.  Click <bpt id="p1">**</bpt>+ New step<ept id="p1">**</ept>. This is the step that will send an email to the visitor.

2.  Suchen Sie nach *E-Mail*, wählen Sie den Connector **Office 365 Outlook** und die Aktion **E-Mail senden (V2)** aus.

3.  Wenn Sie aufgefordert werden, die „Nutzungsbedingungen für diese Aktion zu akzeptieren“, klicken Sie auf **Akzeptieren**.

4.  Wählen Sie **Dynamischen Inhalt hinzufügen** unter dem Feld **An** aus. 
    
5.  Wählen Sie das Feld **E-Mail** aus der Liste dynamischer Inhalte aus.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  Geben Sie **Ihr geplanter Besuch am Bellows College** in das Feld **Betreff** ein.

7.  Geben Sie den folgenden Text in **E-Mail-Text** ein:

>   Dynamic content needs to be placed where fields are named in brackets. It is recommended to copy &amp; paste all text first and then add dynamic content in the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Highlight the <bpt id="p1">**</bpt>{First Name}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>First Name<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>Get the Visitor<ept id="p2">**</ept> step.

9.  Highlight the <bpt id="p1">**</bpt>{Scheduled Start}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled Start<ept id="p1">**</ept> field <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

10.  Highlight the <bpt id="p1">**</bpt>{Scheduled End}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled End<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

11.  Klicken Sie auf **Speichern**.

Leave this flow tab open for the next task. You flow should look approximately like the following:

![Beispiel für Flowschritte.](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>Aufgabe \#4: Flow überprüfen und aktivieren

1.  Öffnen Sie im Browser eine neue Registerkarte, und navigieren Sie zu <https://make.powerapps.com>.

2.  Wählen Sie oben rechts Ihre **[Ihre Initialen] Übung**sumgebung aus, falls diese noch nicht ausgewählt ist.

3.  Klicken Sie auf **Apps**, und wählen Sie die **Bellows Campus-Verwaltungs-App** aus, die Sie zuvor erstellt haben.

3.  Lassen Sie diese Browserregisterkarte geöffnet, und navigieren Sie wieder zurück zu der vorherigen Registerkarte mit Ihrem Flow.

4.  On the command bar, click <bpt id="p1">**</bpt>Test<ept id="p1">**</ept>. Select <bpt id="p1">**</bpt>Manually<ept id="p1">**</ept> and then click <bpt id="p2">**</bpt>Test<ept id="p2">**</ept>.

5.  Navigieren Sie zur Browserregisterkarte mit geöffneter modellgesteuerter App. 

6.  Wählen Sie links im Navigationsbereich die Option **Besuche** aus.

6. Klicken Sie auf die Schaltfläche **+ Neu**, um einen neuen **Besuch**sdatensatz hinzuzufügen.

7. Vervollständigen Sie den Besuchsdatensatz wie folgt:

    -   **Name:** Testbesuch

    -   **Besucher:** John Doe

    -   **Geplanter Start:** Morgen um 8:00 Uhr

    -   **Geplantes Ende:** Morgen um 9:00 Uhr

8. Wählen Sie **Speichern und schließen** aus.

9. Navigate to the browser tab with your flow test running. After a short delay, you should see the flow running. This is where you can catch any issues in the flow or confirm that it ran successfully.

After a short delay, you should see an email in your inbox, since you populated John Doe's email as your personal email. Note that it may go to your Junk Email folder.

## <a name="challenges"></a>Herausforderungen

- Play around with the formatting on the email. How can you make it more professional looking?