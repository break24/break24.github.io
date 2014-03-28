#Require, Backbone, Bootstrap
##Template TODOs 
- Ase komplett konsolideiren
- Typographie hinzufügen

##General Todos
- Ripple Debugger
- check _.bindAll(this, 'render', 'renderOne');
- I18N (f.e. moments)
- Events, listenTo
 
## Rest Backend
- verschiendene Authentication
- Link für Regeln 
- Heroku
 
## Testing, Build, Deploy
- Zusammenfassen von BootBone items .?. und build mit j.js
- Modularisieren
- uglyfy2
- Build mit grunt job
- Testing
- jshint
 
## F&E
- Backbone history start 
- pushState: true, root: "/"

## Git 
###Mein Git Repository
https://github.com/break24

###CSS
http://lesscss.org/ oder http://sass-lang.com/

###Frameworks
- http://getbootstrap.com
- Alternativen: http://maker.github.io/ratchet/ http://purecss.io/ http://metroui.org.ua/

###Struktur 
- http://requirejs.org/ 
- http://backbonejs.org/ oder http://angularjs.org/
 
###mobile Apps
- http://phonegap.com/
- http://www.appliness.com/getting-started-with-html-mobile-application-development-using-jquery-mobile-requirejs-and-backbonejs/#codesyntax_9


###Blogs
- http://coenraets.org/blog/
- http://backstage.soundcloud.com/2012/06/building-the-next-soundcloud/
- http://www.html5rocks.com/de/tutorials/websockets/basics/

#backbone.js

##Backbone.Model und Backbone.Collection 

Collections suffix List

Validieren und Sortieren von Entitäten und Listen : validate & isValid 

comparator-Eigenschaft von Listen
comparator-Eigenschaft eine Funktion zuweisen, die zwei Parameter erwartet. 
Beide Parameter repräsentieren jeweils eine Entität. 
Der Wert -1 bedeutet, dass die erste Entität vor der zweiten einzusortieren ist; 
der Wert 1 beschreibt das Gegenteil. 
Gibt die Funktion hingegen den Wert 0 zurück, bedeutet das, dass beide Entitäten als gleichwertig anzusehen sind.

save- und eine destroy-Funktion

Abhängig vom Rückgabewert der Funktion isNew der Entität entscheidet Backbone.js, ob es eine POST- oder eine PUT-Anfrage

Diese URL setzt man mit Hilfe der url-Eigenschaft an der zugehörigen Liste

id-Eigenschaft

befüllt man eine Liste anfänglich mit Daten vom Webserver. Hierzu dient die Funktion fetch, die man allerdings nicht an einer Entität, sondern an der Liste aufruft.

customers.fetch({ reset: true });

Backbone.sync eine neue Funktion zuzuweisen

Projekt Backbone.localstorage eine Funktion zur Verfügung, die auf den lokalen Speicher des Webbrowsers zugreift. 
Die Integration ist denkbar einfach: Man muss nach dem Laden der Datei backbone.js lediglich die Datei backbone.localstorage.js 
laden, die die Funktion Backbone.sync wie gewünscht ersetzt:


##Backbone.View

Backbone.View zur Verfügung, die zur Definition von Ansichten dient. Eine Ansicht entspricht allerdings eher dem aus MVC bekannten Controller

Kommunikation zwischen der Webseite und dem Domänenmodell

Mindestens tagName ist einzubauen, da die Eigenschaft definiert, als welches HTML-Element die Ansicht gerendert werden soll. 
className und id für CSS-Klasse und -ID 

ist es sinnvoll, die initialize-Funktion zu definieren und in ihr als Reaktion auf eine Änderung des Domänenmodells die render-Funktion aufzurufen. Die Aufgabe dieser Funktion besteht darin, die Darstellung im Webbrowser zu aktualisieren.

render-Funktion selbst nicht das eigentliche Aktualisieren, sondern erzeugt lediglich den erforderlichen HTML-Code, um die Ansicht anzuzeigen. Das weist sie der Eigenschaft el beziehungsweise deren jQuery-gekapselter Variante $el zu, die das konkrete HTML-Element repräsentiert, das mit der Ansicht verknüpft wurde.

Verwendung von HTML-Vorlagen ein, wobei sich im einfachsten Fall wiederum auf die template-Funktion von Underscore.js 

Damit man die render-Funktion an übergeordneter Stelle verkettet aufrufen kann, empfiehlt die Dokumentation von Backbone.js, dass die Funktion this an den Aufrufer zurückgibt

events-Eigenschaft auf Ereignisse innerhalb des Webbrowsers reagieren
 events: {
    'click .save': 'saveCustomer'
  },
  
Beim Erzeugen der konkreten Ansicht 
- Parameter ein bestehendes HTML-Element   
- anzuzeigende Entität beziehungsweise die anzuzeigende Liste übergeben: model beziehungsweise collection

##Backbone.Router

Existenz einer Router-Instanz an sich genügt jedoch noch nicht, damit Backbone.js die Navigation des Webbrowsers verwaltet, zusätzlich start-Funktion des Objekts Backbone.history aufrufen.

Hashbang nutzende Routen oder die in HTML5 neu eingeführte, ausschließlich mit modernen Webbrowsern kompatible History-API verwenden möchte:

!! Da die Navigation mit Hashbang im Internet Explorer die Verwendung eines iframe-Elements voraussetzt, ist es wichtig, die start-Funktion erst nach dem vollständigen Laden der Webseite aufzurufen.




