
# Topología Laboratorio IPv6 SLAAC 

Descripción del entorno de trabajo, archivos necesarios y deploy de la Topología



## Entorno de trabajo
- Laptop con sistema operativo Windows 10 y plataforma VMWare Workstation 16 Pro

- Se crea una VM con sistema operativo Ubuntu Server 22.04.3 con Docker engine

- Se instala Containerlab siguiendo instrucciones desde https://containerlab.dev/install/





    
## Deployment Docker Kaliipv6

- Descargar la imagen del Docker Kaliipv6 desde https://drive.google.com/file/d/1sUkIsvTK4-fJLdO2g5RqtSPhDNcfVc_4/view?usp=sharing

- Subir la imagen kaliipv6.docker al servidor Ubuntu y cargar el docker con el comando "docker load -i kaliipv6.docker"

## Deployment Topologia ipv6slaac.yml

- Desde la terminal Ubuntu clonar el contenedor GIT con el comando "git clone https://github.com/ernestosv73/ipv6slaac.git"

- Desde la terminal Ubuntu, crear el bridge y red compartida con los siguientes comandos:


     docker network create \
       --driver bridge \
       --opt "com.docker.network.bridge.name"="br-clab1" \
     redlan

Dentro del directorio ipv6slaac, ejecutar el archivo ipv6slaac.yml con el siguiente comando:

    clab deploy -t ipv6slaac.yml --network=lan

Comandos para acceder a los nodos PC1, PC3 y Router

 docker exec -it clab-ipv6slaac-PC1 /bin/bash

 docker exec -it clab-ipv6slaac-PC3 /bin/ash

 docker exec -it clab-ipv6slaac-router1 vtysh 








## Authors

- [@esanchezv73](https://github.com/ernestosv73/ipv6slaac)
- esanchez@ucasal.edu.ar

