# 👨‍🍳 Mission: Der digitale Küchen-Praktikant 

### Die Geschichte
Der Chefkoch ist es leid: Ständig fehlen Zutaten, weil niemand rechtzeitig Bescheid gibt. Er hat dich, den neuen **IT-Küchen-Praktikanten**, beauftragt, die Vorratskammer permanent zu überwachen.

Da du keine Lust hast, alle 10 Sekunden manuell nachzusehen, schreibst du ein Skript, welches dir die Arbeit abnimmt. 

---

## 🎯 Deine Aufgabe: Das Überwachungs-Skript

Erstelle ein Bash-Skript namens `vorrats-check.sh` in deinem Home-Verzeichnis. Dieses Skript soll eine permanente Datei Namens `vorratskammer.txt` in deinem Home-Verzeichnis überwachen und eine Warnung ausgeben, wenn die Kammer leer ist.



Schreibe das Skript so, dass es folgendes tut:
1.  **Endlos-Schleife:** Es muss dauerhaft laufen wenn es einmal gestartet wurde.
2.  **Inhalt prüfen:** Es liest alle 10 Sekunden die Datei `~/vorratskammer.txt` aus.
3.  **Alarm-Bedingung:** Wenn in der Datei das Wort **"leer"** gefunden wird:
    * Soll eine Warnung ("⚠️ ALARM: Kammer leer! Nachschub holen! ⚠️") ausgegeben werden.
4.  **Pause:** Nach jedem Durchlauf wartet das Skript genau 10 Sekunden (`sleep 10`).
