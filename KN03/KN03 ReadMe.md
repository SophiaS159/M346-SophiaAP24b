# KN03: IaaS - Virtuelle Server

## Lernziele
- Sie machen die ersten Schritte mit IAAS.
- Eigene manuelle Installation einer virtuellen Instanz. Sie können Services auf einer virtuellen Instanz installieren und Dateien aus einem Git-Repo herunterladen und verwenden.
- Sie lernen wie Sie eine Sicherheitsgruppe (Firewall) erstellen, resp. verändern.
----

## A) Installation von Web- und Datenbankserver (60%)

**sudo apt update:**
![](sudoaptupdate.png)

**sudo apt install apache2:**
![](sudoaptinstallapache2.png)

**sudo apt install php:**
![](sudoaptinstallphp.png)

**sudo apt install libapache2-mod-php:**
![](installlibapache2mod.png)

**sudo apt install mariadb-server:**
![](installmariadb.png)

**sudo apt install php-mysql:**
![](sudoaptinstallphpmysql.png)

**sudo mysql -u root -e "GRANT ALL ON *.* TO 'admin'@'%' IDENTIFIED BY 'Ihr-Passwort' WITH GRANT OPTION;":**
![](createadminuser.png)

**sudo systemctl restart mariadb.service & sudo systemctl restart apache2:**
![](restart.png)

**git clone https://gitlab.com/ch-tbz-it/Stud/m346/m346scripts.git:**
![](clonefromgitlab.png)

<br/>

### Seiten

info.php:
![](infophp.png)

db.php:
![](dbphp.png)

index.html:
![](indexhtml.png)

<br/>

### Öffentliche Ip

![](InstanceIp.png)

<br/>

### Regeln der Sicherheitsgruppe

![](SecurityGroup.png)

<br/>

### Screenshot der Mysql Konsole Befehls
Es zeigt alle Grants des Admin User's an (bw, der Command der wir in der Konsole geschrieben haben):
![](mysqlAdminLogin.png)

----
