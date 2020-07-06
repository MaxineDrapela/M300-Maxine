# M300
This is a repository that is used to document my process and which is used as a cloud.
### Dokumentation LB2 von Maxine Drapela


# Inhaltsverzeichnis

- [K1](#k1)
  - [Umgebung bereit machen](#umgebung-bereit-machen)
- [K2](#k2)
    - [Umgebung eingerichtet](#umgebung-eingerichtet)

- [M300](#m300)
    - [Dokumentation LB2 von Maxine Drapela](#dokumentation-lb2-von-maxine-drapela)
- [Inhaltsverzeichnis](#inhaltsverzeichnis)
  - [K1](#k1)
    - [Umgebung bereit machen](#umgebung-bereit-machen)
    - [SSH Key](#ssh-key)
    - [Git-Client](#git-client)
  - [K2 Umgebung eingerichtet](#k2-umgebung-eingerichtet)
    - [Persönlicher Wissensstand zu den Themen](#persönlicher-wissensstand-zu-den-themen)
      - [Virtualisierung mit Virtualbox](#virtualisierung-mit-virtualbox)
      - [Vagrant](#vagrant)
      - [Sicherheit](#sicherheit)
  - [K3 Vagrant](#k3-vagrant)
    - [vagrant-befehle](#vagrant-befehle)
    - [Vagrantfile](#vagrantfile)
    - [netzwerkplan](#netzwerkplan)
    - [Webalizer Installation](#webalizer-installation)
    - [sicherheitsaspekte](#sicherheitsaspekte)
    - [testfälle](#testfälle)
      - [Test 1 - Apache Webserver](#test-1---apache-webserver)
  - [K4 Sicherheitsaspekte implementieren](#k4-sicherheitsaspekte-implementieren)
    - [Firewall mit den Rules](#firewall-mit-den-rules)
    - [Reverse-Proxy Einrichtung](#reverse-proxy-einrichtung)
    - [Benutzer- und Rechtvergabe](#benutzer--und-rechtvergabe)
  - [Persönlicher Lernzuwachs/Reflexion](#persönlicher-lernzuwachsreflexion)
- [LB3](#lb3)
  - [K1 und K2](#k1-und-k2)
  - [K2](#k2)
    - [Persönlicher Wissenstand im Bezug auf die wichtigsten Themen](#persönlicher-wissenstand-im-bezug-auf-die-wichtigsten-themen)
  - [K3](#k3)
    - [Docker implementieren](#docker-implementieren)
    - [Befehle](#befehle)
      - [Netzwerkplan](#netzwerkplan-1)
      - [Schichtenmodell](#schichtenmodell)
  - [K4](#k4)
    - [Reflexion](#reflexion)
  
## K1
### Umgebung bereit machen
### SSH Key
    
SSH-Key erstellen

Man muss Git/Bash  ([https://git-scm.com/download/win](https://git-scm.com/download/win)) installieren um dann darauf Befehle auszuführen. 

Nun führt man folgenden Code aus um ein SSH Key zu erstellen. 

     $ ssh-keygen -t rsa -b 4096 -C "beispiel@beispiel.com"

Nun fragt man wo man den Schlüssen speichern soll. Um den Standard zu wählen klickt man einfach auf Enter. 

     Enter a file in which to save the key (~/.ssh/id_rsa):


Um dann den SSH Key dem SSH Agent hinzuzufügen kopiert man die Datei %HOME%/.ssh/id_rsa.pub oder $HOME/.ssh/id_rsa.pub und besucht daraufhin die Website [www.github.com](http://www.github.com/)
Dort öffnet man Settings > SSH Keys und erstellt ein neuer SSH Key unter "New SSH key" und gibt die kopierte Datei von der Zwischenablage ein. Sobald der SSH Key erkannt wird ist dieser eingerichtet und erledigt.


### Git-Client

Der Git-Client ist ein kommandozeilenbasierendes Tool, mit welchem man GitHub Repositories bedienen kann. Es kann mit dem Linux Bash verglichen werden, da sie im Prinzip gleich arbeiten. Dies kann man auf der offiziellen Website herunterladen und installieren.  
https://git-scm.com/downloads

Client konfigurieren

     
     $ git config --global username "username"
     $ git config --global user.email "e-mail "


Repositories importieren

Mit diesem Befehl werden Online Repositories im gewünschten Ordner importiert. 

     $ cd Wohin\auch\immer
	 $ git clone git@github.com:<Ihr Name>/my_M300.git
	 
Repository herunterladen	



Mit dem folgenden Befehl holt man alle Daten, die auf dem Online Service sind, herunter auf die lokale Maschine.

	$ git pull
	
	
## K2 Umgebung eingerichtet
Für LB2 mussten wir einen Github Account erstellen. Dies habe ich gemacht. Zudem ist ein Lernziel, die Dokumentation im Markdown zu führen. Dies habe ich so einrichten können. 
### Persönlicher Wissensstand zu den Themen
#### Virtualisierung mit Virtualbox
In diesem Modul lernen wir viel über die Virtualisierung von verschiedenen Diensten. Für die Virtualisierung benutzen wir Virtualbox.
Ich habe in der Vergangenheit bereits einmal mit Virtualbox gearbeitet und ich kam sehr gut damit klar. Der Vorteil bei Virtualbox ist, dass diese Software mit Vagrant kompatibel ist.
**Einrichtung Virtualbox**
Virtualbox hatte ich bereits auf dem Computer, also musste ich nichts installieren. Ich musste aber dennoch die ISO-Dateien herunterladen, die wir für die Vm's dann benötigten.
#### Vagrant

Mit Vagrant können wir virtuelle Maschinen viel einfacher und automatisierter erstellen.
**Einrichtug Vagrant**
Die Einrichtung mit Vagrant war recht simpel. Ich konnte alles so installieren, wie ich es mir vorgestellt habe. Anfangs hatte ich ein wenig Mühe, mich dran zu gewhöhnen, dass jetzt alles so einfach und schnell installiert werden kann.
#### Sicherheit
**reverse Proxy**
Der Reverse Proxy funktioniert ähnlich wie der Forward Proxy. Ein Außenstehender denkt er kommuniziere direkt mit mir, er wird jedoch zum Reverse Proxy weitergeleitet der meine Identität geheimhält und ihm eine andere zurückgibt. 

## K3 Vagrant
 ### vagrant-befehle
 Mit Vagrant kann man super viele Befehle anwenden. Hier sind die, die ich am meisten gebraucht habe:
 - `vagrant init ubuntu/xenial64` setzt eine VM auf
 - `vagrant up` startet die VM
 - `vagrant ssh` Stellt eine sichere verbindung via SSH mit der VM auf
 - `vagrant status` zeigt den Status der VM an
 - `vagrant halt` schaltet die VM aus
 - `vagrant destroy` löscht die VM komplett
 ### Vagrantfile
  Das Vagrantfile wird beim Starten einer Maschine sofort erstellt/ausgeführt. Es wird gebraucht um Vagrant zu konfigurieren oder um gewisse Funktionen und Einstellungen zu ändern. Vagrantfiles werden mit Ruby geschrieben, eine Programmiersprache. 
  **Vagrantfile bearbeiten**
  Da ich nicht so viel Erfahrung mit Vagrant allgemein habe, habe ich nur das minimum geändert, was gefragt wurde. Die Infos, wie ich es ändern musste, konnte ich durch das Github holen, oder teilweise auch im Internet. 
  `Vagrant.configure(2) do |Config|`
  So kann man es bearbeiten. Ich habe diesen Weg aber erst am Schluss entdeckt. Ich habe mein Vagrantfile mit dem Notepad++ bearbeitet.
  Mein Vagrantfile befindet sich unter "LB2" in meinem Github.


 ### netzwerkplan
 ![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/netzwerkplan.PNG "Netzwerkplan")
 Meinen Netzwekplan habe ich relativ simpel gehalten. Da mein Laptop nicht direkt am Router angeschlossen ist, habe ich dazwischen noch einen Access Point reingetan.
 ### Webalizer Installation
 Mit dem Programm Webalizer kann man verschiedene Log Dateien auswerten. Die Installation ist sehr simpel aufgebaut.
 Wenn wir davon ausgehen, dass wir vorher bereits alle Updates durchgeführt haben, dann muss man nur noch foglenden Befehl eingeben:
  - `sudo apt-get install -y webalizer`
  Das war's auch schon.

 ### sicherheitsaspekte
 ### testfälle
 #### Test 1 - Apache Webserver
 Ich habe in meiner Vagrantfile eine Portweiterleitung eingerichtet, sodass ich mit 8080 Port auf den Default Web Page komme.
 ![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/testapache.PNG "Default Apache Webpage")
 Das hat sehr gut geklappt. Die Default Seite hat sich angezeigt.



## K4 Sicherheitsaspekte implementieren
  ### Firewall mit den Rules
  Nun habe ich die Firewall UFW installiert. Ich habe die Ports 80 und 22 freigegeben für die IP 10.0.2.2. Bei diesem Punkt bin ich mir aber unsicher. 
  Ich habe zuerst alle Rules erstellt, und dann erst am Schluss die Firewall enabled.
  Folgende Befehle habe ich eingegeben:
  -  `sudo ufw allow from 10.0.2.2 to any port 22`
  -  `sudo ufw allow 80/tcp`
  - `sufo ufw allow out 22/tcp`
   Nachdem ich alle Regeln eingegeben habe, habe ich die Firewall mit dem Befehl `sudo ufw enable` angeschalten. Danach bin ich mit dem Befehl `exit` raus. Um zu testen, ob ich dann wieder reinkomme, bin ich dann mit `vagrant ssh` wieder in meine VM, mit Erfolg!

  ### Reverse-Proxy Einrichtung
  Der Apache Webserver kann auch als Reverse Proxy einesetzt werden. Für das muss ich folgende Module in Apache2 installieren  
    - `sudo a2enmod proxy`  
    - `sudo a2enmod proxy_html`  
    - `sudo a2enmod proxy_http`  
  und die conf Datei von Apache2 musste ich mit folgendem ergänzen:
   -  `ServerName localhost`
  Danach habe ich den Apache-Webserver neu gestartet.
  **Konfiguration**
  Hier habe ich im File `001-reversedproxy` noch die Weiterleitungen eingetragen.
  ### Benutzer- und Rechtvergabe
  **Benutzer**
  Standardmässig hat Linux bereits den "root" Benutzer. Es gibt auch ein paar andere Benutzer die schon beim Start des Betriebssystemes drauf sind, aber die sind für dieses Modul nicht relevant.
  alle Benutzer kann man unter `/etc/passwd` auffinden.
  **Rechtevergabe**
  Grundsätzlich ist es so, dass der Root Benutzer alle Rechte hat. Es gibt aber Befehle die das Recht für eine Datei beispielsweise ändert.
  Hier eine Liste mit den Befehlen die ich mir merken kann:
  - `chmod` setzt das Dateirecht
  - `chown` ändert den Dateibesitzer
  
  dann gibt es noch die read,write,execute Berechtigungen
  - `-r` damit darf ein Benutzer eine Datei lesen.
  - `-w` mit dem erlaubt es einem Benutzer eine Datei zu schreiben
  - `-x` gibt dem Benutzer das Recht, eine Datei auszuführen
  Natürlich gibt es noch mehr Berechtigungseinstellungen die man präzisieren kann, aber die sind mir gerade noch präsent.
  
  ## Persönlicher Lernzuwachs/Reflexion
  Mit diesem Auftrag habe ich mir viel Wissen aneignen können. Ich kannte vorher weder Vagrant, noch Markdown. Bei beidem konnte ich mir ein sehr gutes Grundwissen aneignen. Im Nachhinein, gefällt mir Markdown sehr zum dokumentieren. Ich würde nun auch in Zukunft gerne mit Markdown und Vagrant arbeiten, es macht die Arbeit einfacher und schneller.


  # LB3
  
  ## K1 und K2
  Da K1 und K2 Punkte sind, welche wir in LB2 schon haben mussten, ist es eine Grundvoraussetzung, dass ich diesen Punkte bei LB3 bereits habe. Weiter oben in der Dokumentation zu LB2 kann man meine Nachweise zu K1 und K2 einsehen. Es war Voraussetzung, dass man Virtualbox, Visualstudio-code, Den Git-Client, Vagrant und einen SSH-Key hat.

  ## K2

 ### Persönlicher Wissenstand im Bezug auf die wichtigsten Themen


  **Containerisierung**  
  Containerisierung erlaubt es auf eine Maschine mehrere unabhängige Kontexte am laufen zu haben, die Applikationen laufen lassen. 
  **Vorteile von Containerisierung**  
  Auf einer Hardware können unterschiedliche Applikationen unabhängig voneinander laufen.
  das Betriebssystem kann in jedem Kontext anderst konfiguriert werden.
  Container können problemlos auf jedem Maschinentyp installiert werden.
  **Nachteile von Containerisierung**   
  Für die Containerisierung müssen andere Konzepte und Arbeitsweisen erlernt werden.
  es braucht ein gewisses Know-How.
  **Docker**   
  Docker ist eine Software, welche die Container-Virtualisierung von Anwendungen ermöglicht. Diese werden mittels Docker in ein Image gepackt. Die Applikation ist bis auf gewisse Schnittstellen komplett isoliert.Der Docker probiert die Arbeit mit Containern möglichst praktisch und unkompliziert zu machen.
  **Microservices**   
 Microservices sind Dienste, die jeweils eine kleine Aufgabe in einer Software erfüllen. Die Prozesse lassen sich wie Module miteinander verbinden, und aus dem bildet sich dann eine Software. Das positive an Microservices ist, dass sie sich leicht ersetzen lassen. 

 ## K3

 ### Docker implementieren

 Als Docker benutze ich den zur Verfügung gestellten Docker für LB3.
 Als Container habe ich Apache2 installiert. Damit das funktioniert, habe ich den Befehl `docker build -t apache` eingegeben.

Um den Container zu starten musste ich die Befehle `docker run --rm -d -p 8080:80 -y`
 `/web/var/www/html --name apache apache` eingeben.

![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/index angepasst.PNG "Index angepasst")
Hier ist zu sehen, wie ich den Index im Apache angepasst habe. Der Container ist nun erolfgreich getestet.


 ### Befehle

 - `RUN` Befehl ausführen
 - `ENV` Setzt eine Umgebungsvariabel
 - `CMD` Befehl beim Start ausführen
 - `FROM` Image auswählen welches als        Grundlage verwendet wird
 - `EXPOSE` Port freigeben
 - `VOLUME` Ordner freigeben
 - `docker build` kreiert ein Image von einem Dockerfile
 - `docker checkpoint` Checkpoints können bearbeitet werden
 - `docker commit` neues Image von Veränderungen erstellen
 - `docker container` Container können bearbeitet werden
 - `docker create` Container wird erstellt
 - `docker exec` Befehl ausführen in einem laufendem Container
 - `docker history` zeigt die Versionverläufe von einem Image an
  
Es gibt noch viel mehr Befehle, die sehr nützlich sein können, aber ich habe nicht alle gebraucht, deshalb werde ich nicht alle aufschreiben. 

#### Netzwerkplan
![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/netzwerkplan1.PNG "Netzerkplan")

#### Schichtenmodell
![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/738x415_f5f5f5.jpg "Schichtenmodell")

## K4
**Sicherheitsaspekte implementieren**
Mittels Logging protokolliert Docker alles. Die Logs kann ich dann über den Befehl `docker logs` abrufen.
mit dem Befehl `docker logs streamtest`,sind folgende Logs angezeigt worden:
![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/logtest.PNG "Logtest")

**Microservices zur Überwachung**

Zur Überwachung von meinem Docker und Container habe ich mir cAdvisor von Google ausgesucht.
`docker run -d --name cadvisor -v /:/rootfs:ro -v /var/run:/var/run:rw -v /sys:/sys:ro -v /var/lib/docker/:/var/lib/docker:ro -p 8080:8080 google/cadvisor:latest`
Mit diesem Befehl habe ich den cAdvisor zum laufen gebracht. Ich konnte mit `localhost:8080` im Browser drauf zugreifen.

**weitere Sicherheitsimplementationen**
Ich habe aus Sicherheitsgründen einen neuen Benutzer "max" erstellt, der nicht so viel Rechte wie der root User hat. Somit gibt es keine Gefahr, dass der Benutzer etwas an den Einstellungen kabutt machen könnte.
![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/useradd.PNG "add user")

Des Weiteren hätte ich noch den Speicher begrenzen können, damit ich mich vor DoS-Angriffen schützen kann. Da dies von der Zeit aber nicht drin lag, habe ich dies nicht gemacht.

Zur weiteren Sicherheit habe ich noch SELINUX installiert, konfiguriert und enabled. 
![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/Bilder/SElinux.PNG "SElinux")
Mit Selinux werden erstmal alle eingehende oder ausgehende Verbindungen abgelehnt, die nicht benötigt werden. Dadurch sind nur Ports offen, die auch benötigt werden.

### Reflexion

Für die LB3 hatte ich für meinen Geschmack viel zu wenig Zeit. Auch wenn ich mehrmals ausserhalb der Schulzeiten, am Wochenende dran gearbeitet habe, konnte ich nicht alles installieren und so konfigurieren wie ich es mir vorgestellt habe. Es war für mich ein wenig zu hohes Niveau, um es mir die meiste Zeit selber beibringen zu können. 
Deshalb habe ich soviel probiert wie es geht, und dann hat es halt manchesmal nicht so geklappt, wie ich es mir erhofft habe, aber das ist okay.
Ich habe nichts desto trotz ziemlich viel von der LB mitgenommen und gelernt.