# GIT  

# Partie 1 : Introduction à Git et aux bases  

## Qu’est-ce que Git ?  

Git est un système de gestion de version distribué, principalement utilisé pour suivre les modifications de fichiers et coordonner  
le travail entre plusieurs personnes sur un projet. Grâce à Git, tu peux enregistrer l’historique complet d’un projet,  
revenir à des versions antérieures, créer des branches pour tester des fonctionnalités et bien plus.  

## Pourquoi utiliser Git ?  

	1.	Suivi de l’historique : Git garde une trace de toutes les modifications effectuées sur les fichiers. Cela te permet de revenir en arrière si nécessaire.  
	2.	Collaboration : Git facilite le travail en équipe en permettant à plusieurs développeurs de travailler sur le même projet sans risquer de modifier le travail des autres.  
	3.	Branchements et expérimentations : Git permet de créer des branches qui isolent les changements. Ainsi, on peut expérimenter sans affecter la version principale du projet.  

## GitHub et GitLab  

GitHub et GitLab sont des plateformes d’hébergement de projets Git qui permettent de stocker, partager et collaborer en ligne.  
Les deux proposent des fonctionnalités comme la gestion des permissions, les discussions, les tickets de bug et l’intégration continue (CI/CD).  
GitHub est très populaire et largement utilisé, tandis que GitLab est apprécié pour ses fonctionnalités CI/CD intégrées et pour la possibilité d’être auto-hébergé.  

# Partie 2 : Installation et Configuration de Git  

## Avant d’utiliser Git, tu dois l’installer sur ton ordinateur :  

	•	Sur Windows : Télécharger Git  
	•	Sur Mac : brew install git (si Homebrew est installé)  
	•	Sur Linux : sudo apt install git (pour Debian/Ubuntu) ou sudo dnf install git (pour Fedora)  

## Configurer Git pour la première fois  

Après l’installation, configure ton nom d’utilisateur et ton e-mail avec les commandes suivantes :  
```bash
git config --global user.name "TonNom"  
git config --global user.email "TonEmail@example.com"  
```
Ces informations seront utilisées pour attribuer chaque changement que tu fais dans Git.  

# Partie 3 : Les Commandes Git  

## 1. Initialiser un dépôt Git  

Pour commencer à suivre un projet avec Git, va dans le dossier de ton projet et exécute :  
```bash
git init
```
Cette commande crée un dépôt Git local.  

## 2. Cloner un dépôt existant  

Si tu veux récupérer un projet depuis GitHub ou GitLab :  
```bash
git clone URL_DU_DEPOT
```

## 3. Ajouter des modifications  

Git surveille les fichiers ajoutés ou modifiés dans ton projet, mais ne les inclut pas automatiquement dans le prochain enregistrement.  
Pour ajouter des fichiers au “staging area” (zone d’attente avant validation) :  
```bash
git add fichier.txt        # Ajouter un fichier spécifique
git add .                  # Ajouter tous les fichiers modifiés
```

## 4. Enregistrer les modifications (Commit)  

Un commit est un enregistrement d’un ensemble de changements. Pour créer un commit :  
```bash
git commit -m "Message décrivant les modifications"
```

## 5. Ajouter et enregistrer des modifications ensemble  

Voici un exemple concret de l’ajout de modifications suivies d’un commit :  
```bash
# Supposons que tu as modifié des fichiers dans ton projet
git add fichier1.txt fichier2.txt        # Ajoute ces fichiers modifiés
git commit -m "Ajout des nouvelles fonctionnalités à fichier1 et fichier2"
```
Cet exemple te montre comment ajouter des fichiers spécifiques et les valider en un seul flux de travail.  

## 6. Vérifier l’état du dépôt  

Pour voir l’état actuel des modifications (fichiers ajoutés, modifiés, etc.) :  
```bash
git status
```

## 7. Voir l’historique des commits  

Pour consulter tous les commits effectués jusqu’à présent :  
```bash
git log
```

## 8. Travailler avec des branches  

Créer une nouvelle branche  
Les branches permettent de développer des fonctionnalités ou de corriger des bugs sans affecter la branche principale.  
```bash
git branch nom-de-la-branche
```

Changer de branche  
```bash
git checkout nom-de-la-branche
```

Créer et changer de branche en une seule commande  
```bash
git checkout -b nom-de-la-branche
```

Fusionner une branche  
Une fois que les changements d’une branche sont prêts, tu peux les fusionner dans une autre branche, par exemple main :  
```bash
git checkout main
git merge nom-de-la-branche
```

Supprimer une branche  
```bash
git branch -d nom-de-la-branche
```

## 9. Envoyer les modifications vers un dépôt distant  

Pour partager les modifications avec un dépôt distant, comme GitHub ou GitLab :  
```bash
git push origine nom-de-la-branche
```

## 10. Récupérer les modifications du dépôt distant  

Pour obtenir les dernières modifications du dépôt distant :  
```bash
git pull origine nom-de-la-branche
```

## 11. Voir les différences entre les fichiers  

Pour voir les différences entre les fichiers modifiés et la dernière version validée :  
```bash
git diff
```

## 12. Revenir à une version précédente  

Si tu veux revenir à une version précédente d’un fichier ou d’un projet :  
```bash
git checkout commit_hash    # pour revenir à un commit spécifique
git revert commit_hash      # annuler un commit
```

## 13. Réinitialiser le dépôt  

Pour annuler des modifications ou des commits de manière plus radicale :  
```bash
git reset --hard commit_hash
```

## 14. Rebaser une branche  

Le rebase permet de réécrire l’historique des commits, ce qui est utile pour garder un historique propre.  
Cependant, utilise cette commande avec précaution et uniquement si tu sais ce que tu fais.  
```bash
git rebase nom-de-la-branche
```

## 15. Stashing : sauvegarder temporairement des modifications  

Sauvegarder les modifications  
Pour sauvegarder temporairement les modifications non enregistrées :  
```bash
git stash
```

Voir la liste des stashes  
Pour voir tous les stashes enregistrés :  
```bash
git stash list
```

Restaurer le dernier stash  
Pour restaurer les modifications du dernier stash :  
```bash
git stash pop
```

Restaurer un stash spécifique  
Si tu veux restaurer un stash spécifique (par exemple stash@{1}) :  
```bash
git stash pop stash@{1}
```

Supprimer un stash spécifique  
Pour supprimer un stash particulier (par exemple stash@{0}) :  
```bash
git stash drop stash@{0}
```

Supprimer tous les stashes  
Pour supprimer tous les stashes enregistrés :  
```bash
git stash clear
```

# Récapitulatif des Commandes de Git  

| Commande                           | Description                                                         |
|------------------------------------|---------------------------------------------------------------------|
| `git init`                         | Initialise un nouveau dépôt Git                                     |
| `git clone <url>`                  | Clone un dépôt distant                                             |
| `git add <file>`                   | Ajoute des fichiers au staging area                                |
| `git commit -m "message"`          | Crée un commit avec un message                                     |
| `git status`                       | Montre l’état actuel des fichiers modifiés                         |
| `git log`                          | Affiche l’historique des commits                                   |
| `git branch <branch_name>`         | Crée une nouvelle branche                                          |
| `git checkout <branch_name>`       | Change de branche                                                  |
| `git checkout -b <branch_name>`    | Crée et change de branche en une seule commande                    |
| `git merge <branch_name>`          | Fusionne une branche dans la branche actuelle                      |
| `git push origin <branch_name>`    | Envoie les modifications vers un dépôt distant                     |
| `git pull origin <branch_name>`    | Récupère les modifications d’un dépôt distant                      |
| `git diff`                         | Affiche les différences entre les fichiers                         |
| `git revert <commit_hash>`         | Annule un commit spécifique en créant un nouveau commit            |
| `git reset --hard <commit_hash>`   | Réinitialise à un commit précédent, supprimant les modifications   |
| `git rebase <branch_name>`         | Applique les commits d’une branche sur une autre                   |
| `git stash`                        | Sauvegarde temporairement les modifications non enregistrées       |
| `git stash list`                   | Affiche la liste des stashes                                       |
| `git stash pop`                    | Restaure le dernier stash                                          |
| `git stash pop stash@{n}`          | Restaure un stash spécifique                                       |
| `git stash drop stash@{n}`         | Supprime un stash spécifique                                       |
| `git stash clear`                  | Supprime tous les stashes enregistrés                              |

# Conclusion  

Ce guide couvre les commandes essentielles et avancées de Git. Pour te perfectionner, pratique régulièrement et essaie de collaborer  
sur des projets sur GitHub ou GitLab. Cela te permettra d’approfondir  
