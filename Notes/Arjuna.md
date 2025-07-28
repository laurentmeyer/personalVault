## Gestion du temps
* [ ] le timing des messages / articles devient relatif
- [ ] la date de début est une date YYYY-MM-DD-HH-mm
* [ ] ça permet de passer minuit sans problème
* [ ] plus facile pour tester (modèle plus simple)
* [ ] limite d'autres bugs (serveur sur une zone inhabituelle, qqun qui suit la formation avec un temps local différent)
* [ ] un peu plus chiant pour la rédaction du scénario
* [ ] c'est peut-être le moment de cleanup la base de données? #todo
* [x] on valide ?
### Futures idées
## Facture
- gdocs
## Bugs
* site pas whitelisté => responsive design
* site pas vu comme une menace: https??
- zone de test / profil public avec une erreur "ceci sera dispo le jour J"
* ajouter un bouton PDF
* mettre un background "exercice"
* recherche des auteurs / hasth
## Finalisation minuit
* faire une sauvegarde d'absolument tout
* voir si on ne veut pas faire d'autres modifs par la même occasion
* faire l'etat actuel du process et de la db
* rédiger l'état final
* voir comment migrer
### Design cible
- Le backend renvoie une liste de messages avec la bonne heure
	- de back vers front pour un message = heure de début + offset
	- de front vers back = heure actuelle - heure de début
### Changements à faire
* Article et Message gardent la propriété time : pas de changement à faire
* firstMessageTime, lastMessageTime et sessionStartTime sont supprimés
* creation d'un datetime sessionStart
* j'ai l'impression que Strapi enregistre à l'heure du systeme. Je n'ai pas trop voulu investiguer mais dans le doute j'ai mis la timezone française en dur
