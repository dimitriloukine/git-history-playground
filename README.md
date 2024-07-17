# git-history-playground


# Déplacer un fichier sans perde l'historique

git mv ekino-de-bergerac.txt src/ekino-de-bergerac.txt

# Séparer un fichier en deux sans perdre l'historique

git switch -c split
git switch -c left
git mv ekino-de-bergerac.txt src/a2s9.txt
git commit -am "mv src/a2s9.txt"
*Retirer le contenu de la scene 10 du fichier a2s9*
git commit -am "split src/a2s9.txt"

git switch split
git switch -c right
git mv ekino-de-bergerac.txt src/a2s10.txt
git commit -am "mv src/a2s10.txt"
*Retirer le contenu de la scene 9 du fichier a2s9*
git commit -am "split src/a2s9.txt"

git switch split
git merge left right

# Concaténer deux fichiers en un sans perdre l'historique