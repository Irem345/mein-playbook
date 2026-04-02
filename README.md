# Ansible Playbook – Infrastruktur Automatisierung

## Ausführung

Das Playbook wird mit folgendem Befehl gestartet:

ansible-playbook -i inventory/hosts.ini site.yml --ask-become-pass

Vor der Ausführung müssen ggf. Variablen in group_vars/all.yml angepasst werden.

---

## Wahlapplikationen

### htop

htop ist ein Tool zur Überwachung von Prozessen und Systemleistung.
Ich habe es gewählt, weil es eine übersichtliche Darstellung von CPU und RAM bietet.

### Wireshark

Wireshark ist ein Netzwerk-Analyse-Tool.
Ich habe es gewählt, um Netzwerkverkehr analysieren zu können.

---

## nmap-Ergebnis

PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http

Kommentar:
Die Ports 22 und 80 sind offen, da SSH und Apache aktiv sind.
Andere Ports sind geschlossen, was der Firewall-Konfiguration entspricht.

---

## Reflexion

In diesem Projekt habe ich gelernt, wie man Infrastruktur mit Ansible automatisiert. Besonders schwierig war das Arbeiten mit YAML, da kleine Fehler grosse Probleme verursachen können. Ich hatte Probleme mit der Apache-Konfiguration, weil ein Tippfehler den Dienst am Starten gehindert hat.

Ich habe die Fehler gelöst, indem ich die Fehlermeldungen analysiert und Schritt für Schritt angepasst habe. Dabei habe ich auch KI verwendet, um schneller zu verstehen, wo das Problem liegt.


