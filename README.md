# TP4 Master 1 MIAGE IoT

Membres du groupe : 

-Quentin Bertramo
-Alexandre de Santa Barbara
-Jules Vesnat

L'application du TP4 a été déployée sur Heroku, elle est accessible à cette adresse : https://m1miageiot.herokuapp.com/

L'adresse MAC de votre ESP est déjà enregistrée sur le serveur NodeJS, afin que la solution proposée fonctionne, il vous suffit de rajouter vos credentials wifi dans le fichier /esp32_lucioles/classic_setup.ino afin que votre ESP soit connecté au monde et qu'il puisse envoyer ses données de température et de lumières sur le serveur Heroku
Pour la sécurisation des données nous avons pensé à créer des JWT (Json Web Token) pour sécuriser les requêtes depuis les interfaces utilisateurs vers le serveur NodeJS déployé sur Heroku.

Un JSON Web Token est un access token (jeton d’accès) aux normes RFC 7519 qui permet un échange sécurisé de donnée entre deux parties. Il contient toutes les informations importantes sur une entité, ce qui rend la consultation d’une base de données superflue et la session n’a pas besoin d’être stockée sur le serveur (stateless session).
Le serveur Node possède l'algorithme de création de token et de chiffrement, il peut délivrer un token à une interface utilisateur si l'utilisateur s'est correctement authentifié. Toutes les autres requêtes GET et POST qui transiterons entre l'interface utilisateur et le serveur NodeJS possèderont un JWT pour renforcer la sécurité des requêtes avec un certificat HTTPS afin de mieux protéger les données.
