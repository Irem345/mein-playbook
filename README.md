# Ansible Projekt – Infrastruktur Automatisierung

## Ausführung

Das Playbook wird mit folgendem Befehl gestartet:

```bash
ansible-playbook -i inventory/hosts.ini site.yml --ask-become-pass
```

Vor der Ausführung müssen in der Datei group_vars/all.yml Variablen angepasst werden, zum Beispiel der Webseiten-Name oder Pfade wie /var/www/mywebsite. Diese Werte bestimmen, wie der Server konfiguriert wird.



## Wahlapplikationen

**htop**:
htop ist ein Tool zur Überwachung von Systemressourcen wie CPU und RAM. Ich habe es gewählt, um die Auslastung des Servers einfach und übersichtlich zu sehen. Meine Konfiguration installiert htop automatisch, sodass es direkt verwendet werden kann.

**vsftpd**:
vsftpd ist ein FTP-Server, mit dem Dateien übertragen werden können. Ich habe es gewählt, um eine zusätzliche Netzwerkfunktion auf meinem Server zu haben. Meine Konfiguration installiert und startet den FTP-Dienst, sodass er direkt verfügbar ist.

**Wireshark**:
Wireshark ist ein Tool zur Analyse von Netzwerkverkehr. Ich habe es gewählt, um zu sehen, wie Daten zwischen Client und Server übertragen werden. Meine Konfiguration installiert Wireshark automatisch, sodass ich Netzwerkpakete analysieren kann.

## nmap-Ergebnis

```bash
nmap localhost

PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http
21/tcp open  ftp
```

Offen sind die Ports 22 (SSH), 80 (HTTP) und 21 (FTP). Alle anderen Ports sind geschlossen. Das entspricht den UFW Regeln, da nur die benötigten Dienste erlaubt wurden und alles andere blockiert ist.



## Reflexion

In diesem Projekt habe ich gelernt, wie man mit Ansible eine komplette Serverumgebung automatisiert. Neu für mich war vor allem die Arbeit mit Rollen, YAML-Dateien und die Struktur eines Playbooks. Am Anfang hatte ich viele Probleme mit der YAML Syntax, besonders mit Einrückungen, was oft zu Fehlermeldungen geführt hat. Diese Fehler habe ich gelöst, indem ich die Struktur genau überprüft und die Fehlermeldungen Schritt für Schritt analysiert habe.

Ein weiteres Problem war Apache, da der Server oft nicht starten konnte. Der Grund war meistens ein Fehler in der VirtualHost Konfiguration. Mit dem Befehl apache2ctl configtest konnte ich diese Fehler finden und korrigieren. Auch Git war am Anfang schwierig, da ich nicht wusste, dass man einen Token statt eines Passworts verwenden muss.

Ich habe KI genutzt, um Fehler schneller zu verstehen und Lösungen zu finden, besonders bei Ansible und Apache. Ohne KI hätte ich vieles auch selbst herausfinden können, aber es hätte deutlich länger gedauert. Insgesamt habe ich viel über Server, Netzwerke und Automatisierung gelernt.

KI verwendet bei: Apache Konfiguration, vhost Konfiguration, Probleme lösen und ufw Konfiguration.
Quellen: 
https://linuxcapable.com/how-to-install-htop-on-ubuntu-linux/
https://serverspace.io/de/support/help/basic-commands-ufw/
https://ubuntu-user.de/tech/wireshark-unter-ubuntu-installieren-anleitung/
https://de.linux-terminal.com/?p=8524


