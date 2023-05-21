Comment j'organise un arpentage ?

# Déterminer l'ordre de passage

Si personne ne connaît le texte au préalable, mon ordre de passage peut grandement influencer mon expérience de lecture et de restitution. Tout dépends dans quelle mesure je me sens à l'aise avec l'exercice et/ou le texte.
Si le texte est facile à comprendre, passer parmi les premiers est plus rassurant. Si le texte est difficile à comprendre, c'est l'inverse.

## Comment déterminer l'ordre de passage d'un texte difficile ?

Le résultat de nos discussions :

* Lors d'un arpentage en présentiel, les premiers binômes à passé ont exprimé un rejet des idées et/ou de la rigueur (au sens manque d'étayage des idées avancées). Interprétation : plus on avance dans la lecture, plus on a un contexte dans lequel interpréter l'autrice et la charité herménotique devient de plus en plus facile. Equivalent d'une lecture en plusieurs passes d'un article compliqué. Dans un arpentage, les premières qui passent apportent plus de contexte que de contenu et c'est générateur de frustrations et de difficultées.
* la personne qui ouvre la voie est importante. Après cette personne, c’est plus facile pour les autres. Caractéristiques qui aident une personne à ouvrir une voie
  * familiarité avec le domaine du texte (par exemple, pour une prof de Français, et un texte écrit par une critique litéraire)
  * avoir déjà lu le texte

La méthaphore du guide de haute montagne pourrait être employé pour l'arpentage.

# Répartir les pages

Plusieurs méthodes possibles : assigner des pages dans le texte complet ou n'envoyer que les parties correspondantes.

## Intervalle de pages

Distribuer le texte complet et assigner des numéros de pages :
- personne 1 : 1-9
- personne 2 : 10-18
- personne 3 : 19-27
- personne 4 : 28-36
- personne 5 : 37-45
- personne 6 : 46-54

## Envoyer les fichiers à quelqu’un dans zoom

Il est possible de faire un clic droit sur une fenêtre vidéo pour envoyer un fichier à une participante en particulier.

## Découper l'ouvrage physiquement

Une vidéo est disponible sur youtube.

## Découper le pdf

### Extraire avec _ghostscript_

Découper au préalable et n'envoyer que chaque partie concernée :

> ghostscript -sDEVICE=pdfwrite -q -dNOPAUSE -dBATCH -sOutputFile=début.pdf -dFirstPage=1 -dLastPage=9 texte-complet.pdf


### Séparer en morceaux de n pages avec _pdftk_

[source](https://fosspost.org/divide-pdf-small-chunks-linux-command-line/)

```
$ cat ~/bin/pdfsplit.sh
#!/usr/bin/bash

number=$(pdfinfo -- "$file" 2> /dev/null | awk '$1 == "Pages:" {print $2}')

count=$((($number+$pagesper-1)/$pagesper))
filename=${file%.pdf}

counter=0
while [ "$count" -gt "$counter" ]; do
  start=$((counter*pagesper + 1));
  end=$((start + pagesper - 1));
  if [ $end -gt $number ]; then
    end=$number
  fi

  counterstring=$(printf %01d "$counter")
  pdftk "$file" cat "${start}-${end}" output "${filename}_${counterstring}.pdf"
  counter=$((counter + 1))
done

$ pagesper=5 file=E77676H7X112878_01012018_000730_001160.pdf pdfsplit.sh

$ ls E77676H7X112878_01012018_000730_001160*
E77676H7X112878_01012018_000730_001160_0.pdf   E77676H7X112878_01012018_000730_001160_3.pdf  E77676H7X112878_01012018_000730_001160_7.pdf
E77676H7X112878_01012018_000730_001160_10.pdf  E77676H7X112878_01012018_000730_001160_4.pdf  E77676H7X112878_01012018_000730_001160_8.pdf
E77676H7X112878_01012018_000730_001160_1.pdf   E77676H7X112878_01012018_000730_001160_5.pdf  E77676H7X112878_01012018_000730_001160_9.pdf
E77676H7X112878_01012018_000730_001160_2.pdf   E77676H7X112878_01012018_000730_001160_6.pdf  E77676H7X112878_01012018_000730_001160.pdf
```

Note pratique : commencer dans un répertoire vide, c’est plus pratique pour retrouver ses fichiers.


