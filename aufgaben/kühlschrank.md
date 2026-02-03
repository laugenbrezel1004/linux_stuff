# ❄️ Mission: Der neue Tiefkühlschrank (Storage-Management)

### Die Geschichte
Die Küche platzt aus allen Nähten! Der Chef hat einen neuen Tiefkühlschrank (eine neue Festplatte) gekauft. Deine Aufgabe als IT-Praktikant ist es, diesen Schrank betriebsbereit zu machen, ihn in das Küchensystem einzubinden und zu überwachen.

---

## 🎯 Deine Aufgabe

### Schritt 1: Den Schrank finden und inspizieren
Der neue Schrank wurde gerade angeschlossen.
1.  Finde heraus, wie die neue "Platte" heißt: `lsblk`
2.  Lass dir die eindeutige ID (UUID) anzeigen: `blkid`

### Schritt 2: Fächer einbauen (Partitionieren)
Ein großer Schrank ohne Regale ist nutzlos.
1.  Nutze `fdisk /dev/loopX` (dein Device), um eine neue Partition anzulegen.
2.  Erstelle eine primäre Partition, die den ganzen Platz nutzt.

### Schritt 3: Den Schrank auswischen (Formatieren)
Damit wir Lebensmittel lagern können, brauchen wir eine saubere Oberfläche (Dateisystem).
1.  Formatiere die neue Partition mit dem Standard-Dateisystem: `mkfs.ext4 /dev/loopXp1`

### Schritt 4: Den Schrank in die Küche schieben (Mounten)
Der Schrank steht noch im Flur. Wir müssen ihn an der richtigen Stelle in der Küche verfügbar machen.
1.  Erstelle einen Ordner: `sudo mkdir /mnt/tiefkuehlschrank`
2.  Hänge die Platte dort ein: `sudo mount /dev/loopXp1 /mnt/tiefkuehlschrank`

### Schritt 5: Inventur und Füllstand (df & du)
1.  Prüfe, wie viel Platz im neuen Schrank noch frei ist: `df -h`
2.  Kopiere ein paar Testdateien hinein und schau, wie viel Platz dieser "Vorrat" verbraucht: `du -sh /mnt/tiefkuehlschrank`

### Schritt 6: Den Schrank abschließen (lsof & umount)
Der Chef will den Schrank verschieben, aber jemand hat noch die Tür offen!
1.  Versuche `sudo umount /mnt/tiefkuehlschrank`, während du mit `cd` im Verzeichnis stehst. (Es wird fehlschlagen!)
2.  Nutze `lsof /mnt/tiefkuehlschrank`, um den "Übeltäter" (den Prozess) zu finden.
3.  Gehe aus dem Ordner raus und hänge ihn erfolgreich aus.