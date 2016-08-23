### Skin für IP-Symcon 4.0 WebFront im Material Design Stil

**Inhaltsverzeichnis**

1. [Funktionsumfang](#1-funktionsumfang) 
2. [Systemanforderungen](#2-systemanforderungen)
3. [Installation](#3-installation)
4. [Anleitung](#4-anleitung)
5. [Changelog](#5-changelog) 
6. [Sonstiges](#6-sonstiges) 


### 1. Funktionsumfang
Basierend auf den originalen IP Symcon Skin stellt dieser Material Design Skin eine
Alternative dar, die sich an das Material Design von Google anlehnt. Es handelt sich 
um einen hellen Skin, der die WebFront-Container als "Cards" betrachtet und eine
"schwarzer Text auf hellem Grund" Ansicht erzeugt.

Im Prinzip werden nur Teile der original IP-Symcon CSS Datei mit neuen Attributen
versehen. Handhabung, Design und Bedienung entsprechen dem normalen WebFront.

Als Icons werden die originalen IP Symcon Icons verwendet, bei denen lediglich die 
Zeichenfarbe "weiß" (#ffffff) gegen "schwarz" (#000000) getauscht wurde. 


### 2. Systemanforderungen
* IP-Symcon ab Version 4.x


### 3. Installation
Im Objektbaum der IP Symcon Managment Console über die Kern-Instanz "Skins" folgende URL hinzufügen:
`git://github.com/Uhula/MaterialDesignLight.git`
Die Skin wird hinzugefügt und kann anschließend verwendet werden.

Die Gesamtgröße beträgt, bedingt durch die SVG Icons, rund 1.7 MB.

Verwendung auf eigene Gefahr, der Autor übernimmt weder Gewähr noch Haftung.

### 4. Anleitung
#### Welche Anpassungen sind in der CSS vorhanden ?
Um den Material Design Style zu erhalten, werden in der CSS Datei folgenden Einstellungen
zum originalen Skin vorgenommen: 
* alle Border werden durch "transparent" unsichtbar geschaltet
* alle Hintergründe werden flach, also ohneVerlauf dargestellt
* Navigation
  * weiße Schrift, weiße Icons
  * die aktive Navigation wird in einer Akzentfarbe markiert
  * erste Ebene wird dunkler hinterlegt als die weiteren Ebenen
* Container
  * die Hintergrundfarben werden vom dunklen zum hellen Style geändert
  * schwarze Schrift, schwarze Icons
  * Wertdarstellungen sind fett und leicht größer
* Schaltflächen werden als Text in der Akzentfarbe angezeigt
* Slider werden als Strich dargestellt und erhalten einen "Anfasser"
* Popups füllen zentriert 10% des Fensters, Ausnahme: Charts
* ...

#### Welche Anpasssungen sollten in IP Symcon vorgenommen werden ?
* um die Darstellung der Werte und Schaltflächen sinnvoll nutzen zu können,
sollten Farbzuverweisungen in den Variablen-Stilen nur dort vorgenommen
werden, wo sie notwendig sind. Z.B. bei Alarm- und Fehlerzuständen.
* ...

#### Wie kann man die Farbeinstellungen in der CSS anpassen ?
Die CSS Datei wurde bewusst so formatiert, dass sie eine einfache Anpassung an eigene 
Farbanpassungen ermöglicht. Als Basis dienen hierbei die 
Material Design Farben für die Darstellung in brown/teal(Akzentfarbe):

.dark-primary-color    { background: #5D4037; }
.default-primary-color { background: #795548; }
.light-primary-color   { background: #D7CCC8; }
.text-primary-color    { color: #FFFFFF; }
.accent-color          { background: #009688; } 
.primary-text-color    { color: #212121; }
.secondary-text-color  { color: #727272; }
.divider-color         { border-color: #B6B6B6; }

Wenn man eigene Farben verwenden möchte, muss man lediglich die Farbangaben
#5D4037, ... durch eigene ersetzen. Hierzu muss mit einem Editor lediglich ein 
"Suchen & Ersetzen" der Hex-Angaben durchgeführt werden. 

Auf der Site https://www.materialpalette.com lassen sich Farbkombinationen
zusammenstellen und die Farb-Hex-Codes dann herunter laden.



### 5. Changelog
Version 0.9 (24.03.2016):
  - Erster Upload


### 6. Sonstiges
#### float / flex
Alle Versuche die WebFront-Container sinnvoll in einem responsible Design darzustellen,
scheiterten an den Anforderungen der Browser. So wird "display:flex" noch nicht von allen
aktuellen Browsers unterstütz, von älteren ohnehin nicht.
Auch "float:left" funktioniert bei Chrome nicht, da hier zwingend eine Width-Angabe erwartet
wird.
Also, die WebFront so verwenden, wie sie gedacht sind: Statische Aufteilung des Browserfensters

#### Wünsche an IP Symcon
Viele Wünsche gibt es nicht, jedoch würde es die CSS Möglichkeiten deutlich erweitern,
wenn 
* entweder die IPS-Instance-ID als Attribut mit in das Element geschrieben 
wird: <div ... ipsID="4711"...>
* oder jede Instance zusäzlich eine class-Angabe hätte, die man frei eingeben kann und die
dann mit in <div class="... myclasses ..."> gerendert wird  

