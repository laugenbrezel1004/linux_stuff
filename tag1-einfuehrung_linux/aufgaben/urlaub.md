# Linux-Verzeichnisverwaltung - Übungsaufgabe

## 📋 Aufgabenstellung

Du hast deine Urlaubsfotos unorganisiert gespeichert und kannst ein wichtiges Foto aus dem Mallorca-Urlaub nicht finden. Jetzt möchtest du die Fotos nachträglich ordnen.

---
## Pfadvereinfachung
**Vereinfache die folgende Pfade:**
```bash
/home/user/../user/./Documents/../Downloads/file.txt
/var/www/html/../../etc/./nginx/conf.d/../sites-available
./../../../usr/local/./bin/../bin
```


## Verzeichnisse erstellen 


**Anforderungen:**
- Hauptverzeichnis: `~/Bilder/`
- Drei Unterverzeichnisse für verschiedene Urlaube:
  - `Mallorca_2023`
  - `Alpen_2022` 
  - `SchwaebischesMeer_2021`
- Im Mallorca-Verzeichnis ein zusätzliches Unterverzeichnis: `Ballermann`



---

## Falsches Jahr...

**Problem:** Der Mallorca-Urlaub fand bereits 2022 statt - das Verzeichnis muss korrigiert werden.


---

## Verzeichnisse löschen

**Situation:** Du hast bemerkt, dass alle Fotos bereits auf CD gesichert sind und werden auf dem PC nicht mehr benötigt. Lösche die Verzeichnisse wieder.

---

<details>

<summary>Tipp 💡</summary>


| Könnten behilflich sein... |
|--------|
| `mkdir` |
| `mv` |
| `rm` |
| `rmdir` | 

</details>

## ⚠️ Sicherheitshinweise

- `rm -r` löscht **unwiderruflich** - verwende es mit Vorsicht!
- Immer zuerst mit `ls` prüfen, was gelöscht werden soll
- Bei wichtigen Daten: Backup erstellen!

---

Jetzt sind deine Fotos (zumindest theoretisch) perfekt organisiert! 🎉
