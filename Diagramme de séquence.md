
![[Pasted image 20250305130946.png]]


**Le diagramme de séquence UML est une représentation dynamique et détaillée d’un scénario décrit dans un diagramme de cas d'utilisation** :
*  Il montre la **chronologie des échanges** entre les objets du système.
*  Il **détaille l’exécution du scénario**, en spécifiant l’ordre des messages échangés.
        


---

![[Pasted image 20250305130547.png]]


---

## Exemple d'un diagramme de cas d'utilisation  pour un système e-commerce qui intègre l'intelligence artificielle 

```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle
skinparam actorStyle awesome

actor "Client" as client
actor "Administrateur" as admin
actor "Intelligence Artificielle" as ia
actor "Système de Paiement" as paiement

rectangle "Système E-Commerce" {
  usecase "S'inscrire" as UC1
  usecase "Se connecter" as UC2
  usecase "Parcourir les produits" as UC3
  usecase "Rechercher des produits" as UC4
  usecase "Consulter les détails d'un produit" as UC5
  usecase "Ajouter au panier" as UC6
  usecase "Passer commande" as UC7
  usecase "Suivre la commande" as UC8
  usecase "Laisser un avis" as UC9
  usecase "Gérer le catalogue" as UC10
  usecase "Gérer les commandes" as UC11
  usecase "Gérer les utilisateurs" as UC12
  usecase "Recommander des produits personnalisés" as UC13
  usecase "Analyser le comportement utilisateur" as UC14
  usecase "Optimiser les prix dynamiquement" as UC15
  usecase "Répondre aux questions (chatbot)" as UC16
  usecase "Détecter les fraudes" as UC17
  usecase "Prédire les tendances du marché" as UC18
  usecase "Traiter le paiement" as UC19
}

client --> UC1
client --> UC2
client --> UC3
client --> UC4
client --> UC5
client --> UC6
client --> UC7
client --> UC8
client --> UC9

admin --> UC10
admin --> UC11
admin --> UC12

ia --> UC13
ia --> UC14
ia --> UC15
ia --> UC16
ia --> UC17
ia --> UC18

paiement --> UC19

UC7 ..> UC19 : <<include>>
UC3 <.. UC13 : <<extend>>
UC7 <.. UC17 : <<include>>
@enduml

```

Ce diagramme montre:

**Acteurs:**

- Client: l'utilisateur principal du système
- Administrateur: gère le système
- Intelligence Artificielle: fournit des services basés sur l'IA
- Système de Paiement: acteur externe pour les transactions

**Cas d'utilisation pour le Client:**

- S'inscrire et se connecter
- Parcourir et rechercher des produits
- Consulter les détails d'un produit
- Ajouter au panier et passer commande
- Suivre la commande
- Laisser un avis

**Cas d'utilisation pour l'Administrateur:**

- Gérer le catalogue
- Gérer les commandes
- Gérer les utilisateurs

**Cas d'utilisation pour l'Intelligence Artificielle:**

- Recommander des produits personnalisés
- Analyser le comportement utilisateur
- Optimiser les prix dynamiquement
- Répondre aux questions (chatbot)
- Détecter les fraudes
- Prédire les tendances du marché

**Relations:**

- Le paiement est inclus dans le processus de commande
- La recommandation de produits étend la navigation
- La détection de fraude est incluse dans le processus de commande


---

## Le diagramme de séquence correspondant au diagramme de cas d'utilisation. 

Il détaille les interactions entre le **Client**, le **Système de recommandation de livres** et le **Système de recommandation IA**.


```plantuml
@startuml

actor "Client" as client
actor "Administrateur" as admin
actor "Intelligence Artificielle" as ia
actor "Système de Paiement" as paiement

participant "Système E-Commerce" as system

' Inscription et connexion
client -> system: S'inscrire
system --> client: Confirmation d'inscription
client -> system: Se connecter
system --> client: Accès autorisé

' Navigation et interaction avec les produits
client -> system: Parcourir les produits
system --> client: Affichage des produits
client -> system: Rechercher des produits
system --> client: Résultats de la recherche
client -> system: Consulter les détails d'un produit
system --> client: Affichage des détails

' Ajout au panier et commande
client -> system: Ajouter au panier
system --> client: Produit ajouté
client -> system: Passer commande
system -> paiement: Demande de paiement
paiement --> system: Confirmation de paiement
system --> client: Commande validée

' Suivi et avis
client -> system: Suivre la commande
system --> client: Statut de la commande
client -> system: Laisser un avis
system --> client: Avis enregistré

' Gestion par l'administrateur
admin -> system: Gérer le catalogue
system --> admin: Catalogue mis à jour
admin -> system: Gérer les commandes
system --> admin: Commandes mises à jour
admin -> system: Gérer les utilisateurs
system --> admin: Utilisateurs mis à jour

' Intelligence Artificielle
system -> ia: Analyser le comportement utilisateur
ia --> system: Résultats d'analyse
system -> ia: Recommander des produits personnalisés
ia --> system: Liste des recommandations
system --> client: Affichage des recommandations
system -> ia: Optimiser les prix dynamiquement
ia --> system: Prix mis à jour
system -> ia: Détecter les fraudes
ia --> system: Alerte fraude détectée
system -> ia: Prédire les tendances du marché
ia --> system: Tendances analysées

@enduml
```



