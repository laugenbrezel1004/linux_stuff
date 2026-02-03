# Shell Alias Aufgabe

## Ziel der Aufgabe
Erstelle einen benutzerdefinierten Shell-Alias, der beim Aufruf den aktuellen Benutzer begrüßt und das aktuelle Datum anzeigt.

## Aufgabenstellung
Implementiere einen Alias namens `hallo`, der folgende Funktionen ausführt:
- Begrüßung des aktuell eingeloggten Benutzers
- Anzeige des aktuellen Datums und der Uhrzeit

## Technische Details

### Alias-Definition
Der Alias soll folgende Befehle kombinieren:
```bash
echo "Hallo $USER! Heute ist $(date)"
```

### Alternative Benutzernamen-Abfrage
Statt `$USER` können Sie auch `$(whoami)` verwenden:
```bash
echo "Hallo $(whoami)! Heute ist $(date)"
```

## Implementierungsschritte

### 1. Shell-Konfigurationsdatei öffnen
```bash
nano ~/.bashrc
# oder
nano ~/.bash_aliases
```

### 2. Alias hinzufügen
Fügen Sie am Ende der Datei folgende Zeile hinzu:
```bash
alias hallo='echo "Hallo $USER! Heute ist $(date)"'
```

### 3. Konfiguration neu laden
```bash
source ~/.bashrc
# oder
source ~/.bash_aliases
```

### 4. Alias testen
```bash
hallo
```

## Erwartete Ausgabe
```
Hallo username! Heute ist Mon Dec 11 14:30:25 CET 2023
```

## Zeitaufwand
🕐 Geschätzte Bearbeitungszeit: **15 Minuten**

## Hilfreiche Befehle
- `whoami` - zeigt den aktuellen Benutzernamen an
- `date` - zeigt das aktuelle Datum und die Uhrzeit an
- `alias` - listet alle definierten Aliase auf

## Tipps
- Stellen Sie sicher, dass Sie die richtige Konfigurationsdatei für Ihre Shell verwenden
- Verwenden Sie Anführungszeichen korrekt, um Variablen und Befehle zu expandieren
- Testen Sie den Alias in einem neuen Terminal-Fenster, falls er nicht sofort funktioniert
