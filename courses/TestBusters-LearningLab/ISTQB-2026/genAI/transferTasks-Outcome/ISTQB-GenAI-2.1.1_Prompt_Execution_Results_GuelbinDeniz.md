# Prompt Execution Results – TT - ISTQB - GenAI 2.1.1: Transform Weak Prompts into High-Quality Test Prompts

## Prompt 1 – Exploratory Testing

* ## Original Prompt Results (P1):
## Explorative Testnotizen – Registrierung mit Social Login

| Nr. | Beobachtung | Möglicher Befund / Risiko |
|------|-------------|--------------------------|
| 1 | Registrierung über Google gestartet, dann abgebrochen und zurück zur Registrierungsseite gewechselt. | Nutzer landet evtl. ohne klare Meldung wieder im Formular. Abbruch sollte verständlich erklärt werden. |
| 2 | Wechsel von Google zu GitHub während des Registrierungsprozesses. | Risiko: doppelte oder unklare Benutzerkonten, wenn dieselbe E-Mail-Adresse verwendet wird. |
| 3 | LinkedIn-Login geöffnet, Browser-Zurück-Button verwendet. | Mögliche Inkonsistenz: Seite bleibt hängen oder zeigt alten Ladezustand. |
| 4 | Social Login gestartet, danach normale Registrierung mit E-Mail versucht. | System sollte klar erkennen, ob die E-Mail bereits über Social Login verwendet wurde. |
| 5 | GitHub-Konto ohne öffentliche E-Mail verwendet. | Risiko: Registrierung schlägt fehl oder Konto wird ohne verständliche Fehlermeldung nicht erstellt. |
| 6 | Mehrere Social-Login-Buttons schnell hintereinander geklickt. | Mögliche technische Fehler, doppelte Requests oder verwirrende Weiterleitungen. |
| 7 | Social Login auf Login-Seite statt Registrierungsseite gestartet. | Erwartung: Wenn Konto noch nicht existiert, sollte Registrierung sauber möglich sein. |
| 8 | Registrierung mit Google abgeschlossen, danach mit LinkedIn mit gleicher E-Mail versucht. | System sollte Konto-Verknüpfung oder klare Fehlermeldung anbieten. |
| 9 | Social Login in neuem Tab geöffnet und ursprüngliche Seite weiter benutzt. | Risiko: Session-Konflikte oder unerwarteter Login-Zustand. |
| 10 | Zustimmung beim Social Provider verweigert. | Fehlermeldung sollte freundlich und verständlich sein, nicht technisch. |
---

## Überraschende Punkte / Fragen

- Was passiert, wenn dieselbe E-Mail-Adresse bei Google, GitHub und LinkedIn verwendet wird?
- Wird ein bestehendes Konto automatisch erkannt oder wird ein doppeltes Konto erstellt?
- Sind Fehlermeldungen für abgebrochene Social-Logins verständlich?
- Bleibt der Registrierungsstatus nach Unterbrechungen stabil?
- Sind die Begriffe auf Buttons und Fehlermeldungen einheitlich, z. B. „Mit Google registrieren“ vs. „Mit Google anmelden“?

---

## Mögliche Usability-Probleme

- Nutzer versteht nicht, ob er sich gerade registriert oder anmeldet.
- Nach Abbruch beim Social Provider fehlt eine klare Rückmeldung.
- Unterschiedliche Social Provider führen zu unterschiedlichem Verhalten.
- Fehlende Erklärung, welche Daten vom Social-Media-Konto übernommen werden.
- Keine klare Möglichkeit, Social Login und normales Passwort-Konto später zu verbinden.



---

* ## Improved Prompt Results (P1):


| Testidee | Testschritte | Erwartetes Ergebnis | Beobachtung | Priorität |
|-----------|-------------|---------------------|-------------|-----------|
| Registrierung über Google erfolgreich durchführen | Registrierungsseite öffnen → „Mit Google registrieren“ wählen → gültiges Google-Konto auswählen → Zugriff bestätigen | Benutzer wird erfolgreich registriert und anschließend angemeldet. | Zu prüfen / dokumentieren | Hoch |
| Registrierung über GitHub erfolgreich durchführen | Registrierungsseite öffnen → „Mit GitHub registrieren“ wählen → gültiges GitHub-Konto auswählen → Zugriff bestätigen | Benutzer wird erfolgreich registriert und anschließend angemeldet. | Zu prüfen / dokumentieren | Hoch |
| Registrierung über LinkedIn erfolgreich durchführen | Registrierungsseite öffnen → „Mit LinkedIn registrieren“ wählen → gültiges LinkedIn-Konto auswählen → Zugriff bestätigen | Benutzer wird erfolgreich registriert und anschließend angemeldet. | Zu prüfen / dokumentieren | Hoch |
| Social Login abbrechen | Registrierung über Google starten → Login beim Provider abbrechen → zurück zum Webshop | Verständliche Fehlermeldung wird angezeigt. Benutzer bleibt im Registrierungsprozess. | Zu prüfen / dokumentieren | Hoch |
| Zwischen Social-Login-Arten wechseln | Google-Registrierung starten → abbrechen → danach GitHub wählen → anschließend LinkedIn testen | Jeder neue Versuch startet sauber. Keine alten Fehlermeldungen oder Ladezustände bleiben sichtbar. | Zu prüfen / dokumentieren | Mittel |
| Normale Registrierung nach Social-Login-Abbruch testen | Social Login starten und abbrechen → danach normale Registrierung mit E-Mail versuchen | Normale Registrierung funktioniert weiterhin ohne blockierten Zustand. | Zu prüfen / dokumentieren | Hoch |
| Login-Seite als Einstiegspunkt verwenden | Login-Seite öffnen → Social Login mit noch nicht registriertem Konto starten | Benutzer wird korrekt registriert oder erhält eine klare Meldung. | Zu prüfen / dokumentieren | Hoch |
| Mehrfaches schnelles Klicken auf Social-Login-Buttons | Registrierungsseite öffnen → mehrere Social-Login-Buttons schnell hintereinander anklicken | Es wird nur ein sauberer Registrierungsprozess gestartet. Keine doppelten Weiterleitungen. | Zu prüfen / dokumentieren | Mittel |
| Browser-Zurück-Button während Provider-Login nutzen | Social Login starten → beim Provider Browser-Zurück verwenden | Benutzer kehrt kontrolliert zur Registrierung zurück. Kein leerer oder eingefrorener Zustand. | Zu prüfen / dokumentieren | Mittel |
| Social Login in neuem Tab öffnen | Social Login starten → Link/Weiterleitung in neuem Tab öffnen → ursprünglichen Tab erneut verwenden | Session-Zustand bleibt verständlich und konsistent. | Zu prüfen / dokumentieren | Mittel |
| Zugriff beim Provider verweigern | Registrierung über GitHub/LinkedIn starten → Berechtigung verweigern | Verständliche Fehlermeldung wird angezeigt. Kein Konto wird unklar angelegt. | Zu prüfen / dokumentieren | Hoch |
| Bereits registriertes Social-Konto erneut verwenden | Konto zuerst über Google registrieren → danach erneut Registrierung mit demselben Google-Konto starten | System erkennt bestehendes Konto und meldet den Benutzer an oder zeigt klare Meldung. | Zu prüfen / dokumentieren | Hoch |
| Gleiche E-Mail über verschiedene Provider verwenden | Registrierung mit Google durchführen → danach Registrierung mit GitHub/LinkedIn mit gleicher E-Mail versuchen | System verhindert doppelte Konten oder erklärt die Situation verständlich. | Zu prüfen / dokumentieren | Hoch |
| Fehlermeldung nach abgebrochener Anmeldung prüfen | Social Login starten → abbrechen → angezeigte Meldung lesen | Fehlermeldung ist verständlich, nicht technisch und hilfreich. | Zu prüfen / dokumentieren | Mittel |
| Button-Texte und Begriffe vergleichen | Registrierungs- und Login-Seite öffnen → Texte für Google, GitHub und LinkedIn vergleichen | Begriffe sind konsistent, z. B. „registrieren“ vs. „anmelden“ klar getrennt. | Zu prüfen / dokumentieren | Niedrig |
| Datenübernahme nach Social Registrierung prüfen | Registrierung über Social Login abschließen → Profil/Konto prüfen | Übernommene Daten sind sichtbar, korrekt und für den Benutzer nachvollziehbar. | Zu prüfen / dokumentieren | Mittel |


---

* ## Original Prompt Results (P2):
## Ergebnisse des Prompts zur Testfallerstellung

### Wichtige Testszenarien – Registrierung mit Social-Media-Login

#### 1. Erfolgreiche Registrierung mit Google

Ein neuer Benutzer registriert sich mit einem gültigen Google-Konto. Nach der Registrierung ist der Benutzer angemeldet.

#### 2. Erfolgreiche Registrierung mit GitHub

Ein neuer Benutzer registriert sich mit einem gültigen GitHub-Konto. Das Konto wird erstellt und der Benutzer wird eingeloggt.

#### 3. Erfolgreiche Registrierung mit LinkedIn

Ein neuer Benutzer registriert sich mit LinkedIn. Die Registrierung funktioniert ohne Fehlermeldung.

#### 4. Abbruch während des Social-Login-Prozesses

Der Benutzer startet die Registrierung über Google, GitHub oder LinkedIn und bricht den Vorgang ab. Es erscheint eine verständliche Fehlermeldung.

#### 5. Zugriff beim Social Provider verweigern

Der Benutzer erlaubt dem Webshop keinen Zugriff auf sein Social-Media-Konto. Das System reagiert kontrolliert und legt kein unvollständiges Konto an.

#### 6. Bereits registriertes Social-Konto erneut verwenden

Der Benutzer versucht, sich erneut mit demselben Social-Media-Konto zu registrieren. Das System erkennt das bestehende Konto und zeigt ein klares Verhalten.

#### 7. Gleiche E-Mail-Adresse bei verschiedenen Providern

Ein Benutzer registriert sich z. B. mit Google und versucht danach GitHub oder LinkedIn mit derselben E-Mail-Adresse. Es darf kein verwirrendes doppeltes Konto entstehen.

#### 8. Wechsel zwischen Registrierungsmethoden

Der Benutzer startet Google, bricht ab und versucht danach GitHub oder die normale E-Mail-Registrierung. Der Prozess bleibt stabil.

#### 9. Social Login von der Login-Seite aus starten

Ein neuer Benutzer startet Social Login nicht über die Registrierungsseite, sondern über die Login-Seite. Das System sollte trotzdem verständlich reagieren.

#### 10. Mehrfaches schnelles Klicken auf Social-Login-Buttons

Der Benutzer klickt schnell nacheinander auf mehrere Social-Login-Buttons. Es sollten keine doppelten Weiterleitungen oder technischen Fehler entstehen.

#### 11. Browser-Zurück-Button während der Registrierung verwenden

Der Benutzer startet Social Login und nutzt dann den Zurück-Button. Die Anwendung sollte nicht hängen bleiben oder einen falschen Status anzeigen.

#### 12. Fehlende oder nicht öffentliche E-Mail beim Provider

Besonders bei GitHub kann eine E-Mail-Adresse nicht öffentlich sein. Das System sollte diesen Fall verständlich behandeln.

#### 13. Fehlermeldungen prüfen

Bei Fehlern oder Abbrüchen sollten die Meldungen klar, verständlich und nicht zu technisch sein.

#### 14. Konsistenz der Button-Texte und Seiten

Begriffe wie „Registrieren“, „Anmelden“, „Mit Google fortfahren“ sollten konsistent und für Benutzer eindeutig sein.

#### 15. Datenübernahme ins Benutzerkonto prüfen

Nach der Social-Registrierung sollte geprüft werden, ob Name, E-Mail-Adresse oder Profilinformationen korrekt übernommen wurden.

#### 16. Logout und erneuter Login nach Social-Registrierung

Nach erfolgreicher Registrierung meldet sich der Benutzer ab und danach wieder mit demselben Social Provider an. Das sollte ohne Probleme funktionieren.

---

* ## Improved Prompt Results (P2):
## Ergebnisse des T1–T5 Testdesign-Prompts

| Testfall-ID | Test Cases mit T1–T5 Test Ansatz | Priorität |
|------------|----------------------------------|-----------|
| TC-SL-001 | T1_SocialRegistration_GoogleValidAccount_UserRegisteredAndLoggedIn | Hoch |
| TC-SL-002 | T1_SocialRegistration_GitHubValidAccount_UserRegisteredAndLoggedIn | Hoch |
| TC-SL-003 | T1_SocialRegistration_LinkedInValidAccount_UserRegisteredAndLoggedIn | Hoch |
| TC-SL-004 | T2_SocialRegistration_StartFromLoginPage_NewUserRegistrationHandledCorrectly | Hoch |
| TC-SL-005 | T2_SocialRegistration_SwitchFromGoogleToGitHub_CleanNewRegistrationFlowStarted | Mittel |
| TC-SL-006 | T2_SocialRegistration_SwitchFromSocialLoginToEmailRegistration_EmailRegistrationStillPossible | Mittel |
| TC-SL-007 | T2_SocialRegistration_ExistingSocialAccountUsedAgain_UserLoggedInOrClearMessageShown | Hoch |
| TC-SL-008 | T3_SocialRegistration_UserCancelsGoogleLogin_UnderstandableErrorMessageDisplayed | Hoch |
| TC-SL-009 | T3_SocialRegistration_UserDeniesGitHubPermission_UnderstandableErrorMessageDisplayed | Hoch |
| TC-SL-010 | T3_SocialRegistration_LinkedInServiceTemporarilyUnavailable_UnderstandableErrorMessageDisplayed | Hoch |
| TC-SL-011 | T3_SocialRegistration_GitHubEmailNotPublic_ClearMessageOrEmailRequestDisplayed | Mittel |
| TC-SL-012 | T3_SocialRegistration_BrowserBackDuringProviderLogin_UserReturnedToRegistrationSafely | Mittel |
| TC-SL-013 | T4_SocialRegistration_SameEmailUsedWithDifferentProvider_DuplicateAccountPreventedOrClearMessageShown | Hoch |
| TC-SL-014 | T4_SocialRegistration_InvalidProviderResponse_RegistrationNotCompletedAndErrorShown | Hoch |
| TC-SL-015 | T4_SocialRegistration_MissingRequiredEmail_RegistrationBlockedWithClearMessage | Hoch |
| TC-SL-016 | T4_SocialRegistration_ExpiredProviderSession_UserAskedToRestartRegistration | Mittel |
| TC-SL-017 | T5_SocialRegistration_MultipleProviderButtonsClickedQuickly_OnlyOneRegistrationFlowStarted | Mittel |
| TC-SL-018 | T5_SocialRegistration_SocialLoginOpenedInMultipleTabs_SessionStateRemainsConsistent | Mittel |
| TC-SL-019 | T5_SocialRegistration_ManipulatedReturnUrl_RegistrationNotRedirectedToUnsafePage | Hoch |
| TC-SL-020 | T5_SocialRegistration_RepeatedFailedSocialLoginAttempts_SystemRemainsStable | Mittel |

### Verteilung nach T1–T5

#### T1 – Standard Case (Happy Path)

- T1_SocialRegistration_GoogleValidAccount_UserRegisteredAndLoggedIn
- T1_SocialRegistration_GitHubValidAccount_UserRegisteredAndLoggedIn
- T1_SocialRegistration_LinkedInValidAccount_UserRegisteredAndLoggedIn

#### T2 – Alternative Case

- T2_SocialRegistration_StartFromLoginPage_NewUserRegistrationHandledCorrectly
- T2_SocialRegistration_SwitchFromGoogleToGitHub_CleanNewRegistrationFlowStarted
- T2_SocialRegistration_SwitchFromSocialLoginToEmailRegistration_EmailRegistrationStillPossible
- T2_SocialRegistration_ExistingSocialAccountUsedAgain_UserLoggedInOrClearMessageShown

#### T3 – Exception Case

- T3_SocialRegistration_UserCancelsGoogleLogin_UnderstandableErrorMessageDisplayed
- T3_SocialRegistration_UserDeniesGitHubPermission_UnderstandableErrorMessageDisplayed
- T3_SocialRegistration_LinkedInServiceTemporarilyUnavailable_UnderstandableErrorMessageDisplayed
- T3_SocialRegistration_GitHubEmailNotPublic_ClearMessageOrEmailRequestDisplayed
- T3_SocialRegistration_BrowserBackDuringProviderLogin_UserReturnedToRegistrationSafely

#### T4 – Negative Case

- T4_SocialRegistration_SameEmailUsedWithDifferentProvider_DuplicateAccountPreventedOrClearMessageShown
- T4_SocialRegistration_InvalidProviderResponse_RegistrationNotCompletedAndErrorShown
- T4_SocialRegistration_MissingRequiredEmail_RegistrationBlockedWithClearMessage
- T4_SocialRegistration_ExpiredProviderSession_UserAskedToRestartRegistration

#### T5 – Misuse Case

- T5_SocialRegistration_MultipleProviderButtonsClickedQuickly_OnlyOneRegistrationFlowStarted
- T5_SocialRegistration_SocialLoginOpenedInMultipleTabs_SessionStateRemainsConsistent
- T5_SocialRegistration_ManipulatedReturnUrl_RegistrationNotRedirectedToUnsafePage
- T5_SocialRegistration_RepeatedFailedSocialLoginAttempts_SystemRemainsStable
---


* ## Original Prompt Results (P3):
## Ergebnisse des risikobasierten Prompts

Ich würde zuerst die kritischen Kernrisiken testen, also alles, was Registrierung, Login, Kontoerstellung und Vertrauen der Benutzer direkt betrifft.

| Priorität | Risiko | Was ich zuerst testen würde | Warum |
|-----------|--------|-----------------------------|-------|
| Hoch | Benutzer kann sich nicht registrieren | Google, GitHub und LinkedIn jeweils mit gültigem Konto testen | Wenn Registrierung nicht funktioniert, ist die Funktion nicht releasefähig. |
| Hoch | Benutzer wird nach Registrierung nicht angemeldet | Erfolgreiche Registrierung durchführen und prüfen, ob der Benutzer eingeloggt ist | Das ist ein zentrales Akzeptanzkriterium. |
| Hoch | Doppelte Konten durch gleiche E-Mail-Adresse | Registrierung mit Google, danach GitHub/LinkedIn mit gleicher E-Mail testen | Doppelte Konten können Supportaufwand und Datenprobleme verursachen. |
| Hoch | Unklare Fehler bei Abbruch oder verweigertem Zugriff | Social Login starten und abbrechen bzw. Zugriff verweigern | Benutzer müssen verstehen, was passiert ist und wie sie weitermachen können. |
| Hoch | Sicherheitsrisiko durch manipulierte Weiterleitung | Rücksprung nach Social Login prüfen, besonders Redirect-Verhalten | Falsche Weiterleitungen können ein ernstes Sicherheits- und Vertrauensproblem sein. |
| Mittel | GitHub-Konto ohne öffentliche E-Mail | Registrierung mit GitHub testen, wenn keine öffentliche E-Mail verfügbar ist | Häufiger Randfall bei GitHub; kann Registrierung blockieren. |
| Mittel | Wechsel zwischen Providern führt zu instabilem Zustand | Google starten, abbrechen, danach GitHub oder LinkedIn starten | Der Workflow muss nach Unterbrechungen stabil bleiben. |
| Mittel | Mehrfachklicks oder mehrere Tabs erzeugen Fehler | Social-Login-Buttons schnell mehrfach anklicken | Kann zu doppelten Requests oder falschem Session-Zustand führen. |

---

## Reihenfolge beim Testen

### 1. Happy Path für Google, GitHub und LinkedIn

Zuerst prüfen, ob die drei wichtigsten Registrierungswege überhaupt funktionieren.

### 2. Nach erfolgreicher Registrierung Login-Status prüfen

Der Benutzer muss direkt angemeldet sein, sonst ist der Prozess aus Benutzersicht unvollständig.

### 3. Gleiche E-Mail über verschiedene Provider testen

Das ist ein hohes Geschäftsrisiko, weil doppelte Konten Kundendaten, Bestellungen und Support betreffen können.

### 4. Abbruch und verweigerte Berechtigung testen

Diese Fälle passieren realistisch oft. Die Fehlermeldung muss verständlich sein.

### 5. Redirect- und Sicherheitsverhalten prüfen

Vor dem Livegang sollte ausgeschlossen werden, dass Benutzer auf unsichere oder falsche Seiten weitergeleitet werden.

---

## Kurz gesagt

Ich würde zuerst testen, ob Benutzer sich erfolgreich registrieren können, ob keine doppelten Konten entstehen und ob Fehlerfälle verständlich und sicher behandelt werden.

---

* ## Improved Prompt Results (P3):
## Ergebnisse des verbesserten risikobasierten Prompts

| Nr. | Risiko | Warum ist das Risiko kritisch? | Priorität | Empfohlene Testaktivität |
|----|---------|--------------------------------|------------|--------------------------|
| 1 | Registrierung über Google, GitHub oder LinkedIn funktioniert nicht | Neue Kunden können kein Konto erstellen. Direkter Einfluss auf Conversion, Umsatz und Kundenzufriedenheit. | Hoch | Happy-Path-Tests für alle drei Provider mit gültigen Konten durchführen. |
| 2 | Benutzer wird nach erfolgreicher Registrierung nicht automatisch angemeldet | Verstoß gegen die User Story und die Akzeptanzkriterien. Führt zu Verwirrung und Supportanfragen. | Hoch | Erfolgreiche Registrierung prüfen und Login-Status verifizieren. |
| 3 | Doppelte Benutzerkonten bei gleicher E-Mail-Adresse über verschiedene Provider | Kann zu Dateninkonsistenzen, Bestellproblemen und erhöhtem Supportaufwand führen. | Hoch | Registrierung mit derselben E-Mail über Google, GitHub und LinkedIn testen. |
| 4 | Fehlerhafte oder unverständliche Fehlermeldungen bei Abbruch oder Fehlern | Benutzer wissen nicht, wie sie fortfahren sollen, und brechen den Prozess möglicherweise vollständig ab. | Hoch | Registrierung abbrechen, Berechtigungen verweigern und Fehlermeldungen bewerten. |
| 5 | Sicherheitsprobleme bei OAuth-Weiterleitungen (Redirects) | Mögliche Sicherheits- und Vertrauensprobleme, falls Benutzer auf falsche Seiten umgeleitet werden. | Hoch | Redirect-Verhalten nach erfolgreichem und abgebrochenem Login prüfen. |
| 6 | Konto wird trotz unvollständiger oder fehlerhafter Daten erstellt | Kann zu fehlerhaften Benutzerprofilen und Folgeproblemen in anderen Geschäftsprozessen führen. | Hoch | Fälle mit fehlender E-Mail oder unvollständigen Providerdaten testen. |
| 7 | Provider-spezifische Unterschiede führen zu inkonsistentem Verhalten | Ein Provider funktioniert, ein anderer nicht. Benutzererlebnis und Qualität wirken uneinheitlich. | Hoch | Vergleichende Tests für Google, GitHub und LinkedIn durchführen. |
| 8 | Wechsel zwischen verschiedenen Registrierungsarten verursacht Fehler | Benutzer starten häufig mehrere Versuche. Fehler können zu Abbrüchen oder inkonsistenten Zuständen führen. | Mittel | Registrierung starten, abbrechen und mit anderem Provider fortsetzen. |
| 9 | Browser-Zurück, Refresh oder Tab-Wechsel führen zu fehlerhaften Zuständen | Typisches Benutzerverhalten kann zu hängenden Sessions oder Fehlermeldungen führen. | Mittel | Explorative Tests mit Zurück-Button, Refresh und mehreren Tabs durchführen. |
| 10 | Mehrfaches Klicken auf Social-Login-Buttons erzeugt doppelte Requests | Kann technische Fehler oder doppelte Kontoerstellungen verursachen. | Mittel | Schnell hintereinander auf verschiedene Social-Login-Buttons klicken. |
| 11 | GitHub-Konto ohne öffentliche E-Mail-Adresse kann nicht verarbeitet werden | Häufiger Spezialfall bei GitHub-Nutzern. Kann zu Registrierungsabbrüchen führen. | Mittel | GitHub-Registrierung mit Konto ohne öffentliche E-Mail testen. |
| 12 | Schlechte Usability oder inkonsistente Bezeichnungen | Benutzer verstehen nicht, ob sie sich registrieren oder anmelden. Kann die Conversion reduzieren. | Niedrig | Texte, Buttons und Benutzerführung auf Konsistenz prüfen. |

---

## Empfohlene Testreihenfolge vor dem Go-Live  

1. **Happy Path für Google, GitHub und LinkedIn**
2. **Automatische Anmeldung nach erfolgreicher Registrierung**
3. **Gleiche E-Mail-Adresse über verschiedene Provider**
4. **Abbruch- und Fehlerszenarien**
5. **OAuth-Redirects und Sicherheitsaspekte**
6. **Provider-spezifische Randfälle (z. B. GitHub ohne E-Mail)**
7. **Explorative Tests zu Browser-Verhalten, Tabs und Mehrfachklicks**

---

## Fazit

Diese Reihenfolge deckt zuerst die Risiken ab, die den größten Einfluss auf Geschäftserfolg, Benutzerregistrierung und Kundenzufriedenheit haben. Sie entspricht damit einem klassischen risikobasierten Testansatz kurz vor einem Release.