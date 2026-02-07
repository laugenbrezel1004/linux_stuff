# Manpage Cheatsheet: `man` Command

## Grundlegende Syntax
```bash
man [options] [section] page
```

## Manual Sections
| Section | Beschreibung |
|---------|--------------|
| 1 | Allgemeine Befehle |
| 2 | Systemaufrufe |
| 3 | Bibliotheksfunktionen |
| 4 | Kernel-Schnittstellen |
| 5 | Dateiformate |
| 6 | Spiele |
| 7 | Verschiedene Informationen |
| 8 | Systemadministrator-Handbuch |
| 9 | Kernel-Entwickler-Handbuch |

## Häufig verwendete Optionen

```bash
man ls                   # Manpage für ls anzeigen
man 8 adduser            # Section 8 von 'adduser' einsehen
man -k stat              # Alle Manpages mit dem Keyword 'stat' suchen
man -f ls                # Kurzbeschreibung und verschiedene Sektionen anzeigen (wie whatis)
```

### whatis 
```bash
whatis ls                # Kurzbeschreibung für Befehl
man -f ls                # Gleiche Funktion
```

### apropos
```bash
apropos ssh              # Durchsucht alle Manpages
man -k ssh               # Gleiche Funktion
```

## Praktische Beispiele

```bash
# Grundlegende Nutzung
man ls
man 3 printf

# Erweiterte Suche mit wildcards/regex
man -k "^printf"         # Sucht nach printf am Anfang des Titels
```
