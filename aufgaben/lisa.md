Lisa, eine junge Systemadministratorin, hat von ihrem Chef eine besondere Aufgabe bekommen.
"In unserem Verzeichnis `company` sollen wichtige Dokumente sicher aufbewahrt werden", erklärte der Chef. "Wir brauchen drei Ebenen der Zugangsberechtigung." Lisa nickte und machte sich an die Arbeit. Sie erstellte folgende Struktur:

```bash
/var/company/treasure/
├── public/
├── team/
└── secret/
```

Ihre Aufgabe bestand nun darin, die Benutzer für den `chef` (mit Homeverzeichnis) und für die zwei Mitarbeiter `otto` und `frida` (beide ohne Homeverzeichnis) anzulegen.Außerdem soll sie die Gruppe `projektteam` erstellen und Otto und Frida hinzufügen.

Des Weiteren soll sie die Verzeichnisberechtigungen wie folgt anpassen:
1. Alle Mitarbeiter sollen Lesezugriff auf das Verzeichnis "public" haben, aber nur der Chef soll darin schreiben dürfen. 
2. Nur Mitglieder der Gruppe `projektteam` sollen Lese- und Schreibzugriff auf das Verzeichnis `team` bekommen.
3. Ausschließlich der Chef soll vollen Zugriff auf das Verzeichnis `secret` haben.


Lisa ist unerwartet krank geworden. Der Chef muss das Einpflegen eines neuen Benutzers nun selbst erledigen. Schlüpfe in den Benutzer `chef` und lege einen neuen Benutzer `carsten` an, welcher ebenfalls in der Gruppe `projektteam` ist und über ein Home-Verzeichnis verfügen soll.

Oh nein! Otto hat sein Passwort vergessen und es muss zurückgesetzt werden! Setze es für ihn zurück.


<details>
<summary>Für die ganz schnellen</summary>
Sorge dafür, dass alle Dateien in  `team` automatisch der Gruppe `projektteam` zugeordnet werden, unanhängig davon wer die Datei erstellt hat.
</details>


