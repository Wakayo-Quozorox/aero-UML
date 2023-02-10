# Premier jet diagramme de cas d'usage

@startuml

' actors

'together {
    actor administrateur
    actor secretaire
    actor mecanicien
    actor membre
    'together {
        actor instructeur
        'actor eleve
    '}
'}

' heritage des acteurs
top to bottom direction

membre <|-- instructeur

' logiciel

rectangle Logiciel {
    ' use cases    
    (Gérer le parc) as gererParc
    (Réserver un avion) as reserverAvion
    (Controler un avion) as controlerAvion
    (Signaler les anomalies) as signalerAnomalie
    (Relever horametre) as releverHorametre
    (Gérer le statut d'un avion) as gererStatutAvion

    (Plannifier une lecon) as plannifierLecon
    
    (Gérer les membres) as gererMembres
    (Gérer les utilisateurs) as gererUtilisateurs

    (Rédiger un rapport de maintenance) as redigerRapport
}

left to right direction

membre --> controlerAvion
membre --> signalerAnomalie
membre --> releverHorametre

secretaire --> gererMembres
secretaire --> gererStatutAvion
secretaire --> reserverAvion
secretaire --> plannifierLecon
secretaire --> gererParc

administrateur --> gererUtilisateurs

instructeur --> plannifierLecon
instructeur --> reserverAvion

mecanicien --> redigerRapport
mecanicien --> gererStatutAvion

@enduml