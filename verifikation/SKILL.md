---
name: verifikation
description: "Prüft fertige Arbeit wie eine echte Nutzerin, bevor Claude „fertig“ sagt: Seite oder App im Browser öffnen, die geänderten Stellen durchklicken, Screenshots am Computer und in Handy-Breite machen und erst mit diesen Beweisen melden, dass es läuft. Nutze diesen Skill nach JEDER Umsetzung an einer Webseite, App, Salespage, einem Opt-in, Mitgliederbereich oder Formular, und immer bei „prüf das“, „läuft das wirklich?“, „zeig mir, dass es geht“, „verifizieren“, „Beweis“, „ohne dass ich Code lese“."
---

# Verifikation

## Wann
Nach jeder Änderung, die man im Browser sehen oder anklicken kann. Bevor du „fertig“, „erledigt“ oder „läuft“ schreibst, kommt dieser Ablauf. Ein grüner Build oder ein Test im Terminal reicht als Beweis nie. Gezählt wird, was eine Besucherin wirklich sieht.

## Was am Ende herauskommt
Ein kurzer Prüfbericht mit Screenshots: was geprüft wurde, wie es aussieht (Computer und Handy), was geklappt hat und was auffällt. Die Person muss dafür keinen Code lesen.

## Ablauf

1. **Prüfliste schreiben, bevor du klickst.** Aus dem Auftrag ableiten, was sich geändert hat und woran man sieht, dass es funktioniert. Pro Punkt ein Satz: „Auf /kurs steht der neue Titel“, „Formular nimmt eine E-Mail an und zeigt die Danke-Seite“. Höchstens 8 Punkte, die wichtigsten zuerst.
2. **Richtige Adresse wählen.** Ist die Änderung live, die echte Adresse prüfen. Ist sie nur lokal, den lokalen Server starten und die lokale Adresse nehmen. Immer die Stelle prüfen, die die Besucherin sieht, nie nur die Datei.
3. **Browser öffnen.** Einen der Browser nehmen, die Claude steuern kann: den eingebauten Browser, Claude in Chrome oder Playwright mit eigenem Chromium und eigenem Profil. Nie den Browser der Person schliessen oder beenden. Eigene Tabs am Schluss wieder schliessen.
4. **Am Computer prüfen** (Fensterbreite rund 1440 px). Seite laden, jeden Punkt der Prüfliste durchgehen: lesen, klicken, scrollen, bei Formularen nur Testdaten eintragen. Pro Punkt einen Screenshot.
5. **In Handy-Breite prüfen** (rund 390 px breit). Dieselben Punkte noch einmal, vor allem: läuft nichts seitlich aus dem Bild, sind Knöpfe gross genug, ist Text lesbar, überdeckt nichts den Inhalt. Lässt sich das Browserfenster nicht schmaler ziehen (bei maximiertem Chrome häufig), die Handy-Ansicht im eingebauten Browser (Ansicht „Mobile“) oder in Playwright mit fester Fenstergrösse prüfen. Danach mit `window.innerWidth` kontrollieren, dass wirklich die schmale Breite aktiv ist, und mit `document.documentElement.scrollWidth`, dass nichts seitlich hinausragt.
6. **Technik kurz mitprüfen.** Konsole auf rote Fehler ansehen, kaputte Bilder und Links notieren, Ladezeit grob einschätzen (lädt die Seite in wenigen Sekunden?).
7. **Bericht schreiben.** Pro Punkt der Prüfliste: ✅ klappt, mit Screenshot, oder ❌ klappt nicht, mit Screenshot und einem Satz, was zu sehen ist. Dazu „Nebenbei aufgefallen“ für Dinge ausserhalb des Auftrags.
8. **Erst dann „fertig“.** Steht irgendwo ❌, ist die Aufgabe offen. Dann reparieren und den Ablauf ab Schritt 4 für die betroffenen Punkte wiederholen.

## Regeln
- Keine echten Zahlungen, keine echten Bestellungen, keine echten Nachrichten an fremde Leute auslösen. Formulare nur mit Testdaten und nur dort, wo das Absenden nichts kostet oder niemanden stört. Im Zweifel bis kurz vor „Absenden“ prüfen und das melden.
- Keine Passwörter oder Schlüssel eintippen. Braucht eine Seite ein Login, das nicht schon besteht, die Person fragen.
- Screenshots ablegen, wo das Projekt sie erwartet, sonst im Scratchpad. Den Pfad im Bericht nennen.
- Ehrlich bleiben: was nicht geprüft werden konnte, steht als „nicht geprüft“ im Bericht, mit Grund.
