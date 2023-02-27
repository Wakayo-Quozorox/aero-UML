# Premier jet diagramme de cas d'usage

@startuml

' actors

actor administrateur

actor membre
actor instructeur
actor secretaire
actor mecanicien

' heritage des acteurs
top to bottom direction

membre <|-- instructeur

' logiciel

rectangle Logiciel {
    ' use cases    
    (Ajouter un avion au parc) as ajouterAvion
    (Réserver un avion) as reserverAvion
    (Controler un avion) as controlerAvion
    (Signaler les anomalies) as signalerAnomalie
    (Gérer le statut d'un avion) as gererStatutAvion

    (Plannifier une lecon) as plannifierLecon
    
    (Gérer les membres) as gererMembre
    (Ajouter un membre) as ajouterMembre
    (Modifier un membre) as modifierMembre
    (Supprimer un membre) as supprimerMembre
    (Acquitter sa cotisation annuelle) as acquitCotisation
    (Adhesion à la fédération française d’aviation) as adhesionFFA

    (Gérer les utilisateurs) as gererUtilisateurs
    (Ajouter un utilisateur) as ajouterUtilisateur
    (Supprimer un utilisateur) as supprimerUtilisateur

    (Rédiger un rapport de maintenance) as redigerRapport

    reserverAvion <.. plannifierLecon

    controlerAvion <.. signalerAnomalie

    gererUtilisateurs <|-- ajouterUtilisateur
    gererUtilisateurs <|-- supprimerUtilisateur

    gererMembre <|-- ajouterMembre
    gererMembre <|-- modifierMembre
    gererMembre <|-- supprimerMembre
    modifierMembre <.. acquitCotisation
    modifierMembre <.. adhesionFFA
    
    ajouterMembre <.. acquitCotisation
    ajouterMembre <.. adhesionFFA
}



left to right direction

membre --> controlerAvion

secretaire --> gererMembre
secretaire --> gererStatutAvion
secretaire --> reserverAvion
secretaire --> ajouterAvion
administrateur --> gererUtilisateurs

instructeur --> reserverAvion

mecanicien --> redigerRapport
mecanicien --> gererStatutAvion

@enduml