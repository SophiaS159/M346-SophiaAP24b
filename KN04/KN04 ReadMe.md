# KN04: Cloud-init/ Automatisierung

## Lernziele

- Wie lernen wie Sie die Installation von Servern automatisieren können und lernen dabei auch wie sie zur Fehlersuche vorgehen.
- Sie lernen die YAML Syntax
- Sie lernen Cloud-Init als Automatisierungstool kennen.
- Sie trennen die Services aus der früheren Installation und lassen die Services miteinander kommunizieren.
----

### A) Cloud-init File verstehen (10%)

    #cloud-config
Markiert die Datei als Cloud-Init-Konfigurationsdatei, damit Cloud-Init sie beim ersten Booten verarbeitet.

    users:
Beginnt die Liste der Benutzer, die erstellt oder konfiguriert werden sollen.

    - name: ubuntu
Name des Benutzers, der angelegt bzw. konfiguriert wird (hier: „ubuntu“).

    groups: [users, admin]
Gruppen, denen der Benutzer angehört.

    „users“ = Standard-Benutzergruppe
    „admin“ = Gruppe mit Administratorrechten (je nach OS ähnlich wie „sudo“)
    shell: /bin/bash
Standard-Shell, die der Benutzer beim Einloggen verwendet (hier Bash).

    sudo: ALL=(ALL) NOPASSWD:ALL
Sudo-Rechte für den Benutzer:
Dieser User darf alle Befehle als jeder Benutzer (inkl. root) ohne Passwort ausführen.

    ssh_authorized_keys:
Liste der erlaubten SSH-Keys, die sich ohne Passwort einloggen dürfen.

      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC0WGP1EZykEtv5YGC9nMiPFW3U3DmZNzKFO5nEu6uozEHh4jLZzPNHSrfFTuQ2GnRDSt+XbOtTLdcj26+iPNiFoFha42aCIzYjt6V8Z+SQ9pzF4jPPzxwXfDdkEWylgoNnZ+4MG1lNFqa8aO7F62tX0Yj5khjC0Bs7Mb2cHLx1XZaxJV6qSaulDuBbLYe8QUZXkMc7wmob3PM0kflfolR3LE7LResIHWa4j4FL6r5cQmFlDU2BDPpKMFMGUfRSFiUtaWBNXFOWHQBC2+uKmuMPYP4vJC9sBgqMvPN/X2KyemqdMvdKXnCfrzadHuSSJYEzD64Cve5Zl9yVvY4AqyBD aws-key
Öffentlicher SSH-Schlüssel, der für den Benutzer „ubuntu“ freigeschaltet ist.
Der Text nach dem Schlüssel („aws-key“) ist nur ein Kommentar / eine Bezeichnung.

    ssh_pwauth: false
Passwort-Login per SSH ist deaktiviert.
Nur SSH-Schlüssel sind erlaubt → sicherer.

    disable_root: false
root-Benutzer wird NICHT deaktiviert.
root kann weiterhin existieren und sich ggf. einloggen (abhängig von SSH-Konfiguration).

    package_update: true
Führt automatisch ein "apt update" beim ersten Booten aus, damit alle Paketlisten aktuell sind.

    packages:
Liste der Pakete, die Cloud-Init beim Boot installieren soll.

    - curl
Installiert das Paket „curl“ (Tool für Webrequests).

    - wget
Installiert das Paket „wget“ (Download-Tool für Dateien).

----


### B) SSH-Key und Cloud-init (15%)
Bilder der Instanz:
![](InfoInstanz1.png)
![](InfoInstanz2.png)

Diskgrösse: 8

Betriebssystem: Ubuntu Vers 24.04

Grösse des RAM's: 1

Anzahl des CPU's: 1

----


### C) Zugriff mit SSH-Key (40%)

Sophia1 Key Message:
![](Sophia1Key.png)

Sophia2 Key Message:
![](Sophia2Key.png)

Verwendete Schlüssel Liste:
![](List.png)
