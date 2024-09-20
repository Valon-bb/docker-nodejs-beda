# Vorgehen beim Projekt  
![download](https://github.com/user-attachments/assets/9585929e-f97f-42af-ba1b-4790f98d4b46)
## Klonen des Repositories
Um das Repositorie auf den Laptob zu Klonen muss man zubeginn den SSH Schlüssel auf github finden und kopieren. Diesen Schlüssel findet man, wenn man in das     Reposetorie geht und dort auf Code clickt.  
Anschliessend muss man diesen Schlüssel zusammen mit dem folgenden befehl in die Git Bash eingeben.    

  **Achtung**: Schauen sie das in der Git Bash Konsole der gewünschte Speicherort ausgewählt ist.
  

      git clone SSH-Schlüssel
**PS**:Falls sie noch keinen Schlüssel haben können sie sich einen unter einstellungen in Github erstellen.
## Installation der notwendigen Pakete
Um die Applikation auf dem Docker zu starten muss man zuerst noch ein paar Dinge tun.
Zuerst sollten sie im Powershell des kopierten Reposetorys diesen Befehl eingeben:


      git clone https://github.com/docker/docker-nodejs-sample  
Anschliessend können sie noch einen weiteren Befehl eingeben um die Docker Assets anzupassen:


      docker init
Danach sollten sie das ganze wie folgt anpassen:


      ? What application platform does your project use? Node
      ? What version of Node do you want to use? 18.0.0
      ? Which package manager do you want to use? npm
      ? What command do you want to use to start the app: node src/index.js
      ? What port does your server listen on? 3000
## Docker-Konfiguration und -Installation  
### Docker Installiation
Um Docker für den Desktop zu Installieren klicken sie auf den folgenden Link. Anschliessend sollten sie Docker auch noch für Visual Studio code installieren.  
**Achtung**: Achten sie darauf das die Version mit ihrem Prozessor Kompatibel ist.  
[Doker Desktop](https://www.docker.com/products/docker-desktop/)   
[Docker VS](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
### Docker Konfiguration
Nach dem Installieren von Docker ist es wicht gewisse Dinge noch zu Konfigurieren.  
Dazu ist das optionale Feature Windows-Subsystem für Linux durch Ausführung der folgenden Anweisung in der Powershell zu aktivieren:  


      dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
Direkt danach aktiviert man für WSL2 die Virtual Machine Platform:


      dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
Um WSL standartmässig zu aktivieren sollte man den Folgenden befehl ebenfalls eingeben:


      wsl --set-default-version 2
## Starten der Applikation in einem Docker-Container  
Um die Applikation im Docker-Container zu Starten muss man nur einen Simplen befehl eingeben:


      docker compose up --build
Nun können sie im Browser unter diesem Link die Applikation begutachten:


      http://localhost:3000/
