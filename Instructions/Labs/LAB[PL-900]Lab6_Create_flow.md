---
lab:
  title: "Lab\_6: Erstellen Sie einen Power Automate-Flow."
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Automate'
  module: 'Module 2: Build a Microsoft Power Automate flow'
---

## Lernziel

In dieser Übung erstellen Lernende eine Reihe verschiedener Cloudflüsse mithilfe von Microsoft Copilot in Power Automate. Sie verwenden verschiedene Erstellungsmethoden wie Copilot von Grund auf, um sich mit den verschiedenen verfügbaren Optionen vertraut zu machen.

Nach erfolgreichem Abschluss dieser Übung werden Sie:

- Prompts in natürlicher Sprache zum Entwerfen von Workflows verwenden.
- Trigger und Aktionen konfigurieren.
- Die Automatisierung für den praktischen Einsatz testen.

### Szenario

Contoso Consulting ist eine professionelle Dienstleistungsorganisation, die sich auf IT- und KI-Beratungsdienste spezialisiert hat. Im Laufe des Jahres veranstalten sie viele verschiedene Events für ihre Kunden. Einige davon sind Events im Stil von Messen, bei denen viele Partner anwesend sind und Informationen zu neuen Produkten, Markttrends und Dienstleistungen bereitstellen. Andere finden das ganze Jahr über statt und sind kurze Webinare, in denen Details zu einzelnen Produkten vorgestellt werden. Darüber hinaus beginnt Contoso mit der Verwendung von automatisierten Agents, um Kunden bei Fragen zu unterstützen.

Contoso möchte Power Automate verwenden, um einen Bestätigungsfluss für die Registrierung zu erstellen, bei dem bei der Registrierung für ein Ereignis eine automatisierte E-Mail an einen Kunden gesendet wird. 

In dieser Übung erstellen Sie eine Reihe von Power Automate-Flüssen basierend auf bestimmten Kriterien.

Bevor Sie mit dieser Übung beginnen, müssen Sie die folgenden Labs abgeschlossen haben:

- **Lab 2: Erstellen eines Datenmodells**
- **Lab 5: Erstellen einer modellgesteuerten App**

## Übung 1: Erstellen eines Benachrichtigungsflusses für die Sitzungsregistrierung

In dieser ersten Übung erstellen Sie einen Fluss, der automatisch ausgeführt wird, wenn eine neue Sitzungsregistrierung erstellt wird. Er erhält die Details der Sitzung, des Ereignisses und des Kontakts, der sich registriert hat, und sendet eine E-Mail mit den Registrierungsdetails.

### Aufgabe 1: Erstellen eines Flows

Wir möchten eine Registrierungsbestätigung an alle neu registrierten Benutzer senden. Wir erstellen einen Fluss, der Details einer Registrierung erfasst und eine Bestätigungs-E-Mail an den registrierten Benutzer sendet.

1. Navigieren Sie zu [https://make.powerautomate.com](https://make.powerautomate.com/).

2. Möglicherweise müssen Sie sich erneut authentifizieren. Wählen Sie dazu **Anmelden** aus, und befolgen Sie die Anweisungen, falls erforderlich.

3. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist. (Wichtig, vergessen Sie nicht, diesen Schritt auszuführen).

4. Wählen Sie im linken Navigationsbereich **Erstellen** aus. (Wenn Sie dazu aufgefordert werden, wählen Sie **Erste Schritte** aus.)

5. Wählen Sie **+ Neuer Flow** und dann **Automatisierter Cloud-Flow** aus.

6. Geben Sie die **Registrierungsbenachrichtigung** für den **Flussnamen** ein.

7. Suchen Sie unter **Flowtrigger auswählen** nach **Dataverse**.

8. Wählen Sie den Trigger, **wenn eine Zeile hinzugefügt, geändert oder gelöscht wird**, und dann **Erstellen** aus.

    Wenn ein Fehler **Ungültige Parameter** angezeigt wird, liegt dies daran, dass Sie sich nicht authentifiziert haben. Führe die unten aufgeführten Schritte aus, um eine Verbindung herzustellen. 
    - Klicken Sie auf **Verbindung ändern**.
    - Wählen Sie **Neue hinzufügen* aus.
    - Geben Sie im Feld **Verbindungsname** den MOD-**Administrator** ein. Behalten Sie den **Authentifizierungstyp** als **OAuth** bei, und wählen Sie **Anmelden** aus.
    - Nach der Anmeldung wechseln Sie zu **Schritt 9.** 

9. Füllen Sie die Triggerbedingungen für den Flow auf:

    - Wählen Sie **Hinzugefügt** für **Änderungstyp** aus.
    - Wählen Sie **Sitzungsregistrierungen** für den **Tabellennamen** aus.
    - Wählen Sie **Organisation** für **Bereich** im Triggerschritt aus, wählen Sie die Auslassungspunkte (**...**) und dann **Umbenennen** aus. 

10. Benennen Sie den Triggerschritt ** um, wenn eine Sitzungsregistrierung hinzugefügt wird.**

![Screenshot der Konfiguration zum Hinzufügen einer Sitzungstriggerkonfiguration](media/power-automate-01.png)

Dies ist eine gute Vorgehensweise, damit Sie und andere Flow-Editoren den Zweck des Schritts erkennen können, ohne tiefer in die Details gehen zu müssen.


### Aufgabe 2: Erstellen Sie einen Schritt, um die Details der Ereignissitzung abzurufen, für die die Registrierung vorgesehen ist.

1. Wählen Sie **+ Neuer Schritt**aus. 

2. Suchen Sie nach **Zeile nach ID abrufen**. 

3. Wählen Sie die Aktion **Zeile nach ID abrufen** aus.

4. Wählen Sie **Ereignissitzungen** als **Tabellenname** aus.

5. Wählen Sie das Feld **Zeilen-ID** aus. Beachten Sie, dass Symbole angezeigt werden, um **Dynamische Inhalte** oder **Ausdrücke** auszuwählen.

6. Fügen Sie im Feld **Zeilen-ID** den Eintrag **Ereignissitzung (Wert)** in der **Liste für dynamische Inhalte** aus. In diesem Schritt suchen Sie die **Ereignissitzung** für die **Sitzungsregistrierung**, die erstellt wurde, um diesen Fluss auszulösen.

7. Wählen Sie in der Aktion **Zeile nach ID abrufen** die Auslassungspunkte ( **...** ) aus, und wählen Sie dann **Umbenennen** aus. Benennen Sie diese Aktion in **Abrufen der Ereignissitzung** um.

![Screenshot der Ereignissitzungsaktionskonfiguration](media/power-automate-02.png)

Als Nächstes erhalten wir die Details des Ereignisses, in dem sich die Sitzung befindet.

8. Wählen Sie unter dem Schritt **Ereignissitzung abrufen** die Option **+ Aktion einfügen** aus.

9. Suchen Sie nach **Zeile nach ID abrufen**. 

10. Wählen Sie die Aktion **Zeile nach ID abrufen** aus.

11. Wählen Sie **Ereignisse** als **Tabellennamen** aus.

12. Wählen Sie das Feld **Zeilen-ID** aus. Beachten Sie, dass Symbole angezeigt werden, um **Dynamische Inhalte** oder **Ausdrücke** auszuwählen.

13. Fügen Sie im Feld **Zeilen-ID** den Eintrag **Ereignis (Wert)** in der Liste für **dynamische Inhalte** aus. In diesem Schritt suchen Sie das **Ereignis** für die **Ereignissitzung**, das im vorherigen Schritt erfasst wurde.

14. Wählen Sie in der Aktion **Zeile nach ID abrufen** die Auslassungspunkte ( **...** ) aus, und wählen Sie dann **Umbenennen** aus. Benennen Sie diese Aktion in **Ereignis abrufen** um

![Screenshot der Konfiguration für die Aktion „Ereignis abrufen“](media/power-automate-03a.png)

Schließlich werden wir die Details der Person abrufen, die für die Sitzung registriert ist.

15. Wählen Sie unter „Ereignisdetails abrufen“ die Option **Neue Aktion einfügen** aus.

16. Geben Sie im Suchfeld **Zeile nach ID abrufen** ein.

17. Wählen Sie die Aktion **Zeile nach ID abrufen** aus.

18. Wählen Sie **Kontakte** als **Tabellenname** aus.

19. Wählen Sie das Feld **Zeilen-ID** aus. Beachten Sie, dass ein Fenster geöffnet wird, in dem Sie **dynamische Inhalte** oder **Ausdrücke** auswählen können.

20. Wählen Sie im Feld **Zeilen-ID** das Feld **Teilnehmer (Wert)** aus dem Trigger **Wenn eine Sitzungsregistrierung hinzugefügt wird** der Liste **Dynamischer Inhalt** aus.

21. Wählen Sie den Text **Zeile nach ID abrufen** aus, und benennen Sie diese Aktion in **Teilnehmerdetails** **abrufen** um.

![Screenshot der Aktionskonfiguration „Teilnehmerdetails abrufen“](media/power-automate-04a.png)

### Aufgabe 3: Erstellen eines Schritts zum Senden einer E-Mail zum Bestätigen der Sitzungsregistrierung

1. Wählen Sie unter dem Schritt **Teilnehmerdetails abrufen** die Option **Neue Aktion einfügen** aus.

2. Geben Sie im Suchfeld **E-Mail senden** ein.

3. Wählen Sie **E-Mail senden (V2)** aus.

Möglicherweise werden Sie aufgefordert, eine Verbindung mit Outlook herzustellen. Wenn ja, wählen Sie die Schaltfläche **Anmelden** aus, und melden Sie sich mit dem **Mod-Administrator**-Konto an. 

![Screenshot: Fenster zum Erstellen einer Verbindung](media/power-automate-05.png)

4. Wählen Sie direkt oberhalb des Felds **An** das **Zahnradsymbol** aus. Wählen Sie im daraufhin angezeigten Menü **Dynamischen Inhalt verwenden** aus.

![Screenshot der Verwendung dynamischer Inhalte](media/power-automate-06.png) 

5. Wählen Sie im Feld **An** unter **Teilnehmerdetails abrufen** die Option **E-Mail** aus.

![Screenshot: Festlegen des Felds auf die E-Mail-Adresse des Teilnehmers](media/power-automate-07.png)

6. Stellen Sie im Feld **Betreff** sicher, dass er „Registrierungsbestätigung“ lautet

7. Geben Sie den folgenden Text in **E-Mail-Text** ein:

> **Hinweis:** Dynamischer Inhalt muss dort platziert werden, wo Feldnamen in Klammern angegeben sind. Es wird empfohlen, zuerst den gesamten Text zu kopieren und einzufügen und dann dynamischen Inhalt an den richtigen Stellen hinzuzufügen.

  *Hallo {Vorname}, vielen Dank für die Registrierung für unsere bevorstehende Sitzung {Sitzungsname} am {Ereignisdatum}. {Referent} ist Ihr Referent oder Ihre Referentin in dieser Sitzung. Ihre Sitzung ist für die letzte {Dauer (Stunden)} geplant. Sehen Sie sich unsere andere Sitzung bei unserem {Eventname} an.*

  *Mit freundlichen Grüßen*

  *Eventverwaltung*
  
  *Contoso Consulting*

Als Nächstes ersetzen wir den Text in den Klammern durch die unten beschriebenen Elemente.

8. Markieren Sie den Text **{First Name}** (Vorname). Ersetzen Sie ihn durch das Feld **Vorname** aus dem Schritt **Teilnehmerdetails abrufen**.

9. Markieren Sie den Text **{Sitzungsname}**. Ersetzen Sie ihn durch das Feld **Sitzungsname** aus dem Schritt **Ereignissitzung abrufen**.

10. Markieren Sie den Text **{Ereignisdatum}**. Ersetzen Sie ihn durch das Feld **Ereignisdatum** aus dem Schritt **Eventdetails abrufen**.

11. Markieren Sie den **{Referent}**-Text. Ersetzen Sie ihn durch das Feld **Referent (Wert)** aus dem Schritt **Ereignissitzung abrufen**.

12. Markieren Sie den Text **{Dauer (Stunden)}**. Ersetzen Sie ihn durch das Feld **Dauer (Stunden)** aus dem Schritt **Ereignissitzung abrufen**.

13. Markieren Sie den Text **{Ereignisname}**. Ersetzen Sie ihn durch das Feld **Ereignisname** aus dem Schritt **Ereignisdetails abrufen**.

Ihr letzter Schritt sollte der Abbildung ähneln:

![Screenshot der fertigen E-Mail](media/power-automate-08.png)

14. Wählen Sie **Speichern**.

Lassen Sie die Registerkarte dieses Flows für die nächste Aufgabe geöffnet. Die Datei sollte folgendermaßen aussehen:

### Aufgabe 4: Fügen Sie einige Beispieldaten hinzu.

> **Hinweis:** Wenn Sie Lab 5 abgeschlossen haben – „Erstellen einer modellgesteuerten App“, können Sie diese Aufgabe überspringen und direkt zu Aufgabe 5 wechseln. 

1. Wählen Sie links im Navigationsbereich die Option **Apps** aus.

2. Ändern Sie die angezeigten Apps von **Meine Apps** in **Alle**.

3. Zeigen Sie auf die Anwendung **Ereignisverwaltung**, und wählen Sie das Symbol **Wiedergeben** aus.

4. Wählen Sie links im Navigationsbereich die Option **Kontakte** aus.

5. Wählen Sie auf der Befehlsleiste die Schaltfläche **+ Neu** aus.

6. Konfigurieren Sie auf der Oberfläche **Neuer Kontakt** den Kontakt wie folgt:

    - **Vorname:** Suzanne

    - **Nachname:** Diaz

    - **Position:** Techniker

7. Wählen Sie in der Formularkopfzeile den Abwärtspfeil neben **Kontakttyp** aus.

8. Legen Sie den **Kontakttyp** auf **Referent** fest.

![Screenshot, der zeigt, wie das Feld „Kontakttyp“ in einem Formular festgelegt wird](media/power-automate-09.png)

9. Wählen Sie die Schaltfläche **Speichern** aus, um den Kontakt zu speichern, und lassen Sie ihn geöffnet.

10. Wählen Sie die Schaltfläche **+ Neu** aus.

11. Konfigurieren Sie auf der Oberfläche **Neuer Kontakt** den Kontakt wie folgt:

    - **Vorname:** Edgar

    - **Nachname:** Swenson

    - **Position:** architekt

    - **E-Mail:** Geben Sie Ihre E-Mail-Adresse ein (WICHTIG, oder Ihr Fluss wird nicht ausgeführt).

12. Wählen Sie in der Formularkopfzeile den Abwärtspfeil neben **Kontakttyp** aus.

13. Legen Sie den **Kontakttyp** auf **Teilnehmer** fest.

14. Wählen Sie die Schaltfläche **Speichern und schließen** aus.

Als Nächstes fügen wir ein neues Ereignis hinzu.

15. Wählen Sie links im Navigationsbereich die Option **Ereignisse** aus.

16. Wählen Sie auf der Befehlsleiste die Schaltfläche **+ Neu** aus.

17. Führen Sie über **Neues Ereignis** folgende Konfigurationen aus:

    - **Ereignisname:** Frühlingskonferenz

    - **Ereignisdatum** Datum von morgen

    - **Maximale Teilnehmeranzahl:** 500

    - **Ereignisdetails:** Frühlingskonferenz zur Vorstellung von Produktneuheiten und Services von unseren unterstützten Lieferanten

    - **Ereignistyp:** Konferenz

    - **Standort:** Seattle

    - **Registrierung erforderlich:** Ja/Wahr

![Screenshot des ausgefüllten Ereignisformulars ](media/power-automate-10.png)

18. Wählen Sie die Schaltfläche **Speichern und schließen** aus.

Als Nächstes fügen wir eine neue Sitzung für das Ereignis hinzu.

19. Wählen Sie links im Navigationsbereich die Option **Ereignissitzungen** aus.

20. Wählen Sie die Schaltfläche **+ Neu** aus.

21. Konfigurieren Sie die **Ereignissitzung** wie folgt:

    - **Sitzungsname:** Verantwortungsbewusste künstliche Intelligenz

    - **Sitzungsdatum:** Datum von morgen

    - **Dauer:** 1,5 Stunden

    - **Sitzungsbeschreibung:** Mit allen neuen KI-Lösungen ist es wichtig, verantwortungsbewusst zu handeln. Wir werden die Herausforderungen diskutieren.

    - **Referentin:** Suzanne Diaz

    - **Ereignis:** Frühlingskonferenz

![Screenshot des ausgefüllten Ereignissitzungsformulars ](media/power-automate-11.png)

22. Wählen Sie **Speichern und schließen** aus.

 
### Aufgabe 5: Flow überprüfen und aktivieren

1. Öffnen Sie bei Bedarf im Browser eine neue Registerkarte, und navigieren Sie zu [https://make.powerapps.com](https://make.powerapps.com/). 

2. Wählen Sie oben rechts die Umgebung **Dev One** aus, sofern sie noch nicht ausgewählt ist.

3. Wählen Sie **Apps** aus, und öffnen Sie die **Contoso-Ereignisverwaltungs-App**.

4. Lassen Sie diese Browserregisterkarte geöffnet, und navigieren Sie wieder zurück zu der vorherigen Registerkarte mit Ihrem Flow.

5. Wählen Sie in der Befehlsleiste **Test** aus. Wählen Sie **Manuell** aus, und wählen Sie dann **Testen** aus.

6. Navigieren Sie zur Browserregisterkarte mit geöffneter modellgesteuerter App.

Schließlich erstellen wir eine **Sitzungsregistrierung**.

7. Wählen Sie mit der Navigation auf der linken Seite **Sitzungsregistrierungen** aus.

8. Wählen Sie auf der **Befehlsleiste** **+ Neu** aus.

9. Führen Sie die Sitzungsregistrierung wie folgt aus:

    - **Name:** E, Swenson Registration.

    - **Registrierungsdatum:** Heutiges Datum

    - **Teilnehmer:** Edgar Swenson

    - **Sitzung:** Verantwortungsbewusste künstliche Intelligenz

![Screenshot des ausgefüllten Sitzungsregistrierungsformulars ](media/power-automate-12.png)

10. Wählen Sie **Speichern und schließen** aus.

11. Wählen Sie die Schaltfläche **Speichern und schließen** aus.

12. Navigieren Sie zur Browserregisterkarte, auf der Ihr Flowtest ausgeführt wird. Nach einer kurzen Verzögerung sollte der Flow ausgeführt werden. Hier können Sie alle Probleme im Flow abfangen oder bestätigen, dass er erfolgreich ausgeführt wurde.

Nach kurzer Verzögerung sollte eine E-Mail in Ihrem Posteingang angezeigt werden.

> **Hinweis:** Beachten Sie, dass sie möglicherweise in Ihrem Junk-E-Mail-Ordner landen kann.
