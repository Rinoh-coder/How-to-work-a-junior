# FRAMEWORK KANBAN

## 1. Définition et Philosophie Fondamentale
Kanban est une méthode de gestion du flux de travail (workflow) conçue pour optimiser la prestation de services, gérer le travail immatériel et améliorer continuellement les processus existants de manière évolutive, sans rupture brutale.

---
## 2. Les Principes Fondamentaux  

### Principes de Gestion du Changement

* Commencer là où vous êtes : Accepter les processus, les rôles, les responsabilités et les titres actuels. Kanban s'implante sur l'existant.
* Rechercher l'amélioration continue : Encourager des changements évolutifs, progressifs et négociés (Kaizen) plutôt que des révolutions structurelles.
* Encourager le leadership à tous les niveaux : Valoriser les initiatives d'amélioration provenant de chaque membre de l'organisation, du contributeur individuel aux dirigeants.


### Principes de Prestation de Services

* Se concentrer sur les besoins du client : Aligner le système sur la satisfaction et la valeur attendue par le client.
* Gérer le travail, pas les personnes : Laisser les professionnels s'organiser autour des tâches et se concentrer sur la fluidité du flux.
* Faire évoluer le réseau de services : Optimiser les interactions entre les différentes équipes interconnectées pour maximiser la performance globale.

---
## 3. Les 6 Pratiques Clés  

### Pratique 1 : Visualiser le travail
Le travail invisible doit être matérialisé. On cartographie les étapes logiques du processus de l'organisation sous forme de colonnes sur un tableau. Chaque tâche est représentée par une carte contenant ses métadonnées (responsable, date d'entrée, description). Cela permet d'identifier immédiatement la charge de travail, les goulots d'étranglement et la stagnation.

### Pratique 2 : Limiter le travail en cours (WIP - Work In Progress)
Il s'agit de fixer un seuil numérique maximal de cartes autorisées simultanément dans une colonne ou pour une étape donnée. Réduire le WIP permet de concentrer l'effort sur la finalisation des tâches existantes plutôt que sur le démarrage de nouvelles. Cela réduit les temps de cycle et élimine le coût lié au multitâche.

### Pratique 3 : Gérer le flux
L'objectif est de maximiser la régularité et la vitesse de déplacement des cartes à travers le système. On analyse les blocages et les temps d'attente. L'équipe suit deux indicateurs temporels :

* Lead Time : Temps total écoulé entre la formulation de la demande par le client et sa livraison finale.
* Cycle Time : Temps pendant lequel l'équipe travaille activement sur la tâche, depuis son entrée en production jusqu'à sa finalisation.

### Pratique 4 : Rendre les politiques explicites
Les règles du jeu du système doivent être écrites, visibles, partagées et comprises par tous. Sans règles claires, aucune amélioration objective n'est possible. Ces politiques définissent notamment les critères de passage d'une colonne à une autre (Definition of Done par étape) ou la gestion des urgences.

### Pratique 5 : Mettre en place des boucles de rétroaction (Feedback Loops)
Kanban utilise des réunions ritualisées (les Cadences) pour inspecter et ajuster le système à intervalles réguliers :

* Kanban Meeting (Quotidien, 10-15 min) : Point synchrone devant le tableau axé sur les blocages et le flux, et non sur le statut individuel de chacun.
* Replenishment Meeting (Hebdomadaire ou selon les besoins) : Sélection et engagement sur les prochaines tâches à intégrer dans le tableau depuis le backlog.
* Service Delivery Review (Bi-mensuel) : Analyse globale de la performance de livraison face aux attentes des clients.
* Operations Review (Mensuel) : Analyse des interdépendances entre les différentes équipes et services.

### Pratique 6 : Améliorer collaborativement, Évoluer scientifiquement
L'équipe utilise des modèles, des données statistiques et la méthode scientifique (hypothèse, test, mesure, conclusion) pour valider les changements de processus. L'amélioration continue se fait de manière collaborative.

---
## 4. Le Système Pull (Flux Tiré) vs Système Push (Flux Poussé)

* Système Push (Traditionnel) : Les tâches sont affectées aux collaborateurs dès qu'elles sont créées, surchargeant le système sans corrélation avec la capacité réelle de production.
* Système Pull (Kanban) : Une nouvelle tâche n'est introduite dans une colonne que lorsqu'une place se libère sous la limite de WIP définie, signalant une capacité disponible pour traiter le travail.

---
## 5. Classes de Service (Classes of Service)
Pour gérer les priorités au sein du flux, Kanban catégorise les tickets selon leur coût du délai (Cost of Delay) :

* Expedite (Urgence) : Tâche critique qui outrepasse temporairement les limites de WIP. Le coût de son retard est immédiat et colossal (ex: panne de serveur).
* Fixed Date (Date fixe) : Tâche liée à une échéance réglementaire ou commerciale stricte. Le coût du retard explose après une date précise.
* Standard : Tâche classique traitée selon l'ordre d'arrivée (FIFO). Le coût du retard augmente de manière linéaire.
* Intangible : Tâche nécessaire mais non urgente à court terme (ex: nettoyage technique). Le coût du retard est faible aujourd'hui mais très élevé à long terme.

---
## 6. Outils Technologiques et Physiques  

### Solutions Matérielles

* Tableau blanc physique avec ruban adhésif pour délimiter les colonnes.
* Notes repositionnables (Post-it) de différentes couleurs pour distinguer les types de travaux ou les classes de service.
* Gommettes de couleur pour signaler les blocages.

### Solutions Logicielles (Digitales)

* Jira Software : Idéal pour les configurations d'entreprise complexes, le suivi d'indicateurs avancés et la personnalisation fine des workflows.
* Kanbanize / Businessmap : Conçu spécifiquement pour le Kanban d'échelle, incluant la gestion de portefeuilles et des prévisions analytiques poussées.
* Trello : Solution minimaliste et visuelle, adaptée aux petites structures ou à la gestion de flux simples.
* Asana / Monday.com : Outils de gestion de travail généralistes proposant des vues Kanban robustes connectées à des calendriers et des portefeuilles.

---
## 7. Outils de Mesure et d'Analyse (Statistiques du Flux)

* Diagramme de Flux Cumulé (CFD - Cumulative Flow Diagram) : Graphique qui suit le volume total de travail dans chaque état au fil du temps. Il permet de repérer visuellement le WIP global, le Lead Time moyen et les goulots d'étranglement (élargissement d'une couleur sur le graphe).
* Graphique de Dispersion du Temps de Cycle (Cycle Time Scatterplot) : Graphique mesurant la durée exacte de traitement de chaque ticket terminé pour établir des prévisions probabilistes de livraison basées sur l'historique réel de l'équipe.

