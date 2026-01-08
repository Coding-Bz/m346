## A) Kostenrechnung IaaS – Rehosting (60 %)

## Vorgehensweise bei Microsoft Azure

Vorgehensweise bei Microsoft Azure
Zu Beginn meiner Recherche habe ich analysiert, welche Ressourcen für die Anwendung notwendig sind, um Unter- oder Überkapazitäten zu vermeiden. Hierzu habe ich den Kundensupport von Microsoft Azure kontaktiert, meine Anforderungen erläutert und um einen Vergleich verschiedener Optionen gebeten.

Antwort des Azure-Supports (zusammengefasst): Für die Web-Applikation wird der Azure App Service (Linux) im Basic B1 Plan (1 vCPU, 1,75 GB RAM) für ca. 30 Nutzer empfohlen. Die geschätzten Kosten in der Region „Germany West Central“ liegen bei etwa 45–55 USD pro Monat. Dieser Plan umfasst die verwaltete Runtime, Sicherheits-Patches sowie Monitoring.
Für die Datenbank wird ein Azure Database for PostgreSQL Flexible Server (1 vCore, 4 GB RAM, 100 GB Speicher) empfohlen. Die monatlichen Kosten belaufen sich auf ca. 55–70 USD. Hierbei sind automatisierte Backups (7 Tage, 4 Wochen, 3 Monate) bereits ohne manuellen Aufwand inkludiert.
Gesamtkosten Azure: ca. 100–125 USD pro Monat.
Einschätzung: Meiner Meinung nach ist dies eine sehr gute Option, da die Backups inklusive sind und ohne Skripte oder manuelle Eingriffe verwaltet werden. Langfristig ist diese Lösung wirtschaftlicher, da wir Arbeitsstunden sparen, die sonst für die Serverwartung angefallen wären. Alle Anforderungen an den App Service und die Datenbank werden abgedeckt. Beim Support habe ich mich für den Basic Support entschieden, da dieser für unsere Zwecke ausreicht und zusätzliche Gebühren vermeidet.

## Abweichungen zur On-Premise-Infrastruktur

Ich habe bei DB diesmal ProstgreSQL gewählt, weil ich nicht weiss, was momentan verwendet wird. Und MySql und PostgreSQL sind beide beliebte Optionen. Auserdem habe ich beim Web-Server nur 1,75GB RAM, da die andere Optioen viel leistungstärker war (viel mehr als wir benötigen) und auserdem auch viel teurer war.

<img width="2518" height="890" alt="image" src="https://github.com/user-attachments/assets/1ca4b22d-dbab-47c6-92de-105d5c9446b8" />

						
## Vorgehensweise bei AWS
Bei AWS gab es eine grössere Auswahl an Optionen, weshalb ich zunächst verschiedene Instanztypen verglichen habe.

   <img width="945" height="351" alt="image" src="https://github.com/user-attachments/assets/08ad562e-8005-4cd8-8c5c-f83e2aa41b92" />
      
  <img width="945" height="518" alt="image" src="https://github.com/user-attachments/assets/eee15dad-49a9-4391-8ae2-b1783e0c80d2" />

Server-Auswahl: Ich habe die Optionen t3a.small, t4g.small und t3.small geprüft. Letztlich habe ich mich für die t4g.small entschieden. Sie ist preislich am attraktivsten und bietet für unsere Anforderungen eine völlig ausreichende Performance.

<img width="945" height="371" alt="image" src="https://github.com/user-attachments/assets/e71b6149-85dc-4cef-9217-1fb42ed21616" />

Speicher (Storage): Hier habe ich die Konfiguration so gewählt, dass sie das bestmögliche Preis-Leistungs-Verhältnis bietet. Wo möglich, habe ich auch die kostenlosen Angebote berücksichtigt.

<img width="945" height="518" alt="image" src="https://github.com/user-attachments/assets/2ef3c2b3-899d-4170-82ba-03028fc33ee6" />

Datenbank (DB): Auch bei der Datenbank war mein Ziel, die günstigste Option zu wählen, die dennoch die geforderte Performance liefert und alle technischen Voraussetzungen erfüllt.

<img width="945" height="437" alt="image" src="https://github.com/user-attachments/assets/7d8ddb56-5149-4293-a760-ef6b2802b813" />	
						
<img width="3091" height="1073" alt="image" src="https://github.com/user-attachments/assets/b17a15d2-b9ca-4c8e-b9af-ff62f5893c81" />

## Abweichungen zu der On Premise Infrastruktur:

Die einzige wirkliche Abweichung ist, dass ich bei vCPUs 2 ausgewählt habe, da es preislich keinen Unterschied zu 1 vCPUs gemacht hat. Auserdem habe ich mich für MySql entschieden (DB), weil nicht angegeben wurde.

## B) Kostenrechnung PAAS - Replattforming (20%)

 <img width="945" height="40" alt="image" src="https://github.com/user-attachments/assets/2c8ced11-e70d-41f0-8509-9b05d8c46ef8" />

 <img width="945" height="31" alt="image" src="https://github.com/user-attachments/assets/a8ca362a-60e7-432e-ad50-653e71569eed" />

 Monatluch insgesamt: 250$ = 200CHF

## Abweichungen zur On-Premise-Infrastruktur
Im Gegensatz zu den vorherigen hier eine viel grössere Abweichung. Das erste Standard-2x fürs Webserver passt perfekt ist auch, was die Kosten angeht in Ordnung, aber bei der DB musste ich Standard-2 wählen da die schwächere Version nur 64 GB Speicher hatte. Also hier waren die Optionen mit Abstand schlechter, meiner Meinung nach, deswegen war beim Entscheiden meine Vorgehensweise: Zu sehen, was meine Voraussetzungen erfüllt.

##  C) Kostenrechnung SAAS - Repurchasing (10%)

<img width="2560" height="1486" alt="image" src="https://github.com/user-attachments/assets/515ba10c-8e17-4de7-ac42-ad31a359793d" />

Hier hätte ich "Enterprise" ausgewählt, da wir ein Unternehmen sind auch wenn es nur ein Kleinunternehmen ist. Auserdem haben wir verschiedene Vorteile, wie Spezifische Funktionen. Und meiner Meinung nach ist 40 Euro ein ziemlich angmessenes Preis.

<img width="945" height="588" alt="image" src="https://github.com/user-attachments/assets/24de183e-b7c8-4592-9140-b49394208c89" />
Hier würde ich für "Pro Suite" gehen, weil es in Verglcih zu den anderen viel mehr Vorteile hat. Aber wegen dem hohen Preis und weil man hier pro Benutzer ein Lizenz zahlen muss, würde es am meisten Sinn machen zwei Personen zu wählen die sich damit beschäftigen.


## D) Interpretation der Resultate (10%)

Der Grund, wieso die verschiedenen Unternehmen unterschiedliche Preise haben, ist erstens die Nachfrage. Bekannte Unternehmen stehen oft für bestimmte Merkmale (z. B. Apple für Sicherheit) und können somit höhere Preise verlangen. Es kann auch sein, dass einzelne Unternehmen verschiedene Kosten haben, weil sie mit Drittanbietern (3rd Party) zusammenarbeiten. In unserem Fall ist Azure am teuersten, aber was den Kundensupport angeht, sind sie mit Abstand am besten, weswegen man die hohen Preise begründen kann. Ausserdem sind Security-Tools, IP-Adressen, Support-Verträge und spezielle DB-Features oftmals nicht im Preis enthalten. Es ist auch wichtig zu erwähnen, dass man z. B. bei Variante C (SaaS) pro Benutzer/Lizenz zahlen muss, was ein grosser Unterschied ist.

Was die Migration angeht, hat man bei SaaS am meisten Aufwand. Da es sich nicht um eine klassische Migration handelt, sondern um eine Prozessumstellung. Bei Heroku ist es am einfachsten, da es keine Server zum Aufsetzen gibt. AWS und Azure sind mittelschwer, aber das Gute ist, weil sie so bekannt sind, gibt es sehr viel Dokumentation, was den ganzen Prozess um einiges einfacher macht.
