# Shell-Skript Aufgabe (20 Minuten)

## Aufgabenstellung

Schreibe ein Shell-Skript, das folgende Funktionen erfüllt:

### Grundanforderungen:
1. Den Benutzer nach seinem Namen fragen
2. Bei Eingabe des Namens den Benutzer begrüßen
3. Das aktuelle Datum und die Uhrzeit anzeigen
4. Das Skript soll ohne `./` ausführbar sein (PATH-Anpassung)

### Erweiterungsmöglichkeiten:
- If-Else-Logik implementieren
- Mit Übergabeparametern arbeiten
- Default-Variablen verwenden

---

## Musterlösung

### 1. Shell-Skript erstellen

```bash
#!/bin/bash

# Shell-Skript: Begrüßung mit Datum und Uhrzeit
# Autor: [Dein Name]
# Datum: $(date +%Y-%m-%d)

# Default-Name falls kein Parameter übergeben wird
DEFAULT_NAME="Gast"

# Funktion zur Anzeige der Hilfe
show_help() {
    echo "Verwendung: $0 [OPTIONEN] [NAME]"
    echo ""
    echo "Optionen:"
    echo "  -h, --help    Zeige diese Hilfe an"
    echo "  -d, --date    Zeige nur Datum an (ohne Uhrzeit)"
    echo "  -t, --time    Zeige nur Uhrzeit an (ohne Datum)"
    echo ""
    echo "Beispiele:"
    echo "  $0                   # Fragt nach dem Namen"
    echo "  $0 Max               # Begrüßt Max direkt"
    echo "  $0 -d Anna           # Begrüßt Anna mit nur Datum"
}

# Funktion zur Begrüßung
greet_user() {
    local name=$1
    local show_date=$2
    local show_time=$3
    
    echo "Hallo $name!"
    
    if [ "$show_date" = "true" ] && [ "$show_time" = "true" ]; then
        echo "Es ist $(date '+%A, %d. %B %Y, %H:%M:%S Uhr')"
    elif [ "$show_date" = "true" ]; then
        echo "Heute ist $(date '+%A, %d. %B %Y')"
    elif [ "$show_time" = "true" ]; then
        echo "Es ist $(date '+%H:%M:%S Uhr')"
    else
        echo "Es ist $(date)"
    fi
}

# Variablen initialisieren
SHOW_DATE=true
SHOW_TIME=true
USER_NAME=""

# Parameter verarbeiten
while [[ $# -gt 0 ]]; do
    case $1 in
        -h|--help)
            show_help
            exit 0
            ;;
        -d|--date)
            SHOW_TIME=false
            shift
            ;;
        -t|--time)
            SHOW_DATE=false
            shift
            ;;
        *)
            USER_NAME="$1"
            shift
            ;;
    esac
done

# Hauptprogramm
echo "=== Willkommen beim Begrüßungsskript ==="
echo ""

# If-Else: Namen ermitteln
if [ -n "$USER_NAME" ]; then
    # Name wurde als Parameter übergeben
    greet_user "$USER_NAME" "$SHOW_DATE" "$SHOW_TIME"
else
    # Nach Namen fragen
    read -p "Wie heißt du? " input_name
    
    if [ -z "$input_name" ]; then
        echo "Kein Name eingegeben. Verwende Standardname."
        greet_user "$DEFAULT_NAME" "$SHOW_DATE" "$SHOW_TIME"
    else
        greet_user "$input_name" "$SHOW_DATE" "$SHOW_TIME"
    fi
fi

echo ""
echo "Vielen Dank für die Nutzung des Skripts!"
```

### 2. Skript ausführbar machen

```bash
# Skript speichern als 'greeting' (ohne .sh Erweiterung)
chmod +x greeting
```

### 3. PATH konfigurieren (Optionen)

**Option A: Lokales Verzeichnis zum PATH hinzufügen**
```bash
# Temporär für aktuelle Session
export PATH=$PATH:$(pwd)

# Dauerhaft in ~/.bashrc oder ~/.bash_profile
echo 'export PATH=$PATH:~/meine-skripte' >> ~/.bashrc
source ~/.bashrc
```

**Option B: Skript in systemweiten PATH verschieben**
```bash
# Systemweit verfügbar machen (benötigt sudo)
sudo cp greeting /usr/local/bin/
```

---

## Beispiele für die Ausführung

### Beispiel 1: Interaktive Eingabe
```bash
greeting
```
**Ausgabe:**
```
=== Willkommen beim Begrüßungsskript ===

Wie heißt du? Anna
Hallo Anna!
Es ist Montag, 18. Dezember 2023, 14:30:25 Uhr

Vielen Dank für die Nutzung des Skripts!
```

### Beispiel 2: Mit Parameter
```bash
greeting Max
```
**Ausgabe:**
```
=== Willkommen beim Begrüßungsskript ===

Hallo Max!
Es ist Montag, 18. Dezember 2023, 14:30:25 Uhr

Vielen Dank für die Nutzung des Skripts!
```

### Beispiel 3: Nur Datum anzeigen
```bash
greeting -d Sarah
```
**Ausgabe:**
```
=== Willkommen beim Begrüßungsskript ===

Hallo Sarah!
Heute ist Montag, 18. Dezember 2023

Vielen Dank für die Nutzung des Skripts!
```

---

## Lernziele erreicht

✅ **Basisfunktionalität**: Benutzereingabe, Begrüßung, Datum/Uhrzeit  
✅ **If-Else-Logik**: Unterschiedliche Behandlung von Eingaben  
✅ **Parameterverarbeitung**: Flexible Skript-Nutzung  
✅ **Default-Variablen**: Fallback-Werte bei fehlenden Eingaben  
✅ **PATH-Integration**: Ausführung ohne `./`  
✅ **Zusätzliche Features**: Hilfe-Funktion, Formatierungsoptionen  

**Zeitaufwand**: ≈ 20 Minuten
