# Répartir les pages

## Intervalle de pages

Distribuer le texte complet et assigner des numéros de pages :
- personne 1 : 1-9
- personne 2 : 10-18
- personne 3 : 19-27
- personne 4 : 28-36
- personne 5 : 37-45
- personne 6 : 46-54

## Découpage préalable

Découper au préalable et n'envoyer que chaque partie concernée :

> ghostscript -sDEVICE=pdfwrite -q -dNOPAUSE -dBATCH -sOutputFile=début.pdf -dFirstPage=1 -dLastPage=9 texte-complet.pdf
