# Test de diagramme

@startuml

left to right direction

:Porteur de CB: as PorteurCB
:Client bancaire: as ClientBancaire

rectangle DAB {
    (Retirer des billets) as RetirerBillets
    (Effectuer un virement) as EffectuerVirement
    (S'authentifier) as Authentifier
    (Changer le compte à débiter) as ChangerCompte
}

ClientBancaire -- RetirerBillets

PorteurCB --> RetirerBillets
PorteurCB --> EffectuerVirement
ChangerCompte --> Authentifier

@enduml


