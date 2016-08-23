### Skin für IP-Symcon 4.0 WebFront im Material Design Stil

**Inhaltsverzeichnis**

1. [Funktionsumfang](#1-funktionsumfang) 
2. [Systemanforderungen](#2-systemanforderungen)
3. [Installation](#3-installation)
4. [Anleitung](#4-anleitung)
5. [Changelog](#5-changelog) 
6. [Sonstiges](#6-sonstiges) 

[Beispiel Hell](docs/example1.png?raw=true "Beispiel 1")
[Beispiel Dunkel](docs/example_dark.png?raw=true "Beispiel dunkel")
[Beispiel Edititieren](docs/edit_example1.png?raw=true "Beispiel Editieren")

### 1. Funktionsumfang
Basierend auf den originalen IP Symcon Skin stellt dieser Material Design Skin eine
Alternative dar, die sich an das Material Design von Google anlehnt. 

Im Prinzip werden nur Teile der original IP-Symcon CSS Datei mit neuen Attributen
versehen. Handhabung, Design und Bedienung entsprechen dem normalen WebFront.

Als Icons werden entweder die originalen IP Symcon Icons, oder Kopien derer, bei denen lediglich die 
Zeichenfarbe "weiß" (stroke="#ffffff") gegen "schwarz" (stroke="#000000") getauscht wurde, verwendet. 

Über das optionale Modul [IPS MaterialDesignSkinOptions](https://github.com/Uhula/IPSMaterialDesignSkinOptions) lassen sich für den 
Skin verschiedene Farbkombinationen (Themen) wählen, sowohl helle als auch dunkle Themen stehen zur Verfügung.


### 2. Systemanforderungen
* IP-Symcon ab Version 4.x


### 3. Installation
Im Objektbaum der IP Symcon Managment Console über die Kern-Instanz "Skins" folgende URL hinzufügen:
`git://github.com/Uhula/IPSMaterialDesignSkin.git`
Die Skin wird hinzugefügt und kann anschließend verwendet werden.

Die Gesamtgröße beträgt, bedingt durch die SVG Icons, rund 2.0 MB.

Verwendung auf eigene Gefahr, der Autor übernimmt weder Gewähr noch Haftung.

### 4. Anleitung
#### Welche Anpassungen sind in der CSS vorhanden ?
Um den Material Design Style zu erhalten, werden in der CSS Datei folgenden Einstellungen
zum originalen Skin vorgenommen: 
* alle Border werden durch "transparent" unsichtbar geschaltet
* alle Hintergründe werden flach, also ohne Verlauf dargestellt
* Kein Zwang, aber für das Layout wird empfohlen:


    SplitPane 
    +-- TabPane (Menü, fixe Höhe: 34px) "Kopfzeile"
    |   +-- InfoWidgets 1  
    |   +-- InfoWidgets 2 usw  
    +-- SplitPane
        +-- TabPane (Menü, variable Höhe) "Navigation"
        |   +-- TabPane (Menü) "Unternavigation 1"
        |   |   +-- SplitPane "Datenanzeige", horz/vert geteilt
        |   |   ...
        |   +-- SplitPane "Datenanzeige", horz/vert geteilt
        |   |   ...
        |   +-- Kategorie "Datenanzeige", Vollbild
        |   |   ...
        +-- TabPane (Menü, fixe Höhe: 34 px) "Statuszeile"
            +-- InfoWidgets 1  
            +-- InfoWidgets 2 usw  
* Kopfzeile
  * Die erste Menüzeile wird als Kopfzeile angesehen und in dunklerer
    Themenfarbe dargestellt als die folgenden Menüs. Es empfiehlt sich hier nur
    Schaltflächen und InfoWidgets unter zu bringen    
  * erhält einen Schatten nach unten  
* Navigation
  * wird mit der Themenfarbe hinterlegt
  * die aktive Navigation wird in einer Akzentfarbe markiert
  * erhält einen Schatten nach unten  
* Datenanzeiger, Container
  * werden mit einem Schatten dargestellt
  * Wertdarstellungen sind fett und leicht größer
  * Schaltflächen werden als Text in der Akzentfarbe angezeigt
  * Slider werden als Strich dargestellt und erhalten einen "Anfasser"
* Statuszeile
  * Die letzte Menüzeile (SplitPane:bottom) wird als Statuszeile angesehen und in dunklerer
    Themenfarbe wie die Kopfzeile dargestellt. Sie wird an der fixen Höhe von 34px erkannt!   
  * erhält einen Schatten nach oben
* Popups füllen zentriert 10% des Fensters, Ausnahme: Charts
* ...

#### Welche Anpasssungen sollten in IP Symcon vorgenommen werden ?
* um die Darstellung der Werte und Schaltflächen sinnvoll nutzen zu können,
sollten Farbzuverweisungen in den Variablen-Stilen nur dort vorgenommen
werden, wo sie notwendig sind. Z.B. bei Alarm- und Fehlerzuständen.
* ...

#### Wie kann man die Farbeinstellungen in der CSS anpassen ?
Kann man zwar manuell machen, muss man aber nicht, da es hierfür ein weiteres Modul
gibt `git://github.com/Uhula/IPSMaterialDesignSkinOptions.git`


### 5. Changelog
Siehe [ChangeLog](./CHANGELOG.MD).


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
wenn jede Instance zusätzlich eine Property "CSS classes" hätte, die man frei eingeben kann und die
dann mit in <div class="... myclasses ..."> gerendert wird  

