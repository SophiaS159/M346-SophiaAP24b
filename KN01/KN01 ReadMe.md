# KN01: Virtualisierung

## Lernziele
- Sie machen die ersten Schritte Virtualisierung
- Sie lernen die Grenzen der Virtualisierung kennen

---

### A) Hypervisor Typ 1 und 2 (30%)
_Hypervisor_

Die Definition Hypervisor ist ein Software/Programm, dass mehrere VMs( Virtuelle Maschinen) auf einem physischen Computer zu erstellen und dann auch problemlos benutzen können.

_Hypervisor Typ 1_

Hypervisor Typ 1 auch Bare-Metal-Hypervisor genannt, ist ein Visualisierungssoftware, die direkt auf einer physischen Servers installiert wird, anstelle eines Betriebssystems.

_Hypervisor Typ 2_

Hypervisor Typ 2 auch gehosteter Hypervisor genannt, ist eine Software, die als Anwendung auf einem bestehendem Host-Betriebssystem installiert wird. Es ermöglicht die einfache Ausführung von VMs, da er auf Ressourcen des Host-Systems zurückgreift.


<br/>

***Unterschiede zwischen den beiden Hypervisor Typen***

Der Hauptunterschied liegt and der Architektur der beiden Hypervisoren.

|  Merkmal  |  Typ 1  |  Typ 2  |
| ------------- |:-------------:| -----:|
| Installation | physischen Hardware | Host-Betriebssystem |
| Betriebssystem |funktioniert wie ein eigenes Betriebssystem und verwaltet Ressourcen direkt.|Benötigt Host-Betriebssystem, das als Zwischenschicht dient.|
| Sicherheit | Höher | Tiefer |
| Verwaltung | Komplexer | Einfacher |

----
### B) Virtualisierungssoftware (70%)
Gruppenarbeit: *Lynn Ruchti*

#### Vermutung meines Systems ####

Ich vermute mal das mein System von Typ 1 ist. Dies ist jegedlich eine Vermutung und bin mir ziemlich unsicher. Aber da ich ein Macbook habe, denke ich es würde Sinn machen das es von Typ 1 ist.

#### Meine Vermutung testen ####
Also dies sind meine folgende Werte.

*Total Numbers of Cores/Processors:* 8 (4 performance and 4 efficiency)

*RAM/Memory:* 16GB

----
#### VM angepasst ####

**Processoren & RAM**

Ich habe auf der VM die maxmimale Anzahle von Processors udn RAM eingestellt, nähmlich 8 Processoren und 16384MB. Und das VM kann nicht wirklich gestartet werden. Also hier ist ein Bild von der Einschränkung von Processoren & RAM.
![](Einschränkung.png)

**Erklärung**

Der Grund für die Einschränkung ist, weil ich habe der VM alle 16 GB Ram zugewisen und es nicht möglich war das VM sogar zu starten. Und weil die VM den gesamten Speicher benutzt, bleibt kein RAM mehr für macOS und andere Prozesse.

Der Grund wieso es überhaupt möglich ist es so einzustellen ist, dass Visualisierungssoftware erlaubt Overcommitment(Ressourcen-Überbuchung). Also man geht davon aus... 

- dass die VM nie gleichzeitig den kompletten zugewiesenen Speicher nutzt
- dass sie notfalls komprimieren oder auf der Festplatte(Hardware) auslagern kann



