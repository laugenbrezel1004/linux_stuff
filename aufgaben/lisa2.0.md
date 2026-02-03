# 🚀 Mission: Operation Datenrettung

„Wow Lisa, das hast du aber gut gemacht!“, sagte der Chef gut gelaunt.  
„Daher möchte ich dich mit einer noch wichtigeren Aufgabe beauftragen.“

---

## 📋 Das Briefing am Schreibtisch

Der Chef lehnt sich über Lisas Monitor. „Wir haben noch nie Backups gemacht, und du weißt ja: **Kein Backup, kein Mitleid!**“

### Die Anforderungen:
| Feature             | Beschreibung                                      |
|:--------------------|:--------------------------------------------------|
| **Trigger**         | Das Skript muss bei jedem **Systemstart** laufen. |
| **Quelle**          | Das Homeverzeichnis des Chefs (`/home/chef`).     |
| **Ziel**            | Gesichert wird nach `/var/backups/`.              |
| **Naming**          | Zeitstempel im Format `YYYY-MM-DD_HH-MM`.         |
| **Implementierung** | Tar-Archive, mit dem Zeitstempel                  |
| **Limit**           | Maximal **3 Backups** (KI-Budgetkrise 💸).        |

---


So ambitioniert wie Lisa ist, macht sie sich direkt an die Arbeit und hämmert den Code in ihr Terminal...


# 😱 Der „Oh Nein!“-Moment

Plötzlich hallt ein Schrei durch das Büro, der Mark und Bein erschüttert:

> **„Oh Nein!!!!“** > — *Der Chef (hat gerade versehentlich sein Homeverzeichnis gelöscht)*

Ein betretenes Schweigen legt sich über die Etage. Alle Augen richten sich auf Lisa. Sie lehnt sich entspannt zurück, nippt an ihrem Mate-Tee und tippt einen einzigen Befehl ein, um das letzte Archiv aus `/var/backups/` zu entpacken....

**Daten gerettet. Tag gerettet. Job sicher.**

---

## 🏆 Das goldene Fazit

> ### Die Goldene Regel des Restores:
> „Ein Backup, das nicht erfolgreich getestet wurde, existiert nicht.“

---