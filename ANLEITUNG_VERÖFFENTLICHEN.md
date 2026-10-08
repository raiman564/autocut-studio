# AutoCut Studio – Webseite kostenlos veröffentlichen

Du bekommst eine vollständig statische Webseite mit Startseite, Funktionen, TikTok-Integration, FAQ/Kontakt, Datenschutzerklärung, Nutzungsbedingungen und Impressum. Sie hat keine Serverkomponente und benötigt keine eigene Domain.

## A. WICHTIG: Vor dem Hochladen vervollständigen

Die Rechtstexte sind ENTWÜRFE und enthalten sichtbare Platzhalter in eckigen Klammern. Gib die Webseite mit diesen Platzhaltern nicht zur TikTok-Prüfung frei.

Öffne die Dateien `datenschutz.html`, `nutzungsbedingungen.html`, `impressum.html` und `hilfe.html` in einem Texteditor (z. B. Windows Editor oder VS Code) und trage die tatsächlichen Angaben ein:

1. Vollständiger Name/Firma des Betreibers und ladungsfähige Postanschrift im Impressum, in den Nutzungsbedingungen und in der Datenschutzerklärung.
2. Echte, erreichbare Support-E-Mail. In `hilfe.html` auch `href="mailto:KONTAKT_EMAIL_EINTRAGEN"` durch `href="mailto:deine@email.de"` ersetzen.
3. Tatsächliche Speicherung von TikTok-Token, Profil- und Videodaten in der Anwendung; Speicherdauer, mögliche Server/Empfänger, Lösch-/Widerrufsvorgang.
4. Falls die Software an Dritte verteilt wird: konkreten Download-/Zugangsweg, Lizenz, Preis, Support-/Update-Modell und gegebenenfalls weitere rechtliche Pflichtinformationen.
5. Jede kursiv/orange markierte offene Angabe ersetzen. Anschließend die gelben Hinweisboxen am Anfang der drei Rechtstextseiten entfernen, sobald alles rechtlich geprüft ist.
6. Die Texte an der tatsächlichen Software überprüfen lassen. Entwürfe sind keine Rechtsberatung.

Tipp: Schick ChatGPT KEINE TikTok Client Secrets oder Passwörter. Der Schlüssel gehört nur in die lokale AutoCut-Anwendung.

## B. Lokal ansehen

1. Die ZIP-Datei entpacken.
2. Im Ordner `autocut-studio-webseite` auf `index.html` doppelklicken.
3. Links durchgehen: Funktionen, TikTok-Integration, Hilfe, Datenschutzerklärung, Nutzungsbedingungen, Impressum.

## C. Mit GitHub Pages kostenlos veröffentlichen

1. Auf https://github.com/ ein kostenloses Konto erstellen oder anmelden.
2. Auf https://github.com/new gehen.
3. Repository-Name: `autocut-studio` (oder ein anderer verfügbarer Name).
4. **Public** auswählen und **Create repository** anklicken.
5. Im Repository `Add file` → `Upload files` wählen.
6. **Den Inhalt** des entpackten Webseitenordners hochladen – also `index.html`, alle weiteren `.html`-Dateien und den gesamten Ordner `assets` (nicht den übergeordneten Webseitenordner selbst). Achtung: Geheimnisse, Token, private Projektdaten und TikTok Client Secrets niemals hochladen.
7. Unten `Commit changes` bestätigen.
8. Oben `Settings` → links `Pages` öffnen.
9. Unter `Build and deployment` → `Source`: **Deploy from a branch**.
10. Branch: **main** und Ordner: **/(root)** wählen, dann **Save**.
11. Einige Minuten warten (laut GitHub kann es bis zu etwa 10 Minuten dauern), dann `Visit site` anklicken.

Deine öffentliche Adresse lautet typischerweise:

- Webseite: `https://DEIN-GITHUB-NAME.github.io/autocut-studio/`
- Datenschutzerklärung: `https://DEIN-GITHUB-NAME.github.io/autocut-studio/datenschutz.html`
- Nutzungsbedingungen: `https://DEIN-GITHUB-NAME.github.io/autocut-studio/nutzungsbedingungen.html`

Ersetze `DEIN-GITHUB-NAME` durch deinen tatsächlichen GitHub-Benutzernamen. Den exakten Link zeigt GitHub unter Settings → Pages. Wenn du das Repository anders nennst, verändert sich der Link entsprechend.

## D. Diese URLs bei TikTok eintragen

Im TikTok Developer Portal unter deiner App `Auto Cut Studio` im **Produktionsmodus**:

- Offizielle Website/Desktop URL: die GitHub-Pages-Hauptadresse (mit abschließendem `/`)
- Privacy Policy URL: gleiche Adresse plus `datenschutz.html`
- Terms of Service URL: gleiche Adresse plus `nutzungsbedingungen.html`

Prüfe, dass alle drei Links OHNE GitHub-Anmeldung im Inkognito-Browser geöffnet werden können und die Datenschutz-/Nutzungslinks sichtbar in der Fußzeile deiner Startseite stehen.

## E. Domain-/URL-Verifizierung bei TikTok (wichtig!)

TikTok verlangt vor der Produktionsfreigabe die Verifizierung der URLs. Bei GitHub Pages bietet sich **URL prefix** an, nicht die Domain-Überprüfung für das gemeinsam betriebene `github.io`.

1. Im TikTok Developer Portal deine App im **Production**-Modus öffnen.
2. Oben `URL properties` → `Verify properties` öffnen.
3. `URL prefix` auswählen und die vollständige eigene GitHub-Pages-Adresse angeben, wie TikTok sie anzeigt.
4. Die von TikTok bereitgestellte **Signaturdatei** herunterladen.
5. Genau diese Datei über GitHub `Add file` → `Upload files` **in den Website-Stammordner** hochladen, neben `index.html` (oder an den von TikTok ausdrücklich genannten Pfad). Dateiname und Inhalt unverändert lassen.
6. Commit abwarten und im Browser testen, dass die Signaturdatei unter dem verlangten URL-Pfad öffentlich erreichbar ist.
7. Zurück bei TikTok auf `Verify` klicken. Falls TikTok die Datenschutz- und Terms-URL separat verlangt, die jeweiligen URL-Eigenschaften nach den angezeigten Anweisungen einzeln prüfen.

ACHTUNG: Keine selbst erfundene Signaturdatei erstellen. Nur die Datei aus DEINER TikTok-Entwickler-App verwenden.

## F. App-Freigabe bei TikTok

1. Unter Products **Login Kit** und den für die Display API nötigen Zugriff hinzufügen.
2. Benötigte Scopes: `user.info.basic` und `video.list`.
3. Für Windows im Desktop-/Login-Kit-Bereich die zu AutoCut passende **Redirect URI** eintragen. Die genaue localhost-URI muss mit der technischen Implementierung und der von TikTok akzeptierten Konfiguration übereinstimmen. Sie gehört nicht in die Website-/Datenschutzfelder.
4. Die Verbindung zuerst im TikTok-**Sandbox**-Modus testen. TikTok verlangt für die erste Review-Einreichung einen funktionierenden Demo-Ablauf aus der Sandbox.
5. Ein echtes Demonstrationsvideo der funktionierenden Desktop-App erstellen: Kanal auswählen → Login Kit autorisieren → `video.list` bzw. Kontodaten abrufen → bereits veröffentlichtes Video zuordnen. Die öffentlich sichtbare Website allein ist kein Ersatz dafür.
6. Unter App Review den genauen Zweck jedes Scopes erläutern und das Demovideo einreichen.
7. Erst nach Prüfung und Freigabe steht die Produktionsintegration für andere Nutzer regulär zur Verfügung. TikTok kann zusätzliche Angaben anfordern oder Änderungen verlangen.

Hinweise: Die TikTok-Display-API ermöglicht **nicht** das automatische Veröffentlichen. Dafür wäre eine separate Posting API mit einer zusätzlichen Freigabe nötig.

## G. Wenn du Hilfe brauchst

1. Schicke ChatGPT einen Screenshot von deinem GitHub-Repository nach dem Hochladen.
2. Anschließend schick einen Screenshot von `Settings → Pages`, dann kann man die drei tatsächlich gültigen URLs ablesen.
3. Für TikTok die URL-Verifizierungsmaske zeigen (ohne geheime Schlüssel).

Offizielle Quellen:
- TikTok App registration: https://developers.tiktok.com/docs/en/getting-started-create-an-app
- TikTok App review: https://developers.tiktok.com/docs/en/app-review-guidelines
- GitHub Pages setup: https://docs.github.com/de/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- GitHub file upload: https://docs.github.com/de/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
