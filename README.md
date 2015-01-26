labd-tp2
========

Arthur Dewarumez
================

exercice 2
----------
1 - //fruit/producteur  (voire si on ne peut pas sélectionner que le text
2 - //legume[origine="Espagne"]/@type
3 - //fruit[@type="clementine"][@calibre="1"]//bio/../origine
4 - //origine[@region="Bretagne"]/../producteur


exercice 3
----------

	* recettes 1:
		1) //titre
		2) //nom_ing
		3) /cuisine/recette[2]/titre
		4) /cuisine/recette/texte/etape[position()=last()]

	* recettes 2:
		1) //titre
		2) //ingredient
		3) /cuisine/recette[2]/titre
		4) /cuisine/recette/texte/etape[position()=last()]