## 🔥 Aufwärmübung 
Gib die dritt- und viertletzte Zeile der Datei „/etc/passwd“ aus, und ersetze alle Kleinbuchstaben mit Großbuchstaben.

<details>
<summary>💡 Tipps</summary>
RTFM!
( tr, head, tail)



---
### Beispielaufgabe
**"Zeige Dateien nach Größe sortiert an"**
```bash
ls -l | sort -k5 -nr
```
### 💡 Ideen für Programme-Kombinationen
- `grep` + `sort` + `head/tail`
- `find` + `wc` + `awk`
- `ls` + `cut` + `uniq`
- `ps` + `grep` + `sort`
