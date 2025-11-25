## KN04: Cloud-init und AWS

##A) Cloud-init Datei Verstehen (10%)

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
  - curl
  - wget
  - 
```

    

