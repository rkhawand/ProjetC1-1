![alt text](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR1TMG5of1htgEp5JdeHWiKIv__jVMSkiHG-7lEhaDs2QlAtrgM)

# Implémentation de protocole  SSL dans TOMCAT

## Plan de Presentation:

- **Introduction**
- **Apache Tomcat**
  - Fonctionnalité
  - Connecteurs
  - Serveur Web/Application
- **SSL (Secure Socket Layer)**
  - Fonctionnement 
  - Aspects Cryptographiques
  - Certificats
  - Utilisation de SSL
  - Avantages
- **Implémentation SSL dans TOMCAT**


## Exemples:

1- Exécutez la commande suivante pour générer le certificat: 
Keytool - genkeypair - alias MyCert  -keyalg RSA - keystore “C:\Users\roudy\MyCert.cert”
2- Répondez aux questions posées
3- Modifier le fichier server.xml (C:\Program Files\Apache Software Foundation\Tomcat 9.0\conf)
4- Ajouter un connecteur SSL
<Connector port="8443" protocol="org.apache.coyote.http11.Http11NioProtocol"
               maxThreads="150" SSLEnabled="true" scheme="https" secure="true" 
               clientAuth="false" sslProtocole="TLS" keystoreFile="C:\Users\roudy\MyCert.cert" 
               keystorePass="123456"/>
5- Redémarrer Tomcat


## Liens Utils:

- **Installation/Déploiement/Développement/Exemples sur Tomcat:** 
  - <http://tomcat.apache.org/tomcat-9.0-doc/appdev/index.html>
  - <http://www-igm.univ-mlv.fr/~dr/XPOSE2003/tomcat/tomcat.php?rub=3>


- **Configuration du protocole SSL dans Tomcat:**
  - <https://tomcat.apache.org/tomcat-7.0-doc/ssl-howto.html>
  - <https://www.youtube.com/watch?v=rVt6g5AZ6ko>
  - <https://www.youtube.com/watch?v=yVAjpdLeqbw>
