# Linux-Kommandos aneinanderreihen - Aufgabe (10 Minuten)

## Aufgabenstellung

**Ausgabenumlenkung** (nur eine Prompt erlaubt!)

1. **Erstelle eine Datei `systeminfo.txt`** und speichere die Ausgabe des Befehls `uname -a` (Systeminformationen) darin.

2. **Füge die Ausgabe des Befehls `date`** (aktuelles Datum und Uhrzeit) an das Ende von `systeminfo.txt` hinzu, ohne den bestehenden Inhalt zu überschreiben.

3. **Zeige die Liste aller Dateien** im aktuellen Verzeichnis mit `ls -l` an und leite die Ausgabe gleichzeitig in eine Datei `filelist.txt` und auf die Konsole um.

4. **Erstelle eine Datei `summary.txt`**, die die Anzahl der Zeilen in `systeminfo.txt` (mit `wc -l`) enthält.

---

## Hinweise

- **`>`** zum Überschreiben von Dateien
- **`>>`** zum Anhängen an Dateien  
- **`|`** für Pipelines zwischen Befehlen
- **`tee`** leitet Ausgaben gleichzeitig in eine Datei und auf die Konsole
- Überprüfe deine Ergebnisse mit `cat` oder `less`, z.B. `cat systeminfo.txt`

---

## Beispielbefehl für Schritt 1–3

```bash
uname -a > systeminfo.txt && date >> systeminfo.txt && ls -l | tee filelist.txt
```

---

## Ziel der Übung

Lerne die effiziente Verwendung von:
- **Output Redirection** (`>`, `>>`)
- **Pipelines** (`|`)
- **Kombination mehrerer Befehle** (`&&`)
- **Tee-Befehl** für parallele Ausgabe

**Zeitvorgabe: 10 Minuten**
