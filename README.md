# Arpentage : note d'intention

Ce que les organisatrices espèrent que la session va produire :
* Rencontrer la pensée d'une autrice
* Savoir comment d'autres personnes comprennent un de ses textes
* Apprendre à arpenter un texte

# Arpenter "Le temps des bûchers" de Starhawk

## Ne venez pas si
* Vous êtes mal à l'aise avec le néo paganisme
* Vous êtes mal à l'aise avec le concept de sorcière
* Vous détestez le moyen age

## Préparation de l’arpentage

- [1er test d'arpentage - 15 février 2023](2023-02-15-notes-de-travail.html)
- [2ème test d'arpentage - 22 février 2023](2023-02-22-préparation_le_temps_des_bûchers.html)
- [rétro planning - 22 mars 2023](2023-03-22-rétro-planning.html)

Nous publions nos notes pour :

* rendre visible la manière dont nous travaillons
* permettre aux participantes de choisir de venir en connaissance de cause
* nous améliorer en comparant leurs retours à nos intentions

### Prochaine session de préparation mercredi 29 mars à 15h

https://arpentages.github.io

#### Comment déterminer l'order de passage ?
* Lors d'un arpentage en présentiel, les premiers binômes à passé ont exprimé un rejet des idées et/ou de la rigueur (au sens manque d'etayage des idées avancées). Interprétation : plus on avance dans la lecture, plus on a un contexte dans lequel interprété l'autrice et la charité herménotique devient de plus en plus facile. Equivalent d'une lecture en plusieurs passes d'un article compliqué. Dans un arpentage, les premières qui passent apportent plus de contexte que de contenu et c'est générateur de frustrations et de difficultées.
* la personne qui ouvre la voie est importante. Après cette personne, c’est plus facile pour les autres. Caractéristiques qui aident une personne à ouvrir une voie
  * familiarité avec le domaine du texte (par exemple, pour une prof de Français, et un texte écrit par une critique litéraire)
  * avoir déjà lu le texte
* => question du guide de haute montagne. Ce serait sans doute plus facile pour Philippe d’ouvrir.
* contre argument : celle qui commence (et celle qui finit) a une influence particulière sur le contenu de la conversation.

* parler de quels besoins nous sommes en train de nourir en tant qu'organisatrices en faisant cet arpentage ?

#### comment séparer un pdf en morceaux de n pages 

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
