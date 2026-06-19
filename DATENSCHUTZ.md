# Datenschutzerklärung – Transkri

**Stand: Juni 2026**

Diese Datenschutzerklärung gilt für die iOS-App **Transkri** („die App"). Transkri ist eine auf Privatsphäre ausgerichtete App zur Aufnahme, Transkription und Analyse von Audio. Das Grundprinzip: Standardmäßig verbleiben **alle Inhalte ausschließlich lokal auf deinem Gerät**. Es gibt **kein Backend des Anbieters** – wir betreiben keine Server, die deine Inhalte empfangen, speichern oder verarbeiten.

---

## 1. Verantwortlicher

Verantwortlich im Sinne der Datenschutz-Grundverordnung (DSGVO):

**[Dein Name / Firmenname]**
[Anschrift]
E-Mail: office.carlojansen@gmail.com

> *Bitte Name/Anschrift vor Veröffentlichung ergänzen – die Kontakt-E-Mail ist bereits eingetragen.*

---

## 2. Grundprinzip: Lokale Verarbeitung

Transkri ist als „privacy-first"-App konzipiert. Die Aufnahme, die Transkription (Tier 0) und die einfache lokale Analyse von Stichwörtern und Aufgaben finden **vollständig auf deinem Gerät** statt. Für diese Standardnutzung ist **keine Internetverbindung erforderlich**, und es werden **keine Daten an den Anbieter oder Dritte übertragen**.

Eine Datenübermittlung an Dritte findet **ausschließlich** statt, wenn du die optionale Cloud-Analyse (Tier 2) aktiv nutzt – siehe Abschnitt 4.

---

## 3. Welche Daten lokal verarbeitet werden

Die folgenden Daten werden ausschließlich lokal auf deinem Gerät erstellt, verarbeitet und gespeichert:

- **Audioaufnahmen** – von dir aufgenommene oder importierte Audiodateien.
- **Transkripte** – die aus dem Audio erzeugten Texte (lokale WhisperKit-/CoreML-Verarbeitung).
- **Lokale Analyseergebnisse** – Aufgaben (To-Dos) und Stichwörter, die über Apples `NaturalLanguage`-Framework auf dem Gerät extrahiert werden.
- **API-Schlüssel** – falls du Cloud-Analyse nutzt, werden deine selbst hinterlegten Schlüssel verschlüsselt in der **iOS-Keychain** gespeichert und verlassen das Gerät nur als Authentifizierung gegenüber dem von dir gewählten Anbieter.
- **Nutzungsstatistiken** – z. B. Token-Zähler je Anbieter; diese werden nur lokal gehalten und nicht übertragen.

Diese Daten werden **nicht** an den Anbieter gesendet. Du kannst sie jederzeit in der App löschen.

---

## 4. Optionale Cloud-Analyse (Tier 2, „Bring Your Own Key")

Transkri bietet optional eine erweiterte KI-Analyse über externe Cloud-Anbieter an. Diese Funktion ist **standardmäßig deaktiviert** und wird nur wirksam, wenn du sie selbst aktivierst und einen eigenen API-Schlüssel hinterlegst.

Wenn du die Cloud-Analyse nutzt, wird der **Transkript-Text** (kein Audio) an den von dir ausgewählten Anbieter übertragen, damit dieser eine Zusammenfassung bzw. Analyse erstellt. Mögliche Anbieter:

- **NVIDIA** – [Datenschutzhinweise von NVIDIA](https://www.nvidia.com/en-us/about-nvidia/privacy-policy/)
- **Anthropic (Claude)** – [Datenschutzhinweise von Anthropic](https://www.anthropic.com/legal/privacy)
- **Google (Gemini)** – [Datenschutzhinweise von Google](https://policies.google.com/privacy)

Wichtige Hinweise:

- Die Übertragung erfolgt **direkt von deinem Gerät** an den jeweiligen Anbieter über eine gesicherte HTTPS-Verbindung (TLS) mit zusätzlichem Public-Key-Pinning. Der Anbieter von Transkri ist **nicht** zwischengeschaltet und erhält diese Inhalte nicht.
- Für die übermittelten Inhalte gelten **die Datenschutzbestimmungen und Nutzungsbedingungen des jeweiligen Cloud-Anbieters**.
- Du entscheidest pro Nutzung, ob Inhalte das Gerät verlassen.

**Rechtsgrundlage:** Die Übermittlung erfolgt auf Grundlage deiner Einwilligung (Art. 6 Abs. 1 lit. a DSGVO), die du durch das Aktivieren der Funktion und das Auslösen der Analyse erteilst.

---

## 5. Geräteberechtigungen

Transkri fragt nur die für die jeweilige Funktion erforderlichen Berechtigungen ab:

- **Mikrofon** – zur Aufnahme von Audio-Sessions. Die Aufnahme bleibt lokal auf dem Gerät.
- **Spracherkennung** – wird nur im Fallback-Transkriptionsmodus genutzt; die Erkennung läuft erzwungen on-device.
- **Kalender (nur Schreibzugriff)** – um auf deinen Wunsch ein To-Do als Termin einzutragen. Es werden keine Kalenderdaten gelesen.
- **Erinnerungen** – um To-Dos ohne erkanntes Datum als Erinnerung anzulegen.
- **Face ID / Touch ID** – um geschützte Workspaces und den Sicherheitsbereich der App zu schützen. Biometrische Daten werden ausschließlich vom Betriebssystem verarbeitet und sind für die App nicht zugänglich.

Du kannst jede Berechtigung in den iOS-Einstellungen jederzeit widerrufen.

---

## 6. Speicherung & Sicherheit

- **Verschlüsselung im Ruhezustand:** Transkripte und Zusammenfassungen werden als AES-256-GCM-verschlüsselte Dateien gespeichert. Der Schlüssel liegt gerätegebunden in der Keychain und ist nur bei entsperrtem Gerät zugänglich.
- **Dateischutz:** Sensible Dateien nutzen `FileProtectionType.complete`.
- **Backup-Ausschluss:** Audio, Metadaten und verschlüsselte Inhalte sind von iCloud- und iTunes-Backups ausgeschlossen.
- **Keychain:** API-Schlüssel und sicherheitskritische Einstellungen liegen isoliert in der Keychain.
- **Log-Hygiene:** Im Release-Build werden keine sensiblen Inhalte oder Schlüssel in System-Logs geschrieben.

---

## 7. Keine Datenerhebung durch den Anbieter

Der Anbieter von Transkri:

- erhebt, speichert und verarbeitet **keine** personenbezogenen Daten auf eigenen Servern,
- nutzt **kein** Tracking, **keine** Analyse-/Werbe-SDKs und **keine** Werbung,
- gibt **keine** Daten an Dritte weiter (mit Ausnahme der von dir selbst ausgelösten Cloud-Analyse, siehe Abschnitt 4).

---

## 8. In-App-Käufe (freiwillige Unterstützung)

Die App bietet die Möglichkeit einer freiwilligen, einmaligen Unterstützung („Buy Me a Coffee"). Die Zahlung wird **ausschließlich von Apple** über dein App-Store-Konto abgewickelt. Der Anbieter erhält dabei **keine** Zahlungs- oder Kreditkartendaten. Es gelten die Datenschutzbestimmungen von Apple.

---

## 9. Hinweis zu Aufnahmen (§ 201 StGB)

Das nicht öffentlich gesprochene Wort darf in Deutschland nur mit Einwilligung der Beteiligten aufgezeichnet werden (§ 201 StGB; je nach Land vergleichbare Regeln). Du bist als Nutzer dafür verantwortlich, vor einer Aufnahme die erforderliche Zustimmung der beteiligten Personen einzuholen. Transkri zeigt hierzu einen entsprechenden Einwilligungs-Hinweis.

---

## 10. Deine Rechte

Da deine Inhalte lokal auf deinem Gerät liegen, hast du jederzeit die volle Kontrolle: Du kannst Aufnahmen, Transkripte und Schlüssel direkt in der App löschen. Darüber hinaus stehen dir nach DSGVO die Rechte auf Auskunft, Berichtigung, Löschung, Einschränkung der Verarbeitung, Datenübertragbarkeit sowie Widerspruch zu, soweit eine Verarbeitung durch uns stattfindet. Für Anliegen erreichst du uns unter der in Abschnitt 1 genannten Adresse. Für Inhalte, die du an einen Cloud-Anbieter übermittelst, wende dich bitte direkt an den jeweiligen Anbieter (siehe Abschnitt 4).

Du hast zudem das Recht, dich bei einer Datenschutz-Aufsichtsbehörde zu beschweren.

---

## 11. Kinder

Transkri richtet sich nicht an Kinder und erhebt nicht wissentlich Daten von Kindern.

---

## 12. Änderungen dieser Datenschutzerklärung

Wir können diese Datenschutzerklärung anpassen, etwa bei Funktionsänderungen. Die jeweils aktuelle Fassung ist unter dieser URL abrufbar; das Datum oben weist den Stand aus.

---

*Transkri ist eine BYOK-App ohne eigenes Backend. Bei Nutzung der optionalen Cloud-Analyse gelten die Bedingungen des jeweils gewählten Anbieters für die übermittelten Inhalte.*
