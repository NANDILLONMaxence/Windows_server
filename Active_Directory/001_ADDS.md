# Guide pour Créer un Domaine Active Directory sur Windows Server

## Introduction
Ce guide vous aidera à configurer un domaine Active Directory sur un serveur Windows. Active Directory est un service de gestion des identités et des accès, largement utilisé dans les environnements d'entreprise pour gérer les utilisateurs, les ordinateurs et les ressources réseau.

---

## Étapes

### Étape 1 : Installation du rôle Active Directory Domain Services (AD DS)

1. Ouvrez le **Gestionnaire de serveur**.
2. Cliquez sur **Gérer** dans le coin supérieur droit, puis sélectionnez **Ajouter des rôles et des fonctionnalités**.
3. Cochez **Installation basée sur un rôle ou une fonctionnalité** puis **Suivant**.
4. Sélectionnez **un serveur du pool de serveur** et le serveur ou vous voulez installer ADDS.
5. Cliquez sur **Suivant** jusqu'à la page **Sélection des rôles de serveur**.
6. Cochez la case à côté de **Services AD DS**.
7. Cliquez sur **Suivant** et suivez les instructions pour terminer l'installation du rôle.

### Étape 2 : Configuration du domaine

1. Une fois le rôle installé, vous verrez une notification pour **Configurer AD DS**. Cliquez sur cette notification ou ouvrez **Gérer** > **Ajouter des rôles et des fonctionnalités** > **Services AD DS** > **Configurer**.
2. Choisissez **Ajouter une nouvelle forêt**.
3. Entrez le nom de domaine de votre choix, par exemple : `mondomaine.org`.
4. Configurez le niveau fonctionnel de la forêt et du domaine selon vos besoins (par défaut est généralement recommandé).
5. Cochez dans Spécifier les fonctionnalités de contrôleur de domaine : **Serveur DNS** et **Catalogue global**.
6. Définissez le mot de passe pour le mode de restauration de service d'annuaire (DSRM).
7. Sélectionnez les options de réplication DNS appropriées **Suivant**.
8. Configurez le chemin d'accès pour la base de données AD DS et les fichiers journaux.
9. Cliquez sur **Suivant** et suivez les instructions pour terminer la configuration.

### Étape 3 : Redémarrage du serveur

1. Une fois la configuration terminée, redémarrez votre serveur pour appliquer les changements.

---

## Vérification du domaine

### Vérifier l'installation d'Active Directory

1. Après le redémarrage, ouvrez **Gestionnaire de serveur**.
2. Cliquez sur **Outils** dans le coin supérieur droit, puis sélectionnez **Utilisateurs et ordinateurs Active Directory**.
3. Assurez-vous que vous pouvez voir les **Domaines** et les **Utilisateurs** dans la console.

### Tester la connectivité du domaine

1. À partir d'un autre ordinateur sur le réseau, ouvrez une fenêtre de commande.
2. Tapez `ping mondomaine.org` (remplacez `mondomaine.org` par votre nom de domaine).
3. Vous devriez voir des réponses indiquant que la résolution DNS fonctionne.

### Créer un nouvel utilisateur

1. Dans **Utilisateurs et ordinateurs Active Directory**, cliquez avec le bouton droit sur **Utilisateurs**.
2. Sélectionnez **Nouveau** > **Utilisateur**.
3. Suivez les instructions pour créer un nouvel utilisateur dans votre domaine.

---

Vous avez maintenant configuré avec succès un domaine Active Directory sur votre serveur Windows. N'hésitez pas à ajouter des détails supplémentaires ou des instructions spécifiques selon vos besoins.

--- 