# KN10: Kostenberechnung

## Lernziele
- Sie lernen verschiedene Kostenrechner kennen und erstellen und vergleichen die Kosten von mehreren Providern.
- Sie verstehen was die Möglichkeiten und Limitierungen der Migrationsmodelle sind.
----

### A) Kostenrechnung IAAS - Rehosting (60%)


## Azure Erklärung zur Auswahl der Komponenten
#### Webserver:
- On-Premise: 1 Core, 2 GB RAM, 20 GB Speicher
- Azure: B1ms VM, 1 vCPU, 2 GB RAM, S4 SSD 32 GB
- Abweichung: Disk minimal größer (32 GB statt 20 GB) → nötig wegen Azure-Standardgrößen
- Backup: tägliche/wöchentliche/monatliche Retention, LRS


#### Datenbankserver:
- On-Premise: 2 Cores, 4 GB RAM, 100 GB Speicher
- Azure: DC2ds v3 VM, 2 vCPU, 16 GB RAM, S10 SSD 128 GB
- Abweichung: Mehr RAM und größere Disk für stabile DB-Performance
- Backup: gleiche Retention, LRS
#### Begründung:
- Komponenten möglichst nah an On-Premise angepasst
- Kleine Anpassungen (RAM/Disk) für Performance, Stabilität und Azure-Standards
- Backup-Retention identisch übernommen für Datensicherheit

----


### B) Kostenrechnung PAAS - Replattforming (20%)
BlaBla

----


### C) Kostenrechnung SAAS - Repurchasing (10%)
BlaBla

----


### D) Interpretation der Resultate (10%)
BlaBla
