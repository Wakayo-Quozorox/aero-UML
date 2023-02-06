---
tittle: "Projet de gestion d'un club de vol"
---

# Projet de gestion d'un club de vol

```mermaid
classDiagram

Utilisateur <|-- Administrateur
Utilisateur <|-- Secrétaire
Utilisateur <|-- Mécanicien
Utilisateur <|-- Membre
Membre <|-- Elève
Membre <|-- Instructeur
Location <|-- Leçon_pratique
Fiche_transfert <|-- Fiche_sortie
Fiche_transfert <|-- Fiche_entree


Instructeur "1" -- "0..*" Leçon_pratique
Elève "1" -- "*" Leçon_pratique
Parc_Avion "1" -- "1..*" Avion
Location "1" -- "1" Avion
Avion *-- Carnet_entretien

Mécanicien "1" -- "*" Rapport_maintenance
Carnet_entretien *-- Rapport_maintenance

Membre "1" -- "*" Location

class Utilisateur {
    Nom utilisateur
    Mot de passe
}

class Avion {
    Type
    Nombre heure de vol
    Statut
}

class Elève {

    Heure de vol avec instructeur
    Date de délivrance du certificat médical
    Date inscription en centre de formation
}

class Membre {
    Heure de vol en solo
    Nombre atterrissage
    Date de la dernière cotisation annuelle
    Date de la dernière adhésion à la FFA
    Date de naissance
}

class Parc_Avion {
    Nombre avions
}

class Carnet_entretien {
    Liste des rapports de maintenance
}

class Rapport_maintenance {
    Date entrée atelier
    Appareil
    Mécanicien
    Date
    Motif
    Compte rendu
    Conclusion
    Date de sortie
}

class Location {
    Date
    Heure de vol départ
    Heure de vol retour
    Appareil
    Membre
    Anomalies
    Prix
}

class Leçon_pratique {
    Prix instruction
}

class Fiche_transfert {
    Date
    Appareil
}

class Fiche_sortie {
    Prix
    
}

class Fiche_entrée{
    
}
```
