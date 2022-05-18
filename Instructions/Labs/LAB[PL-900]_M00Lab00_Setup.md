---
lab:
  title: 'Lab: Lab-Umgebung überprüfen'
  module: 'Module 0: Course introduction'
ms.openlocfilehash: e69074549dddd4494db53a9ccb9ebfb3ae198d48
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424701"
---
# <a name="module-0-course-introduction"></a>Modul 0: Einführung in den Kurs

## <a name="scenario"></a>Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren.

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.

In diesem Modul-0-Lab werden Sie einen Power Platform-Testmandanten erhalten und auf das Power Platform Admin Center zugreifen. Im Admin Center erstellen Sie dann Ihre **Übungsumgebung**, in der Sie den größten Teil Ihrer Lab-Arbeiten erledigen werden.

## <a name="exercise-1--setup"></a>Übung 1 – Einrichtung

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>Aufgabe 1 – Beziehen Ihres Microsoft Power Platform-Testmandanten

1.  Kopieren Sie Ihre **Microsoft 365-Anmeldeinformationen** vom autorisierten Lab-Hoster.

2.  Navigieren Sie zu <https://powerapps.microsoft.com>, und klicken Sie auf **Kostenlos starten**.

3.  Geben Sie unter **Los geht's** die E-Mail-Adresse aus Ihren Microsoft 365-Anmeldeinformationen in das Textfeld mit der entsprechenden Aufschrift ein (**Geben Sie Ihre geschäftliche E-Mail-Adresse ein**).

4.  Eine Meldung wird eingeblendet, die besagt, dass Sie über ein Konto bei Microsoft verfügen. Wählen Sie **Anmelden** aus.

5.  Geben Sie das Kennwort ein, dass Sie vom autorisierten Lab-Hoster erhalten haben, und melden Sie sich an.

6.  Wählen Sie **Ja** aus, um angemeldet zu bleiben.

7.  Geben Sie Ihre Kontoinformationen ein, und wählen Sie **Erste Schritte** aus, um sich für Ihre Microsoft Power Platform-Testversion zu registrieren.

### <a name="task-2--create-environment"></a>Aufgabe 2 – Erstellen der Umgebung

1.  Rufen Sie <https://admin.powerplatform.microsoft.com> auf, und melden Sie sich mit Ihren Microsoft 365-Anmeldeinformationen an, wenn Sie dazu aufgefordert werden.

2.  Wählen Sie **Umgebungen** aus, und klicken Sie auf **+Neu**.

    1.  Geben Sie als **Name** Folgendes ein: **[Meine Initialen] Übung**. (Beispiel: AJ Übung).

    2.  Wählen Sie als **Typ** die Option **Testversion** aus (Achtung: Wählen Sie nicht die Option „Testversion (abonnementbasiert)“ aus!).

    3.  Stellen Sie den Umschalter **Datenbank für diese Umgebung erstellen?** auf **Ja**.

    4.  Lassen Sie alle anderen Auswahlmöglichkeiten auf ihren Standardwerten, und klicken Sie auf **Weiter**.

    5.  Lassen Sie auf der nächsten Registerkarte alle Auswahlmöglichkeiten auf ihren Standardwerten, und klicken Sie auf **Speichern**.

3.  Ihre **Übungsumgebung** sollte nun in der Liste der Umgebungen angezeigt werden.

>   Ihre Umgebung kann einige Minuten zur Bereitstellung benötigen. Aktualisieren Sie die Seite bei Bedarf.
