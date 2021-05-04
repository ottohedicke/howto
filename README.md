![OTTO.market Logo](https://github.com/Uncrout/TestFuerOttoDL_Leitfaden/blob/main/img/otto_market_logo_white_bg.PNG)

*Read this document in other languages: [deutsch](https://github.com/Uncrout/TestFuerOttoDL_Leitfaden/blob/main/README.md), [english](https://github.com/Uncrout/TestFuerOttoDL_Leitfaden/blob/main/EN/README_EN.md)*

# Leitfaden für eine Dienstleister-Anbindung

Präambel
- Was kann in diesem Repo gefunden werden?
- Hinweis auf Testfälle und Postman Collection

### Kontakt
Partner Connector Management: partnerintegration@otto.market

## Inhaltsverzeichnis
### 1. Wissenswertes vorab
* Einführung
* Prozesschart
* Kontaktpersonen
* Systemlandschaften
### 2. Anbindung
* Must-Haves
* Testphase
* Pilothase
* ~~Projektabschluss~~
### 3. Betrieb
* Marketing und Sales
* ~~Development~~

# 1. Wissenswertes vorab
## Einführung

Nachdem Sie das Partner Connector Management (PCM) kennengelernt haben, 
können wir nun gemeinsam mit der technischen Anbindung beginnen. In diesem 
Dokument finden Sie sämtliche Informationen zum Prozess der Anbindung. Das 
PCM unterstützt Sie bei der Entwicklung einer stabilen und skalierfähigen Schnittstelle,
damit bereits der erste Partner auf eine verlässliche Dienstleistung zählen kann.
Gemeinsam schaffen wir die Basis für eine nachhaltige Potenzialausschöpfung auf beiden Seiten.

Dieses Dokument ist die zentrale Informationsquelle für Ihre Anbindung an den OTTO Market.
Um letztlich eine valide Schnittstelle zu erstellen, ist es essentiell dieses Dokument 
zu lesen und die Informationen stets als Hilfsmittel zu Rate zu ziehen.

Neben einem Überblick über den gesamten Anbindungsprozess und Informationen 
über Ansprechpersonen sowie der Systemlandschaft, beinhaltet das Dokument 
detaillierte Informationen zu den einzelnen Prozessschritten.
Schließlich finden Sie Informationen zu Marketing und den Developmentprozess.

Bevor Sie nun mit dem Durcharbeiten beginnen finden Sie hier noch Erläuterungen 
zum OTTO Sprachgebrauch:

**Partner**: Händler, die auf otto.de verkaufen.

**PCM**: Partner Connector Management

Wir freuen uns auf eine partnerschaftliche Zusammenarbeit und stehen für Rückfragen gerne zur Verfügung.
Sollten Sie Anregungen oder Feedback zu haben kommen Sie gerne auf uns zu. 

## Prozesschart

![Prozesschart Anbindung OTTO.market](https://github.com/Uncrout/TestFuerOttoDL_Leitfaden/blob/main/img/Prozesschart.PNG)

Dieses Prozesschart gibt Ihnen einen allgemeinen Überblick über den obligatorischen Prozess der Anbindung.
Der definierte Prozess stellt eine reibungslose Anbindung sicher, daher sollte sich genau an diesen gehalten werden.

Zum Start des Projektes geht es darum, dass Verhalten der Schnittstellen 
kennenzulernen und mit der Entwicklung zu starten. Dafür erhalten Sie von uns im 
Rahmen des Kickoff-Pakets Testfälle, die Sie in den von uns zur Verfügung
gestellten Testumgebungen bearbeiten. Die Zugänge zu den Testumgebungen 
haben Sie von uns mit diesem Dokument zusammen erhalten. Während der 
Entwicklung haben sie Zeit ihre Software eigenständig zu entwickeln und diese 
intern zu testen. Nach Abschluss der internen Tests müssen Sie die Testfälle einmal 
durchspielen und Ihre Ergebnisse an uns übermitteln.

Bei erfolgreicher Abnahme dieser suchen wir in der Pilotphase gemeinsam nach 
einem geeigneten Pilotpartner und Sie beginnen mit der Einrichtung und 
Datensendungen des Pilotpartners. Sobald dieser live ist und unsere Abnahme 
erfolgreich war, folgt der Projektabschluss und der Übergang in den Betrieb. 

## Kontaktpersonen

Während und nach der Anbindung steht Ihnen das Partner Connector Management (PCM) zur Verfügung.
Das PCM ist die zentrale Anlaufstelle für alle Dienstleister, die sich an OTTO anbinden möchten.

```
Sie erreichen das Partner Connector Management stets unter: partnerintegration@otto.market
```

Bitte verweisen Sie potenzielle Partner an die offizielle Webseite: [OTTO.market](https://www.otto.market/)
  
## Systemlandschaft

Im Laufe des Anbindungsprozesses werden Sie zunächst in der Testumgebung
arbeiten, bevor sie im Betrieb in die Liveumgebung wechseln. Die Zugänge zu den 
Umgebungen, welche sich hinsichtlich ihres Leistungsumfangs unterscheiden, 
erhalten Sie über das PCM.

```
Bitte beachten Sie, dass die Zugangsdaten der Umgebungen unterschiedlich sind.
Daten der Nonlive- funktionieren nicht in der Live-Umgebung.
```

Bitte fügen Sie für alle Datensendungen zu OTTO im Request-Header der API Requests den folgenden Key und das folgende Value ein: 

```
Key: user-agent
Value: <Ihre Dienstleisterkennung>
```

Dies hilft uns, Ihre Datensendungen zu bündeln und Sie bei auftretenden Problemen besser unterstützen zu können.

Um Missverständnissen vorzubeugen, möchten wir Sie bitten sich mit den einzelnen 
Umgebungen vertraut zu machen. Für detailliertere Informationen, nutzen Sie bitte die weiterführenden Links zu unseren API-Dokumentationen.

**Die Sandbox**

Für die technische Integration stellen wir Ihnen eine Sandbox zur Verfügung. Mit dieser können die Endpoints der OTTO Market API getestet werden. Ein UI gibt es für die Sandbox nicht. Außerdem haben Sie in der Sandbox Zugang zu einem Ordergenerator um Testaufträge zu erzeugen. Weiterführende Informationen zur Sandbox finden sie in unserer [API Dokumentation](https://public-docs.nonlive.api.otto.market/02_Sandbox/index.html).

Die Sandbox befindet sich im Aufbau und wird vom Leistungsumfang stetig weiterentwickelt.
Aufgrund der Tatsache, dass in der Sandbox aktuell noch nicht alle Endpoints der Live-Umgebung getestet werden können,
steht Ihnen zusätzlich unsere Nonlive-Umgebung für Testzwecke zur Verfügung.

**Die Nonlive Umgebung**

Die Schnittstellen: Products und Quantities können in der Nonlive-Umgebung getestet werden.
Analog zur Sandbox steht auch in dieser Umgebung ausschließlich die API zur Verfügung.
Sandbox und Nonlive bilden gemeinsam unsere Testumgebung ab.

**Die Live Umgebung**

Die Live Umgebung wird zum ersten Mal in der Pilotphase genutzt. Sie als 
Dienstleister bekommen keinen eigenen Zugriff und müssen auf die Zugänge eines 
ersten aktiven Partners zurückgreifen. Mit diesem sogenannten Pilotpartner testen Sie erstmalig in der Liveumgebung.
Den Zugang bekommen die Partner innerhalb ihres Onboardings.

```
Die Ihnen zur Verfügung gestellten Zugangsdaten funktionieren NUR in der jeweiligen Umgebung.
Z.B. funktionieren die Userdaten der Sandbox nicht in der Nonlive- oder Live-Umgebung und vice versa.
```

# Anbindung

In diesem Abschnitt finden Sie einen detaillieren Überblick über die Prozessschritte der Anbindung.
Zunächst zeigen wir Ihnen im Kapitel **Must-Haves** einen Überblick über die Kategorisierung der Endpoints bezogen auf ihre 
Notwendigkeit. Im Anschluss wird genauer auf die Test- und Pilotphase eingegangen.
Im Kapital Projektabschluss wird der Übergang in den Betrieb erläutert.

## Must-Haves

Nachfolgend finden Sie eine Übersicht mit all unseren **Endpoints** und einer 
Kategorisierung in "Must´s", "Should´s" und "Could´s". Darüber hinaus finden Sie 
weitere wichtige Besonderheiten zu einzelnen Endpoints. Bitte beachten Sie, dass die Kategorisierung differenziert entsprechend Ihres Leistungsumfangs betrachtet werden muss. Wenn Sie z.B. nur den Auftragsabwicklungsprozess mit Ihrem Service abdecken wollen, so gelten auch nur die Must´s aus *Oders*, *Shipments* und *Returns*. Gerne stehen wir beratend sowie für weitere Fragen zu den einzelnzen Must´s, Should´s und Could´s zur Verfügung.

**Must´s**: Endpoints, die verpflichtend zur Nutzung der jeweiligen Schnittstelle gepflegt werden müssen 
**Should´s**: Endpoints, die empfehlenswert, aber nicht verpflichtend sind
**Could´s**: Optionale Endpoints

### Products
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v1|/products|/|GET|Could|
|||/{sku}|GET|Could|
|||/|POST|Must|
|||/brands|GET|Must|
|||/categories|GET|Must|
|||/marketplace-status|GET|Must|
|||{sku}/marketplace-status|GET|Should|
|||/active-status|GET|Should|
|||{sku}/active-status|GET|Could|
|||/active-status|POST|Must|

```
Um stets die aktuellen Marken und Kategorien zu haben, ist es wichtig mehrmals die Woche die Listen 
/v1/ products/ brands (GET) und /v1/ products/ categories (GET) herunter zu laden.
```

```
Um verschiedene Varianten zu bilden ist es wichtig, dass über /v1/products/ (POST) alle
zusammenhängenden SKUs mit dem gleichen productName geschickt werden.
Dieser steuert die Zusammenführung der SKUs zu einem Produkt.
```

```
Bitte beachten Sie, dass die Verarbeitung der Produktdaten (POST/v1/products) asynchron abläuft
und Sie in der Response weiterführende Links (self, succeeded, failed) zum Abrufen der Fehler erhalten. 
```

### Quantities
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v2|/quantities|/|POST|Must|


### Orders
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v3|/|/|GET|Must|
|||/{salesOrderId}|GET|Could|
|||/{salesOrderId}/cancellation|POST|Must|

### Shipments
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v1|/shipments|/|GET|Could|
|||/|POST|Must|
|||/{shipmentId}|POST|Should|
|||/carries/{carrier}/trackingnumbers/{trackingnumber}|GET|Must|
|||/carries/{carrier}/trackingnumbers/{trackingnumber}/positionitems|GET|Should|

```
Bei /v1/shipments/ (POST) muss immer ein Retourentrackingkey übermittelt werden,
wenn es sich um einen Paketversand handelt. Bei Speditionsversand ist dieser optional.
Die Validierung basiert auf dem deliveryType bei der Produktanlage.
```

### Returns
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v2|/returns|/|GET|Should|
|||/acceptance|POST|Must|
|||/rejection|POST|Must|

### Receipts
|**Version**|**Interface**|**Endpoint**|**Request**|**Must / Should / Could**|
|-|-|-|-|-|
|/v2|/receipts|/|GET|Should|
|||/{receiptNumber}|GET|Could|
|||/{receiptNumber}.pdf|GET|Could|

## Testphase

Sobald Sie mit der Implementierung der Schnittstellen fertig sind, müssen 
anschließend die von uns definierten **Testfälle** abgeschlossen werden.

Dies dient dazu zum einen erste Einblicke Ihre Systeme zu erhalten und zum 
anderen die Bilder aus Ihrem System abzuspeichern, um unseren Partnern 
zukünftig besseren Support anbieten zu können.

Diese finden Sie in dem zugehörigen Dokument, welches Sie von uns mit dieser 
Handreichung erhalten haben. Sobald alle Testfälle von uns abgenommen wurden, 
können Sie mit der Pilotphase weiter machen.

## Pilotphase

Nach dem erfolgreichen Abschluss der Testphase wird mit einem Pilotpartner 
erstmals in der Live-Umgebung agiert. Sollte kein Pilotpartner verfügbar sein, 
kommen Sie bitte auf das PCM zu, welches Sie bei der Suche unterstützen wird.

Nach dem ein Pilotpartner feststeht muss dieser beim PCM angegeben werden. In 
der Pilotphase kümmert sich das PCM ausschließlich um die Belange des 
Dienstleisters. Die Betreuung des Partners liegt nicht in der Kompetenz des PCM.

Alle Partner, die mit dem Einspielen von Produkten beginnen, haben zunächst eine 
sogenannte Display Restriction. Konkret bedeutet dies, dass die Produkte nicht 
unmittelbar im Shop öffentlich sichtbar sind. Erst nach der Aufhebung der Display 
Restriction können Kund\*innen die Produkte einsehen. Bevor OTTO die Produkte 
auf otto.de auch für Endkund\*innen sichtbar macht, müssen folgende 
Prozessschritte durchlaufen sein, über die sich der Partner im Partner Helpdesk 
informieren kann: 

1. Das Vorgehen für eine Testbestellung
2. Bestätigung über das Verständnis des Bestellprozesses (Shipment 
Request) per Ticket an OTTO senden

Dieser Mechanismus ermöglicht also das Testen unter realen Bedingungen. Wenn 
die Produktdaten in Ordnung sind und die Voraussetzungen erfüllt sind, kann der 
Partner final live gehen. Seitens des PCM wird zwei Wochen nach dem Livegang 
geprüft, ob es Auffälligkeiten oder Probleme entlang der Schnittstelle gibt.

In der Pilotintegration wird auf folgende Kriterien besonders geachtet:

* Ist die Variantenbildung der Produkte korrekt?
* Import-Fehlermeldungen – sind diese ersichtlich und verstanden?
* Können sich die Aufträge korrekt gezogen werden?
* Funktionieren die Versandmeldungen – Ist auch der returnTrackingkey korrekt enthalten?
* Gibt es Auffällige HTTP-Fehler in den API-Requests? Fehlerquote pro Schnittstelle
* Ist der User-Agent eingepflegt?

In jedem Fall erfolgen dann ein Abschluss und die Abnahme der Pilotintegration. 
Sollten keine Anpassungen mehr nötig sein können Sie nun mit dem Aufschalten 
weiterer Partner beginnen.

# Betrieb
## Marketing und Sales

Nach Abschluss der Anbindung und Abnahme der Pilotphase haben Sie die 
Möglichkeit, ihren Service über unsere Homepage zu vermarkten. Wir benötigen 
hierfür lediglich ein Logo und eine Landing Page von Ihnen. Für etwaige
Marketingaktionen Ihrerseits bitten wir um eine stetige Abstimmung mit uns.
