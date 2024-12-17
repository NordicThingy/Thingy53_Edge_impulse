# Mise en place du Machine learning sur le Thingy:53

Ce manuel a pour but d'expliquer comment mettre en place le Machine Learning sur le Thingy:53 pour détecter des mots ou des chocs...

**Matériel nécessaire :**
- nRF Edge Impulse
- Edge Impulse (ordinateur)
- Nordic Thingy:53

**Mise en place dans Edge Impulse sur ordinateur :**
- Rendez vous sur le lien suivant pour vous inscrire : https://studio.edgeimpulse.com/get-started

Exemple avec la détection du mot "helloworld" du bruit ambiant et d'autres mots
- Rendez vous ensuite sur le lien suivant : https://studio.edgeimpulse.com/public/582088/live
- En haut à droite, appuyez sur "Clone this project" et donnez lui un nom et faites "Clone project"
- Retournez maintenant sur votre arborescence de projet en cliquant sur votre icone en haut à droite puis "project"
- Appuyez sur le projet que vous venez de cloner
- Allez dans Data Acquisition pour visualiser ce qui a été fait dans les enregistrements de données, il y a deux sets de données "Train" et "Test", Train permet d'entrainer notre système et Teste, de le vérifier dans la partie Classifier
- Allez ensuite dans MFCC et faites "save parameters"
- Puis faites Generate features
- Vous pourrez visualiser l'analyse spectrale de chaque échantillon en modifiant celui qui s'affiche sur le haut de la page dans Parameters et une visualisation de la séparabilité des classes, c'est à dire si le système arrive facilement à faire la différence entre chaque échantillon.
Ex : Bonne séparabilité
![image](https://github.com/user-attachments/assets/2000c343-c895-4f79-8876-0cee82e1e718)
- Allez ensuite dans le menu Classifier et faites "Save & Train"
- Vous pourrez voir dans Model, la qualité de votre résultat :
![image](https://github.com/user-attachments/assets/354703e8-83fe-4cb3-8480-a6feafd8f622)
Nous voyons que le taux de bonne prédictions avec le set de données "Test" est de 93,3% (le système "écoute" chaque échantillon du set et regarde s'il le détecte bien comme le label associé)
Le loss représente l'erreur du modèle qui est de 0,19 ce qui montre que le modèle converge bien.
Dans le tableau, vous visualisez quel pourcentage de chaque label a été bien identifié ou identifié comme autre chose
Le F1 score est une métrique combinant précision (proportion de vraies prédictions parmi toutes les prédictions) et rappel (capacité à identifier toutes les occurrences d'une classe) compris entre 0 et 1. Plus le score est haut, mieux c'est.
L'exemple précédent montre donc une bonne précision, une bonne capacités à distinguer les claasses mais des légères confusion pour noise et unknow. le système est globalement fiable.
Le graphique de point en dessous représente le graph de quel valeur est confondu avec qui.
- Le système est maintenant fiable et entrainé pour détecter avec le Thingy:53

- Si vous souhaitez faire votre propre analyse, dans Data acquisition, il faut mesurer pour chaque paramètres 80% dans Train et 20% dans Test avec des gammes et des valeurs différentes.
- Suivez ensuite la même procédure que précédemment
**Mise en place de nRF Edge Impulse sur téléphone:**
- Rendez vous dans Edge Impulse et connectez vous avec le même compte que sur internet
- Ouvrez votre projet sur le téléphone et allumez le Thingy:53
- Dans devices, trouvez le et connectez vous y
- Allez dans l'onglet "Deployment" et appuyez sur Deploy en base de l'écran
- Allez ensuite dans Inferencing et faites "start"
- En fonction de l'exemple choisi ou du projet développé, vous pouvez tester votre capteur
