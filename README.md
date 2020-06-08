# M300
This is a repository that is used to document my process and which is used as a cloud.
### Dokumentation LB2 von Maxine Drapela


# Inhaltsverzeichnis

- [K1](#k1)
  - [Umgebung bereit machen](#umgebung-bereit-machen)
- [K2](#k2)
    - [Umgebung eingerichtet](#umgebung-eingerichtet)

- [K3](#k3)
  - [Vagrant-Befehle](#vagrant-befehle)
  - [Umgebungsvariabel](#umgebungsvariabel)
  - [Netzwerkplan](#netzwerkplan)
  - [Sicherheitsaspekte](#sicherheitsaspekte)
  - [Testfälle](#testflle)
- [K4](#k4)
  - [Firewall mit den Rules](#firewall-mit-den-rules)
  - [Reverse-Proxy](#reverse-proxy)
  - [Benutzer- und Rechtvergabe](#benutzer--und-rechtvergabe)
  - [SSH-Tunnel](#ssh-tunnel)
  - [Sicherheitsmassnahmen](#sicherheitsmassnahmen)
- [K5](#k5)
  - [Persönliche Lernentwicklung](#persnliche-lernentwicklung)
    - [Vorwissen und Wissenszuwachs](#vorwissen-und-wissenszuwachs)
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
![See the source image](https://images.g2crowd.com/uploads/product/image/social_landscape/social_landscape_1489710078/vagrant.png)
Mit Vagrant können wir virtuelle Maschinen viel einfacher und automatisierter erstellen.
**Einrichtug Vagrant**
Die Einrichtung mit Vagrant war recht simpel. Ich konnte alles so installieren, wie ich es mir vorgestellt habe. Anfangs hatte ich ein wenig Mühe, mich dran zu gewhöhnen, dass jetzt alles so einfach und schnell installiert werden kann.
#### Sicherheit
**reverse Proxy**
Der Reverse Proxy funktioniert ähnlich wie der Forward Proxy. Ein Außenstehender denkt er kommuniziere direkt mit mir, er wird jedoch zum Reverse Proxy weitergeleitet der meine Identität geheimhält und ihm eine andere zurückgibt. 
**Einrichtung Reverse Proxy**

## K3 Vagrant
 ### vagrant-befehle
 ### umgebungsvariabel
 ### netzwerkplan
 ### sicherheitsaspekte
 ### testflle

