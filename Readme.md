## Projet 3 : Déploiement d’une infrastructure d’identité hybride entre un Active Directory local et Microsoft Entra ID à l’aide de Microsoft Entra Connect

---

## I. Description du projet

<p>Ce projet consiste à mettre en place une infrastructure d’identité hybride en reliant un Active Directory local (mdf.local) à Microsoft Entra ID (anciennement Azure Active Directory).
L’objectif est de permettre la synchronisation automatique des utilisateurs entre l’annuaire local et le cloud, afin qu’ils puissent s’authentifier sur les services Microsoft (Azure, Office 365, Entra ID) avec leurs identifiants Active Directory.</p>

<p>Pour cela, le projet s’appuie sur l’installation et la configuration de Microsoft Entra Connect, un outil permettant de synchroniser les objets AD (utilisateurs, groupes, mots de passe) vers le tenant cloud JKferme.onmicrosoft.com.</p>

<p>Le travail inclut :</p>

<p>l’installation et la configuration d’un contrôleur de domaine local</p>

<p>la création et l’organisation des utilisateurs dans l’AD</p>

<p>l’installation de Microsoft Entra Connect</p>

<p>la configuration de la synchronisation (UPN, OU, ancre source, filtrage)</p>

<p>la validation de la synchronisation et des authentifications cloud</p>

<p>Ce projet reproduit une architecture moderne utilisée dans les entreprises pour centraliser la gestion des identités et faciliter l’accès aux services cloud.</p>

---

## II. Problématique

<p>Dans un contexte où les organisations utilisent de plus en plus de services cloud (Microsoft 365, Azure, applications SaaS), la gestion des identités devient un enjeu majeur.
Cependant, les utilisateurs sont souvent créés et gérés dans un Active Directory local, ce qui entraîne :</p>

<p>une duplication des comptes entre le local et le cloud</p>

<p>des mots de passe différents selon les services</p>

<p>une complexité de gestion pour l’administrateur</p>

<p>un risque accru d’erreurs et d’incohérences</p>

<p>une expérience utilisateur dégradée</p>

<p>La question centrale devient alors :</p>

<p>Comment assurer une gestion unifiée, cohérente et sécurisée des identités entre un Active Directory local et Microsoft Entra ID, tout en simplifiant l’authentification des utilisateurs ?</p>

---

## III. Objectifs

<p><b>Objectif principal :</b></p>
<p>Mettre en place une identité hybride permettant aux utilisateurs locaux de s’authentifier sur les services Microsoft Cloud grâce à leurs identifiants Active Directory.</p>

<p><b>Objectifs détaillés :</b></p>

<p><b>Synchronisation des utilisateurs :</b></p>
<p>Répliquer automatiquement les comptes AD locaux vers Microsoft Entra ID</p>
<p>Assurer la cohérence des identités entre le local et le cloud</p>

<p><b>Synchronisation du hachage des mots de passe :</b></p>
<p>Permettre aux utilisateurs d’utiliser le même mot de passe en local et dans le cloud</p>
<p>Simplifier l’expérience utilisateur</p>

<p><b>Authentification cloud :</b></p>
<p>Permettre la connexion au portail Azure / Office 365 avec les identifiants AD</p>
<p>Vérifier que les comptes synchronisés sont fonctionnels</p>

<p><b>Modernisation de l’infrastructure :</b></p>
<p>Utiliser ms-DS-ConsistencyGuid comme ancre source (méthode recommandée par Microsoft)</p>
<p>Préparer l’environnement pour des fonctionnalités avancées (MFA, Conditional Access, etc.)</p>

<p><b>Documentation et validation :</b></p>
<p>Produire des captures d’écran structurées</p>
<p>Rédiger un rapport de tests</p>
<p>Démontrer la maîtrise des outils d’administration.</p>

---

## III. Enjeux

<p><b>1. Enjeu de sécurité</b></p>
<p>Garantir une identité unique et fiable pour chaque utilisateur</p>
<p>Réduire les risques liés aux mots de passe multiples</p>
<p>S’appuyer sur les mécanismes de sécurité Microsoft (MFA, Conditional Access, etc.)</p>
<p>Préparer l’infrastructure à des politiques de sécurité modernes.</p>

<p><b>2. Enjeu de cohérence et de centralisation</b></p>
<p>Assurer une synchronisation automatique et continue des comptes</p>
<p>Éviter les doublons et les erreurs de gestion</p>
<p>Maintenir une base d’identité unique entre le local et le cloud</p>
<p>Faciliter l’administration quotidienne.</p>

<p><b>3. Enjeu d’expérience utilisateur</b></p>
<p>Permettre une authentification fluide avec un seul mot de passe</p>
<p>Simplifier l’accès aux services cloud</p>
<p>Réduire les demandes de support liées aux identifiants.</p>

<p>b>4. Enjeu de modernisation de l’infrastructure/b></p>
<p>Préparer l’entreprise à une transition vers le cloud</p>
<p>Mettre en place une architecture hybride moderne</p>
<p>Utiliser des standards actuels (ms-DS-ConsistencyGuid, Password Hash Sync)</p>
<p>Faciliter l’intégration future d’autres services Microsoft.</p>

<p><b>5. Enjeu organisationnel</b></p>
<p>Structurer les processus de création et gestion des comptes</p>
<p>Définir des modalités d’accompagnement pour les utilisateurs</p>
<p>Documenter les procédures pour assurer la continuité du service<p>

---

## IV. Etapes techniques du projet

<p><b>Étape 1 : Installation et configuration de l’Active Directory</b></p>
<p>Installation du rôle AD DS</p>
<p>Promotion du serveur en contrôleur de domaine</p>
<p>Création du domaine mdf.local</p>
<p>Création des OU et des utilisateurs</p>
<p>Vérification du DNS et de la résolution du domaine.</p>

<p><b>Étape 2 : Préparation du serveur pour Entra Connect</b></p>
<p>Installation des prérequis</p>
<p>Désactivation d’Internet Explorer Enhanced Security (IE ESC)</p>
<p>Vérification de la connectivité Internet</p>
<p>Test de résolution DNS (ping mdf.local)</p>

<p><b>Étape 3 : Installation de Microsoft Entra Connect</b></p>
<p>Téléchargement du package officiel</p>
<p>Installation en mode personnalisé</p>
<p>Connexion au tenant cloud JKferme.onmicrosoft.com</p>
<p>Validation des permissions administrateur</p>

<p><b>Étape 4 : Connexion de la forêt Active Directory</b></p>
<p>Ajout de la forêt mdf.local</p>
<p>Validation du compte mdf\Administrateur</p>
<p>Création automatique du compte de service AD</p>
<p>Vérification de la communication entre AD local et Entra Connect</p>

<p><b>Étape 5 : Configuration du mapping UPN</b></p>
<p>Détection du suffixe .local non routable</p>
<p>Activation de l’option Continuer sans faire correspondre tous les suffixes UPN</p>
<p>Attribution automatique du UPN cloud @jkferme.onmicrosoft.com</p>

<p><b>Étape 6 : Filtrage des domaines et des OU</b></p>
<p>Sélection du domaine mdf.local</p>
<p>Préparation du filtrage par OU (bonne pratique)</p>
<p>Synchronisation uniquement des objets nécessaires.</p>

<p><b>Étape 7 : Identification des utilisateurs</b></p>
<p>Choix de l’option : Les utilisateurs ne sont représentés qu’une fois</p>
<p>Utilisation de ms-DS-ConsistencyGuid comme ancre source</p>
<p>Configuration recommandée par Microsoft.</p>

<p><b>Étape 8 : Fonctionnalités facultatives</b></p>
<p>Activation de la synchronisation du hachage des mots de passe</p>
<p>Désactivation des options inutiles (writeback, Exchange, devices…)</p>

<p><b>Étape 9 — Lancement de la synchronisation</b></p>
<p>Création des connecteurs AD ↔ Entra ID</p>
<p>Démarrage automatique de la première synchronisation</p>
<p>Vérification dans le portail Entra : utilisateurs synchronisés, état de la synchronisation, absence d’erreurs.</p>

<p><b>Étape 10 — Tests et validation</b></p>
<p>Test de connexion d’un utilisateur synchronisé</p>
<p>Vérification de la présence des comptes dans Entra ID</p>
<p>Validation du bon fonctionnement du service</p>
<p>Documentation des résultats.</p>

---

## V. Réalisation


---

## VI. Analyses des compétences

<p>1. Des tests pertinents d’intégration et d’acceptation sont rédigés et effectués</p>

<p>Au cours du déploiement, plusieurs tests essentiels ont été réalisés pour valider l’intégration entre l’Active Directory local et Microsoft Entra ID :</p>

<p>Test de résolution DNS du domaine local (ping mdf.local)</p>
<p>Test de connectivité entre le serveur AD et Microsoft Entra</p>
<p>Validation du compte administrateur de la forêt AD</p>
<p>Vérification du mapping UPN et du suffixe non routable .local</p<
<p>Test de synchronisation initiale via Entra Connect</p>
<p>Vérification de l’apparition des utilisateurs synchronisés dans Entra ID</p>
<p>Test d’authentification d’un utilisateur synchronisé sur le portail Azure</p>

<p>Ces tests démontrent que l’intégration fonctionne correctement et que les utilisateurs locaux sont bien répliqués dans le cloud.</p>


<p><b>2. Les outils de test sont utilisés de manière appropriée</b></p>

<p>Les outils professionnels adaptés ont été mobilisés :</p>

<p>PowerShell pour tester la connectivité réseau et DNS</p>
<p>Active Directory Users and Computers pour vérifier les objets locaux</p>
<p>Microsoft Entra Connect Sync pour contrôler la synchronisation</p>
<p>Portail Microsoft Entra pour valider la présence et l’état des utilisateurs synchronisés</p>
<p>L’utilisation de ces outils montre une maîtrise des environnements hybrides et des méthodes de diagnostic.</p>


<p><b>3. Un rapport de test du service est produit</b></p>

<p>Les différentes étapes du déploiement ont été documentées :</p>

<p>Captures d’écran des configurations</p>
<p>Résultats des tests (DNS, connexion, synchronisation)</p>
<p>Validation finale de la synchronisation</p>
<p>Confirmation du bon fonctionnement du service</p>

<p>Ces éléments constituent un rapport de test complet, permettant de retracer l’ensemble du processus et de prouver la conformité du service.</p>


<p><b>4. Un support d’information est disponible</b></p>

<p>Un support d’information clair peut être fourni à partir du travail réalisé :</p>

<p>Documentation des étapes d’installation</p>
<p>Explication du fonctionnement de la synchronisation</p>
<p>Procédure pour ajouter un utilisateur AD et vérifier sa synchronisation</p>
<p>Informations sur les bonnes pratiques (UPN, filtrage des OU, sécurité)</p>

<p>Ce support facilite la compréhension et la prise en main du service par un tiers.</p>


<p>5. Les modalités d’accompagnement sont définies</p>

<p>Le service déployé inclut des modalités d’accompagnement pour les utilisateurs :</p>

<p>Création d’un compte AD local</p>
<p>Synchronisation automatique vers Microsoft Entra ID</p>
<p>Connexion possible au portail Azure avec les identifiants locaux</p>
<p>Possibilité d’étendre la configuration (MFA, groupes, writeback, etc.)</p>

<p>Ces modalités garantissent une transition fluide pour les utilisateurs et une gestion simplifiée pour l’administrateur.</p>


<p>6. Le service déployé est opérationnel et donne satisfaction à l’utilisateur</p>

<p>La synchronisation a été validée comme fonctionnelle :</p>

<p>La configuration Entra Connect s’est terminée sans erreur</p>
<p>Les utilisateurs AD apparaissent correctement dans Entra ID</p>
<p>Le hachage des mots de passe est synchronisé</p>
<p>L’authentification cloud fonctionne</p>
<p>Le service est stable et exploitable immédiatement</p>
<p>Le résultat final répond aux besoins du projet et satisfait les exigences d’un environnement hybride moderne.</p>

---

## VII. Conclusion

<p>Le travail réalisé démontre une maîtrise complète du déploiement d’un service d’identité hybride, incluant installation, configuration, tests, validation, documentation et mise en production.</p>
<p>Toutes les compétences demandées sont pleinement validées.</p>
