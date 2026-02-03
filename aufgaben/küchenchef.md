# 🧑‍🍳 Mission: Der Große Küchenchef

Du bist jetzt der **Küchenchef**!  
Deine Aufgabe ist es, ein interaktives Skript zu programmieren, das dir deine eigenen Köche (Prozesse) übersichtlich anzeigt, sortiert und dir erlaubt, sie gezielt zu beenden – alles über ein komfortables Menü.

---

## 🎯 Deine Aufgabe
Erstelle ein Bash-Skript, das folgende Funktionen erfüllt:

### 1. Alle meine Köche anzeigen
* Zeige nur Prozesse des **aktuellen Benutzers** an.
* Nutze eine schöne, lesbare Tabelle (Spalten: `PID`, `COMMAND`, `%MEM`, `%CPU`).

### 2. Einen Koch per PID rauswerfen
* Das Skript fragt nach der **PID**.
* Sicherheitsabfrage: „Bist du sicher? (j/n)“.
* Unddd Abflug..., raus mit dir!!!

### 3. Einen Koch per Namen rauswerfen
* Das Skript fragt nach dem **Programmnamen** (z. B. „firefox“ oder „sleep“).
* Zeigt zuerst alle passenden Prozesse an.
* Wirf den Koch aus der Küche.

### 4. Programm beenden
* Das Skript läuft in einer **Endlos-Schleife** mit Menü, bis der User „4“ eingibt.

---

## 🖥️ Beispiel-Durchlauf
```bash
$ ./küchen-manager.sh

=== 🧑‍🍳 KÜCHEN-MANAGER v1.0 ===
1) Alle meine Köche anzeigen 
2) Einen Koch per PID rauswerfen
3) Alle Köche eines Namens rauswerfen
4) Programm beenden

Deine Wahl: 1
PID     COMMAND         %MEM    %CPU
5678    firefox         12.4    8.1
2341    htop            1.2     0.5
...

Deine Wahl: 2
Welche PID soll rausfliegen? 5678
Bist du sicher? (j/n) j
✅ Koch 5678 wurde erfolgreich rausgeworfen!