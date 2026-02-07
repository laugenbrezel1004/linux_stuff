# Linux File Hierarchy Standard (FHS) Cheatsheet

## 📁 Wichtige Verzeichnisse im Linux Root (`/`)

| Pfad        | Kurz & Knapp | Für Anfänger relevant |
|-------------|--------------|-----------------------|
| `/`         | Baumwurzel – alles hängt hier drunter | einfach wissen |
| `/home`     | Persönlicher Ordner (`/home/USER`) | **deine Dateien** |
| `/etc`      | System-Konfigurationen | wenn was kaputt ist, hier schauen |
| `/bin` → `/usr/bin` | Basis-Befehle (`ls`, `cp`, …) – heute **Symlink** nach `/usr/bin` | täglich genutzt |
| `/sbin` → `/usr/sbin` | Admin-Befehle (`reboot`, `fdisk`) – ebenfalls **Symlink** | sudo-Bereich |
| `/usr`      | Standard-Programme & Bibliotheken – dank **usrmerge** alles in `/usr` | brauchst du nie direkt |
| `/var`      | Wechselnde Daten (Logs in `/var/log`) | Fehler finden |
| `/tmp`      | Temp-Daten (wird geleert) | zum Spielen, aber nichts Wichtiges |
| `/boot`     | Kernel & Bootloader | **nicht anfassen** |
| `/dev`      | Hardware als Dateien | USB-Stick erscheint hier |
| `/media`    | Automatisch eingehängte USB/Festplatten | einfach drauf zugreifen |
| `/mnt`      | Manuell eingehängte Laufwerke | selten nötig |
| `/root`     | Home-Verzeichnis des Admin-Accounts (root) | nicht verwechseln mit `/` |
| `/proc` & `/sys` | Virtuelle System-Infos | nur zum Anschauen |
| `/opt`      | Große Extra-Programme (Chrome, Discord …) | selten nötig |

> **usrmerge**: moderne Distributionen fassen `/bin`, `/sbin`, `/lib*` nach `/usr` zusammen – die alten Pfade sind nur noch **Symlinks** auf das jeweilige `/usr/…`-Gegenstück.

## Zusätzliche Navigationhilfe
| Symbol | Bedeutung |
|--------|-----------|
| .      | Aktuelles Verzeichnis|
| . .    | Elternverzeichnis (Eins höher)
| ~      | Home-Verzeichnis des aktuellen Benutzers |

## Absoluter vs. Relativer Pfad

### Absoluter Pfad
* Beginnt immer mit `/`
* Beispiel:`/home/laurenz/Dokumente/42`

### Relativer Pfad
* Beginnt ohne `/`, ist immer relativ zum aktuellen Standpunkt/Verzeichnis
* Beispiel: `Dokumente/42`, wenn man sich in `/home/laurenz` befindet



## Arbeiten im FHS, ein paar nützliche Befehle
| Befehl | Bedeutung |
|--------|-----------|
| sudo      | Befehl mit Superuser-Rechten ausführen|
| pwd      | Aktuelles Verzeichnis anzeigen|
| cd      | In ein Verzeichnis wechseln|
| whoami      | Wer bin ich überhaupt?|
| ls      | Inhalt eines Verzeichnisses auflisten|
| cp      | Dateien kopieren|
| mv      | Datein verschiedenen oder umbenenen|
| rm      | Datein/ Verzeichnisse löschen|
| rmdir      | Verzeichnisse löschen|
| mkdir       | Verzeichnisse anlegen|



---

*Hinweis: Die Struktur kann zwischen verschiedenen Linux-Distributionen leicht variieren.*
