# KN04: Cloud-init und AWS

## A) Cloud-init Datei Verstehen (10%)

```
#cloud-config
users:  # User die man neu erstellt oder existierende User konfiguriert
  - name: ubuntu # Benutzername 
    groups: [users, admin] # Gruppen in welchem dr User ist users=Standardgruppe admin=erweiterte Rechte
    shell: /bin/bash # Standard Shell wird festgelegt in unserem Fall Shell
    sudo: ALL=(ALL) NOPASSWD:ALL # Der User kann alles ald jeden User und zwar ohne Passwort ausführen
    ssh_authorized_keys: # Liste der öffentlichen SSH Keys
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC0WGP1EZykEtv5YGC9nMiPFW3U3DmZNzKFO5nEu6uozEHh4jLZzPNHSrfFTuQ2GnRDSt+XbOtTLdcj26+iPNiFoFha42aCIzYjt6V8Z+SQ9pzF4jPPzxwXfDdkEWylgoNnZ+4MG1lNFqa8aO7F62tX0Yj5khjC0Bs7Mb2cHLx1XZaxJV6qSaulDuBbLYe8QUZXkMc7wmob3PM0kflfolR3LE7LResIHWa4j4FL6r5cQmFlDU2BDPpKMFMGUfRSFiUtaWBNXFOWHQBC2+uKmuMPYP4vJC9sBgqMvPN/X2KyemqdMvdKXnCfrzadHuSSJYEzD64Cve5Zl9yVvY4AqyBD aws-key
ssh_pwauth: false  # Man kann sich nur mit SSH keys anmelden (Sicherheit)
disable_root: false  # Root Konto wird nicht deaktviert
package_update: true # Führt update
packages: # Die Packages die installiert werden...
  - curl # Zum übertragen von Dateien via HHTP usw.
  - wget # Dowload Tool
  - 
```

## B) SSH-Key und Cloud-init (15%)

## Ein Screenshot der Details der Instanz. Scrollen Sie so weit runter, dass das Feld "Key pair assigned at launch", sichtbar ist.

<img width="2190" height="850" alt="image" src="https://github.com/user-attachments/assets/7b9fcb3a-6f14-420c-9a7d-9f3777844258" />

## Screenshot mit dem ssh-Befehl und des Resultats unter Verwendung des ersten Schlüssels.

<img width="1186" height="128" alt="image" src="https://github.com/user-attachments/assets/f7734a99-acb8-47b6-acdd-92d380ec5f23" />

## Screenshot mit dem ssh-Befehl und des Resultats unter Verwendung des zweiten Schlüssels.

<img width="1226" height="142" alt="image" src="https://github.com/user-attachments/assets/0f1f8dd5-167c-4de9-9411-6132d07d7991" />

## Screenshot mit dem Auszug aus dem Cloud-Init-Log. Der Befehl den Sie aufgerufen haben um das Log darzustellen und der obere Teil des Logs sollten sichtbar sein. Sie müssen nicht das gesamte Log abgeben.

<img width="2246" height="1080" alt="image" src="https://github.com/user-attachments/assets/3e2684c9-3c5c-401b-aceb-8521c44830cd" />





    

