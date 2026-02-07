# Linux Fehlermeldungen Cheatsheet

## Grundlegendes zu Fehlermeldungen
- **Immer lesen!** Linux sagt genau, was wo falsch gelaufen ist
- Fehlermeldungen bestehen meist aus drei Komponenten:
  ```
  Programmname: Fehlerdetails: Fehlertyp
  Beispiel: ls: cannot access '/asdf': No such file or directory
  ```

## Häufige Fehler und Lösungen

### 🔍 `No such file or directory`
- **Ursache**: Datei/Verzeichnis existiert nicht
- **Lösung**: 
  - Pfad überprüfen: `ls /pfad/zur/datei`
  - Tippfehler korrigieren
  - Mit absoluten Pfaden arbeiten: `pwd` zeigt aktuelles Verzeichnis

### 📁 `File exists`
- **Ursache**: Datei/Verzeichnis soll erstellt werden, existiert aber bereits
- **Lösung**:
  - Anderen Namen wählen
  - Vorhandene Datei löschen/umbenennen
  - Überschreiben erzwingen (wenn sicher): `cp -f quelle ziel`

### 📂 `Not a directory` / `Is a directory`
- **Ursache**: Datei als Verzeichnis oder umgekehrt verwendet
- **Lösung**:
  - Typ überprüfen: `file pfad` oder `ls -l pfad`
  - Korrekten Befehl für Datei/Verzeichnis verwenden

### 🔒 `Permission denied`
- **Ursache**: Fehlende Berechtigungen
- **Lösung**:
  - Berechtigungen prüfen: `ls -l datei`
  - Mit Root-Rechten ausführen: `sudo befehl`
  - Berechtigungen anpassen: `chmod`/`chown`

### ❌ `Command not found`
- **Ursache**: Befehl/Programm nicht installiert oder nicht im PATH
- **Lösung**:
  - Installation prüfen: `which befehl`
  - Programm installieren
  - PATH variable prüfen: `echo $PATH`

## Exit Codes prüfen
```bash
befehl
echo $?  # Zeigt Exit-Code des letzten Befehls (0 = Erfolg; !0 = Fehler)
```

## Debugging-Tipps
1. **Fehlermeldung komplett lesen**
2. **Google-Suche**: Fehlermeldung in Anführungszeichen suchen
3. **Manpages konsultieren**: `man befehl`
4. **Logs prüfen**: `journalctl` oder `/var/log/`
