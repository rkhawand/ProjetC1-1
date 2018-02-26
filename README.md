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

1. Créer une Certificat: Exécutez la commande suivante pour générer le certificat: 
```
Keytool - genkeypair - alias MyCert  -keyalg RSA -keystore “C:\Users\roudy\MyCert.cert”
```
2. Répondez aux questions posées
3. Modifier Configuration de Tomcat (le fichier server.xml under C:\Program Files\Apache Software Foundation\Tomcat 9.0\conf)
4. Ajouter un connecteur SSL avec les attributs suivantes
```
port="8443" protocol="org.apache.coyote.http11.Http11NioProtocol" maxThreads="150" SSLEnabled="true" scheme="https" secure="true" clientAuth="false" sslProtocole="TLS" keystoreFile="[Certifacte Location]" keystorePass="[Certificate Password]"
```
5. Redémarrer Tomcat

## Exemples 2:

Modifier les fichiers de déploiement d'application (pour ouvrir directement en mode https) en ajoutant:
```
<security-constraint>
    <web-resource-collection>
        <web-resource-name>HelloWorldApp</web-resource-name>
        <url-pattern>/*</url-pattern>
    </web-resource-collection>
    <user-data-constraint>
        <transport-guarantee>CONFIDENTIAL</transport-guarantee>
    </user-data-constraint>
</security-constraint>
```

## Liens Utils:

- **Installation/Déploiement/Développement/Exemples sur Tomcat:** 
  - <http://tomcat.apache.org/tomcat-9.0-doc/appdev/index.html>
  - <http://www-igm.univ-mlv.fr/~dr/XPOSE2003/tomcat/tomcat.php?rub=3>


- **Configuration du protocole SSL dans Tomcat:**
  - <https://tomcat.apache.org/tomcat-7.0-doc/ssl-howto.html>
  - <https://www.youtube.com/watch?v=rVt6g5AZ6ko>
  - <https://www.youtube.com/watch?v=yVAjpdLeqbw>
