## A) Kostenrechnung IaaS – Rehosting (60 %)

## Vorgehensweise bei Microsoft Azure

Vorgehensweise bei Microsoft Azure
Zu Beginn meiner Recherche habe ich analysiert, welche Ressourcen für die Anwendung notwendig sind, um Unter- oder Überkapazitäten zu vermeiden. Hierzu habe ich den Kundensupport von Microsoft Azure kontaktiert, meine Anforderungen erläutert und um einen Vergleich verschiedener Optionen gebeten.
Antwort des Azure-Supports (zusammengefasst): Für die Web-Applikation wird der Azure App Service (Linux) im Basic B1 Plan (1 vCPU, 1,75 GB RAM) für ca. 30 Nutzer empfohlen. Die geschätzten Kosten in der Region „Germany West Central“ liegen bei etwa 45–55 USD pro Monat. Dieser Plan umfasst die verwaltete Runtime, Sicherheits-Patches sowie Monitoring.
Für die Datenbank wird ein Azure Database for PostgreSQL Flexible Server (1 vCore, 4 GB RAM, 100 GB Speicher) empfohlen. Die monatlichen Kosten belaufen sich auf ca. 55–70 USD. Hierbei sind automatisierte Backups (7 Tage, 4 Wochen, 3 Monate) bereits ohne manuellen Aufwand inkludiert.
Gesamtkosten Azure: ca. 100–125 USD pro Monat.
Einschätzung: Meiner Meinung nach ist dies eine sehr gute Option, da die Backups inklusive sind und ohne Skripte oder manuelle Eingriffe verwaltet werden. Langfristig ist diese Lösung wirtschaftlicher, da wir Arbeitsstunden sparen, die sonst für die Serverwartung angefallen wären. Alle Anforderungen an den App Service und die Datenbank werden abgedeckt. Beim Support habe ich mich für den Basic Support entschieden, da dieser für unsere Zwecke ausreicht und zusätzliche Gebühren vermeidet.

Abweichungen zur On-Premise-Infrastruktur
Im Vergleich zu AWS habe ich hier weniger Abweichungen. Ich habe bei DB diesmal ProstgreSQL gewählt, weil ich nicht weiss, was momentan verwendet wird. Und MySql und PostgreSQL sind beide beliebte Optionen.

Microsoft Azure Estimate						
Your Estimate						
Service category	Service type	Custom name	Region	Description	Estimated monthly cost	Estimated upfront cost
Compute	App Service		Germany West Central	Basic Tier; 1 B1 (1 Core(s), 1.75 GB RAM, 10 GB Storage) x 730 Hours; Windows OS; 0 SNI SSL Connections; 0 IP SSL Connections; 0 Custom Domains; 0 Standard SLL Certificates; 0 Wildcard SSL Certificates	CHF43.22	CHF0.00
Databases	Azure Database for MySQL		Germany West Central	Flexible Server Deployment, Business Critical Tier, 1 E2DS v4 (2 vCores) x 730 Hours, 100 GB Storage with ZRS redundancy, 0 million Paid IO, 0 GB Additional Backup storage with LRS, without High availability	CHF175.50	CHF0.00
Support			Support		CHF78.94	CHF0.00
			Licensing Program	Microsoft Customer Agreement (MCA)		
			Billing Account			
			Billing Profile			
			Total		CHF297.65	CHF0.00
						
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
