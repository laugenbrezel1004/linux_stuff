# 🛡️ Mission: Der System-Admin-Alltag
In dieser Übung schlüpfst du in die Rolle des IT-Admins. Du musst den kompletten Lebenszyklus eines Benutzers auf deinem Linux-System verwalten.

# 🚩 Teil 1: Ein neuer Kollege kommt an

Ein neuer Mitarbeiter namens Kevin fängt heute an.

Deine Aufgabe: Erstelle den Benutzer kevin.

Anforderung: Er soll automatisch ein Home-Verzeichnis erhalten und als Standard-Shell die /bin/bash nutzen.

Kontrolle: Überprüfe in der Datei /etc/passwd, ob der Benutzer korrekt angelegt wurde.

# 🔑 Teil 2: Das Montags-Problem

Es ist Montagmorgen und Kevin hat bereits sein Passwort vergessen. Er kann sich nicht einloggen.

Deine Aufgabe: Setze Kevins Passwort zurück, ohne sein altes Passwort zu kennen.

Kontrolle: Werde Kevin...

Zusatz-Challenge: Sorge dafür, dass Kevin sein Passwort bei der nächsten Anmeldung zwingend ändern muss (Stichwort: Password Expiry).


# 🚪 Teil 3: Das Offboarding

Kevin verlässt die Firma wieder (er hat ein besseres Angebot als Windows-Admin bekommen).

Deine Aufgabe: Lösche den Benutzer kevin.

Wichtig: Achte darauf, dass auch sein Home-Verzeichnis komplett vom System verschwindet, damit kein Datenmüll zurückbleibt.

Kontrolle: Prüfe mit ob Kevins' Home-Verzeichnis nicht mehr vorhanden ist.