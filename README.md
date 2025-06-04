#- jenkins-docker
configure and use jenkins cloud






entonces recapitulando


se ncesita una cuenta de github
que tu pc tenga como minimo 32gb de ram para emular todo

que sea desde un (8 octacore) o cualquier cosa raizen 9 para arriba los i7 tambien todo eso para arriba ahora la configuracion es un parto pero es la pega una vez hecha ya esta ...


Amd o nvidia video




proyecto-root/
├── docker-compose.yml
├── imagenes/
│   ├── jenkins/
│   │   ├── Dockerfile







#version: '3.8'
services:
  jenkins:
    build: ./imagenes/jenkins/.
    container_name: jenkins
    restart: unless-stopped
    ports:
      - "8080:8080"
      - "50000:50000"
    volumes:
      - C:\Users\gomi\Desktop\test-yaml\jenkins\branch\jenkins-docker\jenkins_home:/var/jenkins_home
      - C:\Users\gomi\Desktop\test-yaml\jenkins\branch\jenkins-docker\var\run\docker.sock:/var/run/docker.sock
      - C:\Users\gomi\Desktop\test-yaml\jenkins\branch\jenkins-docker\plugins.txt:/usr/share/jenkins/ref/plugins.txt  # Plugins automáticos
      - C:\Users\gomi\Desktop\test-yaml\jenkins\branch\jenkins-docker\jenkins.yaml:/var/jenkins_home/casc.yaml  # Configuración como código
    environment:
      - TZ=America/Santiago
      - JAVA_OPTS=-Djenkins.install.runSetupWizard=false
      - CASC_JENKINS_CONFIG=/var/jenkins_home/casc.yaml  # Habilita JCasC

volumes:
  jenkins_home:



#-- docker-compose up -d --build


$ docker compose up --build -d
Compose can now delegate builds to bake for better performance.
 To do so, set COMPOSE_BAKE=true.
[+] Building 52.0s (7/7) FINISHED
 => [jenkins internal] load build definition from Dockerfile
 => => transferring dockerfile: 248B
 => [jenkins internal] load metadata for docker.io/jenkins/jenkins:lts
 => [jenkins internal] load .dockerignore
 => => transferring context: 2B
 => [jenkins 1/2] FROM docker.io/jenkins/jenkins:lts@sha256:2abbd073f06850c3c962eedaa10e7aa21c517db1e582ad8c89b83ecfb6cb7510
 => => resolve docker.io/jenkins/jenkins:lts@sha256:2abbd073f06850c3c962eedaa10e7aa21c517db1e582ad8c89b83ecfb6cb7510
 => [jenkins 2/2] RUN apt-get update && apt-get install -y maven     && [ ! -f /usr/bin/mvn ] && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn || echo "Mvn already exists"
 => [jenkins] exporting to image
 => => exporting layers
 => => exporting manifest sha256:8f47e5a0e89f70a5b8c9cecad7a53e2865774db076d020f898214aac5bbd7fa6
 => => exporting config sha256:d319a1e5b643b7933dfae67a762af4a350989c4f109db169f282711194c5ea58
 => => exporting attestation manifest sha256:c6cca1b7622d31c607dc2c537e308dd53adab0e0924d4146a67221d03874026a
 => => exporting manifest list sha256:6cf7af857a430268af18d7a4b82a09b65bf93bc4dc00dd1862fc74a1dbaca540
 => => naming to docker.io/library/jenkins-docker-jenkins:latest
 => => unpacking to docker.io/library/jenkins-docker-jenkins:latest
 => [jenkins] resolving provenance for metadata file
[+] Running 3/3
 ✔ jenkins                         Built
 ✔ Network jenkins-docker_default  Created
 ✔ Container jenkins               Started











una imagen extendida de jenkins con java y mvn para que ejecute el codigo java en este caso 


1.- se configura el repositorio en github
2.- lo clonas en local y realizan un commit un pull y push 
3.- generas docker-compose.yaml 
4.1 generas configuracion local y la maquina destino path estos los archivos fisicos
5.- Pasas un servless Jenkins con un Dockerfile 
6.- la configuracion del la maquina mvn y java jenkins 
7.- configurar github repository user ssh ... 
8.- configure from cmd or shell scripting create, admin this virtual machine
9.- configure el jenkins tareas o jobs con repository
10.- review configure and ejecute ....
11.-
12.-







