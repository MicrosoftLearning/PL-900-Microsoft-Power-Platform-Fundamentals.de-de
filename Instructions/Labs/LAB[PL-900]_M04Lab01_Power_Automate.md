---
lab:
  title: "Lab\_4: Erstellen einer automatisierten Lösung"
  module: 'Module 4: Get Started with Power Automate'
---

# Lab 4: Erstellen einer automatisierten Lösung

**WWL-Mandanten – Nutzungsbedingungen** Wenn Ihnen im Rahmen einer Präsenzschulung ein Mandant zugewiesen worden ist, steht dieser für Praxislabs innerhalb der Präsenzschulung zur Verfügung. Mandanten sollten nicht für Zwecke außerhalb von Praxislabs freigegeben oder verwendet werden. Der in diesem Kurs verwendete Mandant ist ein Testmandant; er kann nach Abschluss des Kurses nicht verwendet oder erreicht werden und ist nicht für Erweiterungen geeignet. Mandanten dürfen nicht in ein kostenpflichtiges Abonnement konvertiert werden. Die im Rahmen dieses Kurses erworbenen Mandanten verbleiben im Eigentum der Microsoft Corporation, und wir behalten uns das Recht vor, jederzeit auf Mandanten zuzugreifen und diese zurückzuziehen. 

## Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Lab erstellen Sie einen Power Automate-Flow, um einem Besucher per E-Mail mitzuteilen, wenn ein Besuch geplant ist.

## Weiterführende Schritte des Lab

Sie müssen die folgenden Anforderungen implementieren, um das Projekt abzuschließen.

- Kontakte müssen per E-Mail benachrichtigt werden, wenn ein Besuch geplant ist.

## Voraussetzungen

- Beendigung von **Modul 1 Lab 0 – Lab-Umgebung überprüfen**
- Abschluss von **Modul 2 Lab 1: Datenmodellierung**
- Abschluss von **Modul 2 Lab 3: Erstellen einer modellgesteuerten App**
- Der Kontakt „John Doe“ wurde mit einer aufgefüllten persönlichen E-Mail-Adresse erstellt.

## Übung 1: Einen Besuchsbenachrichtigungsfluss erstellen

**Ziel**: In dieser Übung erstellen Sie einen Power Automate-Flow, der die Anforderung implementiert. Dem Besucher sollte eine E-Mail gesendet werden, die den eindeutigen Code enthält, der dem Besuch zugewiesen ist, wenn ein Besuch erstellt wird.

### Aufgabe \#1: Erstellen eines Flows

1.  Navigieren Sie zu `https://make.powerapps.com`.

2.  Möglicherweise müssen Sie sich erneut authentifizieren. Wählen Sie dazu **Anmelden** aus, und befolgen Sie die Anweisungen, falls erforderlich.

3.  Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

4.  Wählen Sie im linken Navigationsbereich **Flows** aus.

5.  Wenn Sie dazu aufgefordert werden, wählen Sie **Erste Schritte** aus.

6.  Wählen Sie **+ Neuer Flow** und dann **Automatisierter Cloud-Flow** aus.

7.  Geben Sie `Visit Notification` als **Flowname** ein.

8.  Suchen Sie unter **Flowtrigger auswählen** nach `Dataverse`.

9.  Wählen Sie den Trigger **Wenn eine Zeile hinzugefügt, geändert oder gelöscht wird** aus, und wählen Sie dann **Erstellen** aus.

10.  Füllen Sie die Triggerbedingungen für den Flow auf:

    1.  Wählen Sie **Hinzugefügt** für **Änderungstyp** aus.

    2.  Wählen Sie **Besuche** als **Tabellenname** aus.

    3.  Wählen Sie im **Bereich** **Organisation** aus

    4.  Klicken Sie im Triggerschritt auf die Schaltfläche mit den Auslassungspunkten ( **...** ), und wählen Sie **Umbenennen** aus. Umbenennen des Triggerschritts `When a Visit is added` 

        Dies ist eine gute Vorgehensweise, damit Sie und andere Flow-Editoren den Zweck des Schritts erkennen können, ohne tiefer in die Details gehen zu müssen.


### Aufgabe \#2: Erstellen eines Schritts zum Abrufen der Besucherzeile

1.  Wählen Sie **+ Neuer Schritt**aus. In diesem Schritt werden Besucherinformationen abgerufen, einschließlich E-Mail-Adressen.

2.  Suchen Sie nach `Dataverse`.

3.  Wählen Sie die Aktion **Zeile nach ID abrufen** aus.

4.  Wählen Sie **Kontakte** als **Tabellenname** aus.

5.  Wählen Sie das Feld **Zeilen-ID** aus. Beachten Sie, dass ein Fenster geöffnet wird, in dem Sie **dynamische Inhalte** oder **Ausdrücke** auswählen können.

6.  Wählen Sie im Feld **Zeilen-ID** den Eintrag **Besucher (Wert)** aus der Liste **Dynamische Inhalte** aus. In diesem Schritt suchen Sie den Kontakt für die Zeile „Visit“, die erstellt wurde, um diesen Flow auszulösen. Da die E-Mail-Adresse Teil der Tabelle „Contact“ ist, benötigen Sie diese Informationen, um die E-Mail an die Besucher*innen zu senden.

7.  Wählen Sie in der Aktion **Zeile nach ID abrufen** die Auslassungspunkte ( **...** ) aus, und wählen Sie dann **Umbenennen** aus. Umbenennen dieser Aktion `Get the Visitor`
 
    Dies ist eine gute Vorgehensweise, damit Sie und andere Flow-Editoren den Zweck des Schritts erkennen können, ohne tiefer in die Details gehen zu müssen.


### Aufgabe \#3: Erstellen eines Schritts zum Senden einer E-Mail an den Besucher

1.  Wählen Sie **+ Neuer Schritt**aus. Mit diesem Schritt werden E-Mails an Besucher*innen gesendet.

2.  Suchen Sie nach `mail`, wählen Sie die Aktion **E-Mail senden (V2)** aus dem **Office 365 Outlook**-Connector aus.

3.  Wenn Sie aufgefordert werden, die „Nutzungsbedingungen für diese Aktion zu akzeptieren“, klicken Sie auf **Ich stimme zu**.

4.  Wählen Sie **Dynamischen Inhalt hinzufügen** unter dem Feld **An** aus. 
    
5.  Wählen Sie das Feld **E-Mail** aus der Liste dynamischer Inhalte aus.

    > Beachten Sie, dass sie sich unter der Kopfzeile **Get the Visitor** befindet. Dies bedeutet, dass Sie die E-Mail auswählen, die mit dem Besucher bzw. der Besucherin verknüpft ist, den bzw. die Sie im vorherigen Schritt gesucht haben.

7.  Geben Sie im Feld **Betreff** Folgendes ein: `Your scheduled visit to Bellows College`

8.  Geben Sie den folgenden Text in **E-Mail-Text** ein:

    > Dynamischer Inhalt muss dort platziert werden, wo Feldnamen in Klammern angegeben sind. Es wird empfohlen, zuerst den gesamten Text zu kopieren und einzufügen und dann dynamischen Inhalt an den richtigen Stellen hinzuzufügen.

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Dear {First Name},

    You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

    Best regards,

    Campus Administration
    Bellows College
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Markieren Sie den Text **{First Name}** (Vorname). Ersetzen Sie ihn durch das Feld **Vorname** aus dem Schritt **Besucher abrufen**.

9.  Markieren Sie den Text **{Scheduled Start}** (Geplanter Start). Ersetzen Sie es durch das Feld **Scheduled Start** aus dem Schritt **Wenn ein Besuch hinzugefügt wird**.

10.  Markieren Sie den Text **{Scheduled End}** (Geplantes Ende). Ersetzen Sie es durch das Feld **Scheduled End** aus dem Schritt **Wenn ein Besuch hinzugefügt wird**.

11.  Wählen Sie **Speichern**.

Lassen Sie die Registerkarte dieses Flows für die nächste Aufgabe geöffnet. Ihr Flow sollte in etwa wie folgt aussehen:

![Beispiel für Flowschritte.](media/4-Flow.png)


### Aufgabe \#4: Flow überprüfen und aktivieren

1.  Öffnen Sie im Browser eine neue Registerkarte, und navigieren Sie zu `https://make.powerapps.com`.

2.  Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

3.  Wählen Sie **Apps** aus, und öffnen Sie die modellgesteuerte App **Bellows-Campusverwaltung**, die Sie zuvor erstellt haben.

3.  Lassen Sie diese Browserregisterkarte geöffnet, und navigieren Sie wieder zurück zu der vorherigen Registerkarte mit Ihrem Flow.

4.  Wählen Sie in der Befehlsleiste **Test** aus. Wählen Sie **Manuell** aus, und wählen Sie dann **Testen** aus.

5.  Navigieren Sie zur Browserregisterkarte mit geöffneter modellgesteuerter App. 

6.  Wählen Sie links in der Sitenavigation die Option **Besuche** aus.

6.  Wählen Sie die Schaltfläche **+ Neu** aus, um einen neuen **Besuchsdatensatz** hinzuzufügen.

7.  Vervollständigen Sie den Besuchsdatensatz wie folgt:

    -   **Name**: `Test Visit`

    -   **Besucher:** John Doe

    -   **Geplanter Start:** Morgen um 8:00 Uhr

    -   **Geplantes Ende:** Morgen um 9:00 Uhr

8.  Wählen Sie die Schaltfläche **Speichern und schließen** aus.

9.  Navigieren Sie zur Browserregisterkarte, auf der Ihr Flowtest ausgeführt wird. Nach einer kurzen Verzögerung sollte der Flow ausgeführt werden. Hier können Sie alle Probleme im Flow abfangen oder bestätigen, dass er erfolgreich ausgeführt wurde.

    Nach einer kurzen Verzögerung sollten Sie eine E-Mail in Ihrem Posteingang sehen, da Sie die E-Mail-Adresse von John Doe mit Ihrer persönlichen E-Mail-Adresse aufgefüllt haben. Beachten Sie, dass sie möglicherweise in Ihrem Junk-E-Mail-Ordner landen kann.


## Herausforderung

- Experimentieren Sie mit der Formatierung der E-Mail. Wie können Sie es professioneller gestalten?


