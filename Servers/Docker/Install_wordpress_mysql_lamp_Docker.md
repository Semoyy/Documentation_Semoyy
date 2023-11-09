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

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
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
