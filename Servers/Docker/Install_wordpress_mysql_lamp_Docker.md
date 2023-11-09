Pour la preparation on a besoin de ces commandes pour notre conteneur:

Commençons donc par créer des répertoires pour le contenu que l'on souhaite modifier et conserver, en l'occurrence les fichiers du site et les bases de donnés :
```bash
mkdir -p ~/conteneur/www ~/conteneur/mysql
```
Rendons les lisibles et modifiables par Docker :

```bash
chmod 777 ~/conteneur/www ~/conteneur/mysql
```

Aller dans le répertoire du conteneur :

```bash
cd ~/conteneur
```

Voici comment vous pouvez exécuter ces commandes sur un serveur Ubuntu :

1. Ajoutez la clé GPG officielle de Docker :

```bash
   sudo apt-get update
   sudo apt-get install ca-certificates curl gnupg
   sudo install -m 0755 -d /etc/apt/keyrings
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

2. Ajoutez le référentiel Docker aux sources Apt avec la commande corrigée :

```bash
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

3. Mettez à jour les informations du package Apt pour prendre en compte le nouveau référentiel Docker :

```bash
   sudo apt-get update
```

Après avoir suivi ces étapes, vous pourrez installer Docker avec LAMP sur votre serveur Ubuntu à l'aide de la commande :
```bash
   sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
Apres on a besoin de runner notre conteneur :
```bash
sudo docker run -i -t -p "80:80" -v ${PWD}/www:/app -v ${PWD}/mysql:/var/lib/mysql mattrayner/lamp:latest
```
![image](https://github.com/Semoyy/Documentation_Semoyy/assets/89610220/99db2f5d-f5aa-4832-9c8e-a60bb23eb058)

Dans se screen montre le user et passwd : 

```bash
mysql -uadmin -pGVrow68Big56 -h<host> -P<port>
```

Il va le falloir le detruire avec `Ctrl+C` ensuite pour le run en background avec `-d` puis le nom du conteneur :
```bash
docker run -i -t -p "80:80" -v ${PWD}/www:/app -v ${PWD}/mysql:/var/lib/mysql -d mattrayner/lamp:latest
```
Le `CONTAINER_ID` qui va en decouler sera important pour le restant car nous allons en avoir besoin pour verifier son fonctionnement.
`4a0d5326d0833930a60782eb77f07963bb3931c21632813663a3a9ab02c40222` pour mon cas sera utiliser dans cette commande: 
```bash
sudo docker logs 4a0d5326d0833930a60782eb77f07963bb3931c21632813663a3a9ab02c40222
```



