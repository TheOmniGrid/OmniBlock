# OmniBlock — Store-Eintrag (Deutsch)

Übersetzte Store-Texte für die deutschsprachigen Länderfassungen von Chrome
Web Store und AMO. Beide Stores akzeptieren pro Sprache eigene Einträge --
siehe `submission-runbook.md` für den Ablauf, wo diese Texte einzutragen
sind. Struktur, Zeichen-Limits, Kategorie, Screenshots, Promo-Kacheln und
die Datenschutz-Angaben sind an `listing.md` (Englisch, Quelle der
Wahrheit für den Ablauf) gebunden -- diese Datei enthält nur die
kundenseitigen Texte, die tatsächlich pro Sprache eingegeben werden.

## Name

```
OmniBlock
```

## Kurzbeschreibung (Chrome Web Store, ≤132 Zeichen)

127 Zeichen:

```
Werbe-, Tracker- und Bedrohungsblocker: 6 Schutzstufen, Security Shield, eigene Listen, Kontrolle pro Website. Ohne Telemetrie.
```

## Zusammenfassung (AMO, ≤250 Zeichen)

192 Zeichen:

```
Blockiert Werbung, Tracker und bekannte Schadseiten auf 6 Schutzstufen plus unabhängiges Security Shield. Eigene Listen, Vertrauen pro Website, Element-Picker. Null Telemetrie, komplett lokal.
```

## Ausführliche Beschreibung (beide Stores)

```
OmniBlock ist ein browserübergreifender Content-Blocker: Werbung, Tracker,
Cookie-Banner und bekannte Schadseiten, mit einem Schutzregler von 0 bis 5,
einem unabhängigen, dauerhaft aktiven Security Shield, Kontrolle pro
Website, eigenen Filterlisten-Abonnements und einem Element-Picker per
Klick.

EHRLICH ÜBER PLATTFORM-UNTERSCHIEDE

Auf Chrome, Edge, Brave und anderen Chromium-Browsern läuft OmniBlock auf
der nativen declarativeNetRequest-API von Manifest V3. Keine
Manifest-V3-Erweiterung -- OmniBlock eingeschlossen -- kann das leisten,
was uBlock Origin zu MV2-Zeiten konnte, weil Chrome die dynamische
Filter-API entfernt hat, die das möglich machte. OmniBlocks eigentliche
Konkurrenz auf Chromium sind uBO Lite und ABP-MV3, und wir wollen beide bei
Filterlisten-Tiefe, Bedienung der Schutzstufen und Kontrolle pro Website
übertreffen -- bei nativer DNR-Geschwindigkeit: null JavaScript im
Anfragepfad, was grundsätzlich schneller ist als jede JS-basierte
Filterprüfung eines MV2-Blockers je war.

Auf Firefox nutzt OmniBlock vollständig blockierendes webRequest mit einer
eigenen Filter-Engine und spielt damit tatsächlich in der Liga von uBlock
Origin: vollständige Unterstützung der Filterlisten-Syntax, unbegrenzte
Regeln, und ein Abgleicher, der laut Ghosterys eigenen veröffentlichten
Benchmarks schneller ist als der von uBO.

Das sagen wir lieber gleich, als dass Sie es später selbst merken.

FUNKTIONEN

- 6 Schutzstufen (Aus bis Festung), jede kumulativ und vorkompiliert --
  ein Stufenwechsel wirkt sofort, kein Neustart nötig
- Unabhängiges Security Shield: Bedrohungs-Feeds (Malware, Phishing,
  Betrug, gefälschte Shops), die auch bei Schutzstufe Aus aktiv bleiben,
  denn Sicherheit ist keine Frage des Werbeblockens
- Eigene Filterlisten-Abonnements -- jede Liste in Adblock- oder
  Hosts-Syntax lässt sich per URL abonnieren
- Eigene Filter -- eigene Filterregeln von Hand schreiben, Zeile für
  Zeile validiert
- Element-Picker -- per Klick alles ausblenden, was eine Filterliste
  übersehen hat
- Kontrolle pro Website -- einer Website mit einem Klick ganz vertrauen
  und sie so von der Blockierung ausnehmen
- Lokales Statistik-Dashboard -- Verlauf blockierter Anfragen und
  meistblockierte Domains (Firefox; siehe den Hinweis auf der
  Statistik-Seite, warum Chromium diese Daten keiner Erweiterung zur
  Verfügung stellen kann)
- Einstellungen als eine einzige Datei importieren/exportieren
- Ausschließlich dunkle Rift-Oberfläche (OmniVex-Designsystem, OmniBlocks
  charakteristisches Blau) für ein schnelles, reibungsloses Popup

DATENSCHUTZ

Keine Datenerhebung. Keine Telemetrie, keine Analyse, keine Konten, kein
Server. Filterlisten werden als Text in Adblock-Syntax von ihren
öffentlichen Betreibern abgerufen (EasyList, die Filterlisten von uBlock
Origin, HaGeZis DNS-Blocklisten). Die Scriptlet-Bibliothek, auf die diese
Regeln verweisen können, ist fest in die Erweiterung selbst eingebettet
und auf eine bestimmte, geprüfte Version festgelegt -- und bei jeder
Liste, die Sie selbst abonnieren, werden Scriptlet-Zeilen entfernt, bevor
OmniBlocks Blockier-Engines sie überhaupt zu sehen bekommen. Vollständige
Richtlinie: siehe den Datenschutz-Tab dieses Eintrags.
```
