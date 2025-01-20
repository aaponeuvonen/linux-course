# Linuxin asennus virtuaalikoneeseen

CPU	AMD Ryzen 5 1600 Six-Core Processor, 3400 Mhz, 6 Core
GPU NVIDIA GeForce GTX 1060 6GB
RAM 8GB
Windows 10 pro 64-bit

Asensin VirtualBoxin koneelle, jonka jälkeen asensin debianin tarkalleen näiden ohjeiden mukaan:

https://terokarvinen.com/2021/install-debian-on-virtualbox/?fromSearch=debian%20install

ISO tiedoston lataamisen jälkeen käynnistin Oracle VirtualBox Managerin ja loin uuden virtuaalikoneen nimeltään "DebianTeroKarvinenCom".


Heti alussa, kun asetin virtuaalikoneen nimeä, niin sen jälkeen liitin jo ISO tiedoston samassa valikossa, joka ainakin itsellä korvaa yhden vaiheen tulevissa ohjeissa.


Asetin muistia 4000mb ja sen jälkeen klikkasin "Create virtual hard disk now", jonka jälkeen seuraavassa ikkunassa loin 60GB
kokoisen virtuaalisen kovalevyn.


Tässä kohtaa aiemmin mainittu ISO tiedosto (CDROM) täytyi asettaa virtuaalikoneen muistiasetuksista IDE CDROM kohtaan empty, mutta
itsellä se oli jo valmiina siellä, johtuen heti alussa tehdyistä asetuksista.


Sitten yritin bootata, mutta VirtualBox antoi vikakoodia
"Not in a hypervisor partition (HVP=0) (VERR_NEM_NOT_AVAILABLE). AMD-V is disabled in the BIOS (or by the host OS)" 

Ongelma oli siis oman PC:ni asetuksissa.

Menin oman koneeni Bios asetuksiin ja laitin asetuksen "Enable CPU Virtualization" Enabled tilaan.
( MSI Click Bios 5, AMD Ryzen)

Sain bootattua, ja pääsin Linux työpöydälle. Kokeilin toimiiko selain ja Teron nettisivut, ja kyllähän ne toimi.

Seuraavaksi Debian GNU/Linux installer,  ajoin sen, klikkasin partitions osiossa Erase Disk ja syötin näppäimistön Generic 105-key PC kielen suomeksi ja asetuksen defaultiksi. Sitten nimeni, "käyttäjätunnuksen", 
sekä luotettavan salasanan. 

Ei mitään ongelmia boottaamisessa, ja kaikki meni niinkuin piti. Pystyin kirjautumaan äsken tehdyillä tunnuksillani ja kaikki toimii. 

Nyt on Debian asennettu!

Sitten Terminal auki, ja hankitaan "superuser" oikeudet ja haetaan samalla päivitykset mitä on mahdollista asentaa.
Komennolla $ sudo apt-get update

Sen jälkeen asensin kaikki uusimmat päivitykset.
Komennolla $ sudo apt-get -y dist-upgrade

Ja lopulta asensin palomuurin 
Komennoilla $ sudo apt-get -y install ufw
$ sudo ufw enable

Sitten boottasin ja kaikki on valmista!





