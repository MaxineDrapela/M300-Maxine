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
    - [umgebungsvariabel](#umgebungsvariabel)
    - [netzwerkplan](#netzwerkplan)
    - [Webalizer Installation](#webalizer-installation)
    - [sicherheitsaspekte](#sicherheitsaspekte)
    - [testfälle](#testfälle)
      - [Test 1 - Apache Webserver](#test-1---apache-webserver)
  - [K4 Sicherheitsaspekte implementieren](#k4-sicherheitsaspekte-implementieren)
    - [Firewall mit den Rules](#firewall-mit-den-rules)
    - [Reverse-Proxy Einrichtung](#reverse-proxy-einrichtung)
    - [Benutzer- und Rechtvergabe](#benutzer--und-rechtvergabe)
    - [SSH-Tunnel](#ssh-tunnel)
    - [Sicherheitsmassnahmen](#sicherheitsmassnahmen)
  
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
 Vagrant 
 ### umgebungsvariabel

 ### netzwerkplan
 ![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/netzwerkplan.PNG "Netzwerkplan")
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
 ![alt text](https://github.com/MaxineDrapela/M300-Maxine/blob/master/testapache.PNG "Default Apache Webpage")
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
  
  ### SSH-Tunnel
  ### Sicherheitsmassnahmen