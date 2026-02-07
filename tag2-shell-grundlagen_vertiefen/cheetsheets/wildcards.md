# Wildcards 

Shell Globbing ermöglicht es, Dateien und Verzeichnisse mit Mustern zu filtern.

## Wildcard-Übersicht

| Wildcard       | Bedeutung | Beispiel | Erläuterung |
|:---------------| :--- | :--- | :--- |
| `*`            | Beliebige Zeichenfolge (auch leer) | `*.jpg` | Findet alle Dateien, die auf `.jpg` enden (z. B. `foto.jpg`, `bild.jpg`). |
| `?`            | Genau ein beliebiges Zeichen | `Bild??.png` | Findet z. B. `Bild01.png` oder `Bildab.png`, aber nicht `Bild1.png`. |
| `[abc]`        | Auswahl aus bestimmten Zeichen | `datei[123].txt` | Findet `datei1.txt`, `datei2.txt` oder `datei3.txt`. |
| `[a-z]`        | Bereich von Zeichen | `log_[0-9].txt` | Findet `log_0.txt` bis `log_9.txt`. |
| `[^abc]` oder  `[!abc]`| Negation: Keines der Zeichen | `[!abc]*` | Findet alles, was **nicht** mit a, b oder c beginnt. |

---

## 🛡️ Maskieren (Escaping & Quoting)

Wildcard-Zeichen wie `*`, `?` oder `[` können als normale Zeichen in Dateinamen vorkommen. Um die Interpretation durch die Shell zu verhindern, müssen sie maskiert werden.

### 1. Backslash (`\`)
Maskiert das **direkt folgende** Zeichen.
* **Beispiel:** `ls Datei\?\.txt`
* *Effekt:* Sucht nach der Datei namens `Datei?.txt`.

### 2. Single Quotes (`' '`)
Schützen den **gesamten Inhalt** vor jeder Interpretation durch die Shell (keine Variablenersetzung).
* **Beispiel:** `ls '*.txt'`
* *Effekt:* Sucht nach einer Datei, die wortwörtlich `*.txt` heißt.

### 3. Double Quotes (`" "`)
Schützen die meisten Sonderzeichen, erlauben aber **Variablen-Ersetzung** (z. B. `$VAR`).
* **Beispiel:** `ls "Datei*.txt"`
* *Effekt:* Das `*` wird als Text behandelt, sucht nach `Datei*.txt`.

> **💡 Tipp:** 
>  man 7 glob