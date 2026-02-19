## Projet 3 : Sauvegarde Azure Active Directory

---

## I. Introduction

<p>Dans les environnements professionnels modernes, la gestion des identités repose de plus en plus sur des solutions cloud telles qu’Azure Active Directory (désormais Microsoft Entra ID). Ces plateformes centralisent l’authentification, les accès et les rôles des utilisateurs. Cependant, malgré leur robustesse, elles ne dispensent pas les organisations de mettre en place des mécanismes de sauvegarde et d’export des comptes utilisateurs afin de garantir la continuité d’activité, la conformité et la traçabilité.</p>

<p>Ce projet consiste à automatiser la sauvegarde des utilisateurs Azure AD en utilisant PowerShell et les modules Microsoft Graph. L’objectif est de créer un export régulier et sécurisé des comptes, incluant leurs attributs essentiels, leurs groupes et leurs rôles.</p>

---

## II. Problématique

<p>Dans Azure AD, les identités sont critiques : elles conditionnent l’accès aux ressources, aux applications et aux données de l’entreprise. En cas de mauvaise manipulation, de suppression accidentelle, d’erreur humaine ou d’incident de sécurité, la perte d’informations sur les utilisateurs peut avoir des conséquences majeures.</p>

<p>Problématique :  Comment mettre en place une solution automatisée permettant de sauvegarder régulièrement les utilisateurs Azure Active Directory, afin de garantir la continuité de service, la conformité et la traçabilité des identités ?</p>

---

## III. Objectifs

<p><b>1. Se connecter à Azure AD via PowerShell / Microsoft Graph</b></p>
<p>Installer les modules nécessaires</p>
<p>Authentifier un administrateur</p>
<p>Accéder aux informations des utilisateurs.</p>

<p><b>2. Exporter les utilisateurs Azure AD</b></p>
<p>Récupérer les attributs essentiels :</p>
<p>DisplayName</p>
<p>UserPrincipalName</p>
<p>Mail</p>
<p>Department</p>
<p>AccountEnabled</p>
<p>Date de création</p>
<p>Exporter au format CSV ou JSON.</p>

<p><b>3. Sauvegarder les groupes et rôles</b></p>
<p>Lister les groupes auxquels chaque utilisateur appartient</p>
<p>Exporter les rôles Azure AD (administrateurs, lecteurs, etc.)</p>

<p><b>4. Automatiser la sauvegarde</b></p>
<p>Planifier l’exécution du script (Task Scheduler ou Azure Automation)</p>
<p>Générer un fichier horodaté</p>
<p>Stocker la sauvegarde dans un dossier sécurisé ou un stockage cloud.</p>

<p><b>5. Sécuriser le processus</b></p>
<p>Utiliser une authentification moderne (MSAL / Graph)</p>
<p>Protéger les identifiants</p>
<p>Limiter les permissions du script.</p>

---

## III. Enjeux

<p><b>Sécurité :</b></p>
<p>Prévenir la perte d’identités en cas de suppression accidentelle</p>
<p>Garantir la disponibilité des informations critiques</p>
<p>Réduire les risques liés aux erreurs humaines.</p>

<p><b>Conformité :</b></p>
<p>Répondre aux exigences RGPD, ISO 27001, ANSSI</p>
<p>Conserver une trace des comptes et de leurs rôles</p>
<p>Faciliter les audits internes et externes.</p>

<p><b>Organisation :</b></p>
Centraliser les sauvegardes des identités</p>
<p>Faciliter la gestion des comptes lors des mouvements RH</p>
<p>Documenter l’état du tenant Azure AD.</p>

<p><b>Opérationnel :</b></p>
<p>Automatiser les exports pour gagner du temps</p>
<p>Standardiser la gestion des identités</p>
<p>Réduire les interventions manuelles.</p>

---

IV. Contexte d'intervention

Dans le cadre de la gestion des identités cloud, une procédure d’intervention a été réalisée :

<p>1. Installation et configuration des modules PowerShell Microsoft Graph</p>

<p>2. Connexion au tenant Azure AD</p>

<p>3. Extraction des utilisateurs et de leurs attributs</p>

<p>4. Export des groupes et rôles associés</p>

<p>5. Automatisation de la sauvegarde via une tâche planifiée</p>

<p>Vérification de la conformité des sauvegardes</p>

<p>Documentation du processus</p>

---

V. Réalisation


---

VI. Conclusion
