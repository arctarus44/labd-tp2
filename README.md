labd-tp2
--------

Arthur Dewarumez
================

exercice 1
----------
....1. Question 1
        *//livre[titre="edition"] sélection le ou les nœuds livre dont le fils titre faut "edition"

        *//livre[titre=edition] sélection le ou les nœuds livre dont le file titre est identique au nœud edition

        *Pour que ces le résultat de ces deux expressions soit égale, on peu utiliser le fichier suivant

        ```xml
        <?xml version="1.0" encoding="UTF-8"?>
        <bibliotheque>
        ....<livre>
        ........<titre>edition</titre>
........        <edition>edition</edition>
        ....</livre>
        ....<livre>
        ........<titre>editions</titre>
        ........<edition>edition</edition>
        ....</livre>
        </bibliotheque>
        ```

    2. Question 2
        */item/livre[@titre="labd" and position()=last()] : retourne le dernier les élément livre ayant un attribut titre à labd et qui se trouve en dernière position
        */item/livre[@titre="labd"] [position()=last()] : retourne les élément livre contenant un attribut titre à labd et sélectionne le dernier
        */item/livre[position()=last()] [@titre="labd"] : retourne le dernier éléments livre et filtre en fonction de la présence d'un attribut titre valant labd

        *```xml
        <?xml version="1.0" encoding="UTF-8"?>
        <item>
        ....<livre titre="labd">
        ........<titre>edition</titre>
        ........<edition>edition</edition>
        ....</livre>
        ....<livre>
        ........<titre>editions</titre>
        ........<edition>edition</edition>
        ....</livre>
        ....<livre titre="labda">
        ........<titre>edition</titre>
        ........<edition>edition</edition>
        ....</livre>
        </item>
        ```

        Pour ce fichier, la première expression retournera rien, la deuxième expression retournera le premier nœud livre, la dernière expression retournera rien.

    3. Question 3
        *//livre[1] : retourne le premier livre de chaque nœud
        */descendant::livre[1] : retourne le premier livre de la racine
        ```xml
        <?xml version="1.0" encoding="UTF-8"?>
        <item>
            <a>
                <livre titre="labd">
                    <titre>edition</titre>
                    <edition>edition</edition>
                </livre>
            </a>
            <livre>
                <titre>editions</titre>
                <edition>edition</edition>
            </livre>
            <livre titre="labda">
                <titre>edition</titre>
                <edition>edition</edition>
            </livre>
        </item>
        ```

        La première commande retournera deux éléments livre, la deuxième un seul élément livre.


exercice 2
----------
    1. //fruit/producteur  (voire si on ne peut pas sélectionner que le text
    2. //legume[origine="Espagne"]/@type
    3. //fruit[@type="clementine"][@calibre="1"]//bio/../origine
    4. //origine[@region="Bretagne"]/../producteur


exercice 3
----------
    * recettes 1:
        1. //titre
        2. //nom_ing
        3. /cuisine/recette[2]/titre
        4. /cuisine/recette/texte/etape[position()=last()]
        5. count(/cuisine/recette)
        6. /cuisine/recette[count(./ingredients/ingredient)<7]
        7. /cuisine/recette/titre[count(../ingredients/ingredient)<7]
        8.
        9.

    * recettes 2:
        1. //titre
        2. //ingredient
        3. /cuisine/recette[2]/titre
        4. /cuisine/recette/texte/etape[position()=last()]
        5. count(/cuisine/recette)
        6. /cuisine/recette[count(./ingredients/ing-recette)<7]
        7. /cuisine/recette/titre[count(../ingredients/ing-recette)<7]
        8.
        9.


exercice 4
----------
    1. count(/plist/dict[position()=1]/key[text()="Tracks"]/following-sibling::dict[position()=1]/key)
    2. /plist/dict[position()=1]/key[text()="Tracks"]/following-sibling::dict[position()=1]/dict/key[text()="Album"]/following-sibling::string[position()=1]
    3. /plist/dict[position()=1]/key[text()="Tracks"]/following-sibling::dict[position()=1]/dict/key[text()="Genre"]/following-sibling::string[position()=1]
    4. count(/plist/dict[position()=1]/key[text()="Tracks"]/following-sibling::dict[position()=1]/dict/key[text()="Genre"]/following-sibling::string[position()=1 and text()="Jazz"])
    5. distinct-values(/plist/dict[position()=1]/key[text()="Tracks"]/following-sibling::dict[position()=1]/dict/key[text()="Genre"]/following-sibling::string[position()=1])
    6. /plist/dict[position()=1]/key[text()="Tracks"]/following-sibling::dict[position()=1]/dict/key[text()="Name"]/following-sibling::string[position()=1 and ../key[text()="Play Count"]/following-sibling::integer[position()=1 and text()>="1"]]
    7./plist/dict[position()=1]/key[text()="Tracks"]/following-sibling::dict[position()=1]/dict/key[text()="Name"]/following-sibling::string[position()=1 and count(../key[text()="Play Count"]) = 0]
    8.
    9.