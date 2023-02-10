# Test de diagramme

@startuml

:Porteur de CB: as PorteurCB
:Client bancaire: as ClientBancaire

left to right direction

rectangle DAB {
    (Retirer des billets) as RetirerBillets
    (Effectuer un virement) as EffectuerVirement
}

PorteurCB <|-- ClientBancaire

PorteurCB --> RetirerBillets
ClientBancaire --> RetirerBillets
ClientBancaire --> EffectuerVirement


@enduml


