# Spécifications fonctionnelles – Analyse de l’insertion professionnelle des étudiants

## 1. Présentation du projet

Ce projet vise à mettre en place un dispositif structuré et pérenne d’enquêtes d’insertion professionnelle pour suivre l’intégration des diplômés du réseau **Compétences & Développement (C&D)** sur le marché du travail.

Il permet de collecter, centraliser et analyser des données fiables sur les parcours professionnels, les situations d’emploi et les caractéristiques des postes occupés. Les résultats contribuent à évaluer l’adéquation entre les formations et les besoins du marché de l’emploi, ainsi qu’à accompagner les décisions stratégiques et l’amélioration continue des formations.

## 2. Objectifs métier

L’objectif général est d’automatiser le processus d’enquête, de la collecte des réponses jusqu’à leur restitution dans des tableaux de bord décisionnels.

Les objectifs spécifiques sont :

- **O1 – Formulaires :** concevoir et mettre à disposition 100 % des formulaires nécessaires.
- **O2 – Diffusion :** automatiser l’envoi des questionnaires à 100 % des étudiants éligibles.
- **O3 – Collecte :** réceptionner et enregistrer correctement au moins 95 % des réponses soumises.
- **O4 – Qualité :** garantir au moins 95 % de données conformes et exploitables.
- **O5 – Reporting :** rendre disponibles 100 % des indicateurs prioritaires dans les tableaux de bord.
- **O6 – Pilotage :** couvrir 100 % des besoins analytiques prioritaires des responsables métiers et pédagogiques.

## 3. Périmètre fonctionnel et processus

Le dispositif couvre six étapes principales :

1. **Préparation des données de référence :** extraction des données d’inscription, contrôle des informations étudiants et transfert depuis IGOR vers une base SQL Server dédiée.
2. **Conception des formulaires :** définition des questionnaires, des questions et des axes d’analyse, puis association aux populations concernées.
3. **Automatisation des enquêtes :** envoi des formulaires, suivi des réponses, relances et réception automatisée des soumissions.
4. **Centralisation :** stockage des réponses dans une base dédiée et rapprochement avec les données de référence.
5. **Transformation et préparation :** nettoyage, normalisation, contrôles qualité et préparation des indicateurs analytiques.
6. **Reporting :** création de tableaux de bord Power BI interactifs adaptés aux besoins de pilotage.

## 4. Indicateurs clés de performance (KPI)

Les indicateurs suivis dans les tableaux de bord comprennent :

| KPI | Définition / règle de calcul | Cible |
|---|---|---:|
| Total des réponses | Nombre de questionnaires remplis et validés | Suivi évolutif |
| Total des notifications | Nombre d’invitations et de relances envoyées | Suivi évolutif |
| Taux de réponse | Réponses / notifications uniques × 100 | ≥ 70 % |
| Total des étudiants employés | Nombre de répondants déclarant être en activité | À définir |
| Total des étudiants non employés | Nombre de répondants déclarant être en recherche d’emploi | 0 % (objectif théorique) |
| Situation non connue | Étudiants ciblés − réponses valides | ≤ 30 % |
| Taux de chômage | Non employés / (employés + non employés) × 100 | < 10 % |
| Taux d’employabilité | Employés / (employés + non employés) × 100 | ≥ 85 % |

*Les cibles sont indicatives et peuvent être ajustées selon les résultats des campagnes et les standards retenus par le Groupe.*

## 5. Architecture des données et sources

### Sources de données

| Source | Description | Accès |
|---|---|---|
| IGOR – SQL Server | Données d’inscription, étudiants, formations et axes analytiques | Lecture selon autorisations |
| Base SQL Server Data Analytics | Données centralisées et préparées pour l’analyse | Lecture et écriture contrôlées |

Les données de référence sont extraites depuis IGOR et transférées vers la base analytique dédiée, selon une fréquence définie par les besoins du projet.

### Qualité des données

Les contrôles portent sur six dimensions :

- **Complétude :** présence des informations obligatoires, notamment les adresses e-mail et les axes analytiques.
- **Exactitude :** validité et bonne association des coordonnées des étudiants.
- **Cohérence :** concordance entre inscriptions, formations et données analytiques.
- **Unicité :** identification unique des enquêtes et contrôle des doublons.
- **Fraîcheur :** actualisation des données selon une fréquence documentée.
- **Traçabilité :** documentation des sources, des autorisations et des traitements.

## 6. Règles de gestion

| ID | Règle | Description | Statut |
|---|---|---|---|
| RG-DEF-001 | Éligibilité | Un étudiant doit être inscrit dans IGOR, rattaché à une période de formation concernée et disposer des informations nécessaires à l’envoi. | En revue |
| RG-CAL-001 | Taux de réponse | Calculé à partir des destinataires ayant répondu valablement parmi ceux ayant effectivement reçu le formulaire. | En revue |
| RG-PER-001 | Périmètre | Les étudiants, marques et périodes inclus dans la campagne sont retenus ; les populations non éligibles et campagnes annulées sont exclues. | En revue |
| RG-QUA-001 | Qualité | Les identifiants, périodes de formation et adresses e-mail sont contrôlés avant l’envoi. | Brouillon |
| RG-EXC-001 | Anomalies | Les données manquantes, réponses non associées et doublons sont signalés et vérifiés avant réintégration. | Brouillon |
| RG-TMP-001 | Temporalité | Envoi initial à J+6M, puis relances à J+7M et J+8M après la fin de période de formation. Aucune relance après réponse valide ou clôture. | Brouillon |
| RG-SEC-001 | Sécurité | Les accès aux données nominatives et aux résultats sont limités selon les rôles et périmètres autorisés. | Brouillon |

## 7. Valeur ajoutée du projet

Le dispositif met à disposition un référentiel d’indicateurs et des tableaux de bord interactifs permettant notamment de :

- Suivre les taux d’emploi, de chômage et d’insertion professionnelle.
- Comparer les résultats par établissement, marque, programme et promotion.
- Analyser les délais d’accès au premier emploi et les périodes de recherche.
- Étudier les statuts professionnels, contrats et niveaux de responsabilité.
- Identifier les entreprises employeuses et leur répartition géographique.
- Analyser les métiers, secteurs et sous-secteurs d’activité.
- Suivre les niveaux de rémunération.
- Étudier l’adéquation entre formations, compétences et emplois occupés.
- Comparer les évolutions entre promotions et établissements.
- Accompagner le pilotage stratégique et l’amélioration continue des formations.

---

**Projet :** Analyse de l’insertion professionnelle des étudiants  
**Organisation :** Groupe Compétences & Développement  
**Outil de reporting :** Microsoft Power BI
