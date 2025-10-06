# Correction Projet : Git / GitHub

Ce projet contient **trois exercices** réalisés entièrement via le **terminal**, dans le but de comprendre les bases de **Git** et **GitHub**, notamment la création de dépôts, les commits, la gestion des branches et la résolution de conflits.

---

## Exercice N°1 — *First Repo & Simple Commit*

### Objectif
Comprendre comment créer un dépôt Git, y effectuer des changements, et suivre l’historique des commits.

### 1. Enoncer 
- Créez un nouveau repo GitHub appelé<br>
- git-learning-1. <br>
- Clonez le localement <br>
- Créez un fichier README.md with some text (exemple: "Mon premier projet Git") <br>
- Ajoutez une autre ligne au README.md (votre nom et le numéro de votre MAc), puis faites un commit, puis un push final <br>
- Sur GitHub, vérifier l'historique des commits

### 2. Reponce 
1. gh repo create "git-learning-1" --public : cette commande permet de créer un repo github (dépot) apartir du terninal <br> 
2. git clone https://github.com/Sultan9463/git-learning-1.git : ça permet de cloner du dépôt en local via le terminal.  
3. echo "Mon premier projet Git" > README.md pour creer  un fichier `README.md` contenant le texte :  Mon premier projet Git
4. echo "nom : sultan et le numéro de votre MAc 9" >> README.md : les deux chevrons >> ça indique que on a ajouter une autre ligne dans le fichier .
5. git add README.md : pour prendre en compte les modification dans le fichier.
6. git commit -m "message" : pour faire un commit
7. git push -u origin main : pour pousser les modification vers le github
8. verififaction du l'historique dans github
![commit-history](/histori_du_commit.png)

## Exercice N°2 — *Branching & Merging*

### Objectif
Apprendre à créer des branches, y effectuer des modifications, puis les fusionner dans la branche principale (main).

### 1. Enoncer 
- Depuis un repo clonez du nom: git-learning-2 que vous aurez créez créez une nouvelle branche du nom de myself.<br>
- Créez un fichier about.txt avec des infos sur vous (nom, prénom, lieu de naissance...)<br>
- Faites un commit puis, puis pushez la branche myself. <br>
- Faites un pull request de git-learning-2/myself -> main. <br>
- Mergez le pull request. <br>
- Sur GitHub, vérifier l'historique. <br>

### 2. Reponse
1. git clone https://github.com/username/git-learning-2.git pour cloner un fichier de local vers github
2. git checkout -b myself : il vas créer une branche et basculé directement vers la branche 
3. echo -e "Nom : Zeyanou\nPrenom : Arzika\nPays : Niger" > about.txt
4. git add about.txt : pour prendre toutes les modifications
5. git commit -m "ajout" 
6. git push -u myself pour poussser vers gitgub
7. gh pr create --base main --head myself --title "Merge branch myself" --body "Ajout du fichier about.txt" : ici ce pour creer un pull request c'est a dire une demande d'extration.
8. gh pr lis : pour verifier si y'a un pull request en cours
9. gh pr merge : pour fussionner les pull request.
10. verification de l'historique
![commit-history](/Capture%20d’écran%202025-10-06%20à%2007.45.56.png)

## Exercice N°3 — *Gestion des conflits durant le merging*

### Objectif
Comprendre comment gérer les conflits lors d’un merge entre deux branches contenant des modifications sur le même fichier

### 1. Enoncer
- Créez un nouveau repo GitHub appelé git-learning-3. <br>
- Sur la branche main, ajoutez un nouveau fichier notes.txt avec pour contenu "Ligne écrite depuis la branche main".<br>
- Faites un commit et pushez. <br>
- Créez une branche conflict-test <br>
- Editez note.txt depuis la branche conflict-test et insérez y la phrase "Ligne écrite depuis la branche conflict-test". <br>
- Faites un commit et pushez. <br>
- Revenez à la branche main et remodifiez notes.txt différemment avec la phrase "Ligne écrite depuis la branche main pour la seconde fois". <br>
- Faites un commit et pushez. <br>
- Essayez de merger la branche conflict-test dans main.

- Vous obtiendrez une **erreur**. <br>

- Ouvrez notes.txt depuis votre éditeur de code, et résolvez le conflit manuellement (décidez de gardez les deux lignes). <br>
- Vérifiez la version finale sur Github en ouvrant note.txt. <br>

### 2. Reponse
1. gh repo create "git-learning-3" --public : cette commande permet de créer un repo github (dépot) apartir du terninal <br> 
2. git checkout -b main : creer la branche main et basculer vers main automatiquement
3. git echo "Ligne écrite depuis la branche main"  > notes.txt 
4. git add notes.txt : prendre les modification en compte
5. git commit -m "message" 
6. git push -u origin main : pousser vers github
7. git checkout -b conflict-test : creer une nouvelle branch conflict-test
8. echo "Ligne écrite depuis la branche conflict-test" > notes.txt 
9. git add notes.txt
git commit -m "message"
10. git push -u origin conflict-test
11. git checkout main : pour revenir a la branch main
12. echo "Ligne écrite depuis la branche main pour la seconde fois" > notes.txt : il vas prendre ce modification en compte et il vas ecraser les premiers modifications 
13. git add notes.txt
14. git commit -m "message"
15. git push -u origin main 
16. git merge conflict-test : essai de merger conflict-test
17. Voici le message erreur << **CONFLICT (content): Merge conflict in notes.txt
Automatic merge failed; fix conflicts and then commit the result.** >> pour ça ont va juste aller dans le dossier manuellement et edité le test.
18. pour verifier la version final sur github avec le terminal ont fait cat notes.txt

## Experiences aquises
Création et configuration d’un dépôt Git et GitHub apartir du ternimal 

Suivi de l’historique avec avec la commande **git log**

Création et fusion de Pull Requests

Résolution de conflits lors d’un merge