# 3ème test : envoi à distance - 29 mars 2023

Le test : 4 pages lues en 15 minutes et restituées en 10 minutes par personne (total 20')

## Comment déterminer l'ordre de passage ?
* Lors d'un arpentage en présentiel, les premiers binômes à passé ont exprimé un rejet des idées et/ou de la rigueur (au sens manque d'etayage des idées avancées). Interprétation : plus on avance dans la lecture, plus on a un contexte dans lequel interprété l'autrice et la charité herménotique devient de plus en plus facile. Equivalent d'une lecture en plusieurs passes d'un article compliqué. Dans un arpentage, les premières qui passent apportent plus de contexte que de contenu et c'est générateur de frustrations et de difficultées.
* la personne qui ouvre la voie est importante. Après cette personne, c’est plus facile pour les autres. Caractéristiques qui aident une personne à ouvrir une voie
  * familiarité avec le domaine du texte (par exemple, pour une prof de Français, et un texte écrit par une critique litéraire)
  * avoir déjà lu le texte
* => question du guide de haute montagne. Ce serait sans doute plus facile pour Philippe d’ouvrir.
* contre argument : celle qui commence (et celle qui finit) a une influence particulière sur le contenu de la conversation.


## comment séparer un pdf en morceaux de n pages

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

## Envoyer les fichiers à quelqu’un dans zoom

Il est possible de faire un clic droit sur une fenêtre vidéo pour envoyer un fichier à une participante en particulier.
