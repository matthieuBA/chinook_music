a) Niveau facile

    Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?

    > puts Album.count


    Qui est l'auteur de la chanson "White Room" ?

    >puts my_track= Track.find_by(title: 'White Room').artist


    Quelle chanson dure exactement 188133 milliseconds ?

    >puts my_track= Track.find_by(duration: '188133').title


    Quel groupe a sorti l'album "Use Your Illusion II" ?

    >puts my_group= Album.find_by(title: 'Use Your Illusion II').artist

b) Niveau Moyen

    Combien y a t'il d'albums dont le titre contient "Great" ? (indice)

    >puts great= Album.where("title like ?", "%Great%").count


    Supprime tous les albums dont le nom contient "music".

    >music= Album.where"titl, "%music%")
    >music.each { |obj| obj.destroy }


    Combien y a t'il d'albums écrits par AC/DC ?

    >puts acdc= Album.where("artist", "AC/DC").count


    Combien de chanson durent exactement 158589 millisecondes ?

    > my_track= Track.where(duration: '158589').count



c) Niveau Difficile

Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

    puts en console tous les titres de AC/DC.

    >acdc= Track.where(artist: 'AC/DC')
    > acdc.each {|tr| tr.title}


    puts en console tous les titres de l'album "Let There Be Rock".

    >acdc= Track.where(album: 'Let There Be Rock')
    >acdc.each {|tr| puts tr.title}


    Calcule le prix total de cet album ainsi que sa durée totale.

    >duration=0
    >price=0
    >acdc= Track.where(album: 'Let There Be Rock')
    >acdc.each {|tr| duration+=tr.duration}
    >acdc.each {|tr| price+=tr.price}
    >puts duration
    >puts price

    Calcule le coût de l'intégralité de la discographie de "Deep Purple".

    >duration=0
    >deep= Track.where(artist: 'Deep Purple')
    >deep.each {|tr| duration+=tr.price}
    >puts duration


    Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.

    >clap= Track.where(artist: 'Eric Clapton')
    >clap.each {|tr| tr.update(artist: 'britney spears')}
    