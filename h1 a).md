# Linuxin asennus virtuaalikoneeseen

CPU	AMD Ryzen 5 1600 Six-Core Processor, 3400 Mhz, 6 Core
GPU NVIDIA GeForce GTX 1060 6GB
RAM 8GB
Windows 10 pro 64-bit

Asensin VirtualBoxin koneelle, jonka jälkeen asensin debianin tarkalleen näiden ohjeiden mukaan:
https://terokarvinen.com/2021/install-debian-on-virtualbox/?fromSearch=debian%20install

ISO tiedoston lataamisen jälkeen käynnistin Oracle VirtualBox Managerin ja loin uuden virtuaalikoneen nimeltään "DebianTeroKarvinenCom".
! Heti alussa, kun asetin virtuaalikoneen nimeä, niin sen jälkeen liitin jo ISO tiedoston samassa valikossa, joka ainakin itsellä korvaa yhden vaiheen tulevissa ohjeissa.
Asetin muistia 4000mb ja sen jälkeen klikkasin "Create virtual hard disk now", jonka jälkeen seuraavassa ikkunassa loin 60GB
kokoisen virtuaalisen kovalevyn.

! Tässä kohtaa aiemmin mainittu ISO tiedosto (CDROM) täytyi asettaa virtuaalikoneen muistiasetuksista IDE CDROM kohtaan empty, mutta
itsellä se oli jo valmiina siellä, johtuen heti alussa tehdyistä asetuksista.

Sitten yritin bootata, mutta VirtualBox antoi vikakoodia
"Not in a hypervisor partition (HVP=0) (VERR_NEM_NOT_AVAILABLE). AMD-V is disabled in the BIOS (or by the host OS)" 

Menin oman koneeni Bios asetuksiin ja laitin asetuksen "Allow CPU Virtualization" Enabled tilaan.
( MSI Click Bios 5, AMD Ryzen)
![Bios virtualization setting'](https://github.com/user-attachments/assets/0b5d7848-5845-4cb3-92c4-62738e417015)
