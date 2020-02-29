---
date: "2020-01-11"
title: Dell XPS 13 bios upgrade onder Ubuntu (zonder USB-disk)
---

Hoewel de bios-upgrade van Dell-machines nog steeds wordt gedomineerd door Windows, is het zeker mogelijk de upgrade te doen zonder Windows.

## De officiële Dell methode

Dell heeft hiervoor [instructies](https://www.dell.com/support/article/nl/nl/nlbsdt1/sln171755/het-dell-bios-updaten-in-een-linux-of-ubuntu-omgeving?lang=nl#updatebios2015) beschikbaar. Heel kort gezegd:

* maak een dos USB-disk;
* zet de fimrware daarop;
* herstart en druk op F12;
* Voer de bios upgrade uit.

Werkt, maar vereist dus een USB-disk.

## De alternatieve fwupd methode

Een alternatief, in het geval van deze machine (en menig andere) is controleren of deze ondersteuning heeft voor LVFS. Als dat zo is, dan is updaten met fwupd een optie. Een goede uitleg hiervoor is terug te lezen in "[How to Update Firmware on Ubuntu 18.04](https://itsfoss.com/update-firmware-ubuntu/)".

## De zelf op je machine downloaden methode

Maar er is nog een derde optie, die ik ooit eens per toeval tegenkwam (lees: na kloten met bovenstaande optie en de ingebakken upgrader in Ubuntu). De BIOS-updater kan namelijk op je lokale systeem een specifieke map uitlezen bij het zoeken naar firmware, zoals ook gesproken in dit Stack-antwoord: /boot/efi/

In het kort:

* Download je firmware, de .exe van de site van Dell;
* Verplaats het bestand naar /boot/efi (sudo vereist);
* Herstart je machine, druk op F12;
* Kies je firmware in de updater zodra je de kans hebt te bladeren naar het bestand;
* Upgraden...
