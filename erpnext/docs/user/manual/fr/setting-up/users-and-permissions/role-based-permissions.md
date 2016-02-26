# Les permissions basées sur les rôles

ERPNext a des permissions basées sur les rôles. Cela signifie que vous pouvez assigner des rôles à des utlisateurs puis
definir des permissions sur ces roles. La structure des permissions permet de définir différentes permissions pour chaque
champs en utilisant un concept appelé **niveau de permission** d'un champ. Une fois que les rôles sont assignés à un utilisateur,
cela donne la possibilité de limiter l'acces à des documents spécifiques.


Pour commencer, rendez-vous sur:
> Setup > Permissions > Role Permissions Manager

<img alt="Manage Read, Write, Create, Submit, Amend access using the Role Permissions Manager" class="screenshot" src="{{docs_base_url}}/assets/img/users-and-permissions/setting-up-permissions-leave-application.png">

Les permissions sont appliquées par une combinaison de :

  * **Roles:** Comme vu précédemment, des rôles sont assignés aux utilisateurs, et des permissions sont données à ces rôles.

  *Reponsable des ventes, Employé, Employé des ressources humaines sont des exemples de rôles*

  * **Types de documents:** Chaque type de document transaction, possède sa propre liste de permissions basée sur les rôles.

  *Une facture, une demande d'autorisation, une entrée de stock etc. sont des types de documents.*

  * **Niveaux de permissions:** Pour chaque document, vous pouvez regrouper les champs par niveaux. Chaque groupe de champs 
  est noté avec un numéro unique (0, 1, 2, 3, etc.). Une liste de permission spécifique peut être appliquée sur chaque groupe de champs. 
  Par défaut tous les champs sont au niveau 0.

    *Le niveau de permission relie le groupe de champs qui ont le niveau X avec une règle niveau X.*

  * **Etats du document:** Les permissions sont appliquées sur chaque état du document comme la création, la sauvegarde, la soumission, l'annulation, la modification. 
  Un rôle peut être autorisé à imprimer, envoyer par email, exporter/importer des données, accéder aux rapports ou definir des permissions pour les utilisateurs.

  * **Appliquer les permissions des utilisateurs:** Cet interrupteur détermine si les permissions de l'utiilisateur doivent être 
  appliquées pour le rôle sur les états du document selectionné.

	Si c'est activé, un utilisateur avec ce rôle pourra accéder à des documents de ce type. En plus de cela, les autorisations définies pour d'autres types de documents seront appliquées si elles sont en lien avec des champs de ce type de document.

	Pour configurer des permissions utilisateurs:
    > Setup > Permissions > [User Permissions Manager]({{docs_base_url}}/user/manual/fr/setting-up/users-and-permissions/user-permissions.html)

---

**Ajouter une nouvelle règle**, cliquez sur le bouton "Add a New Rule", une pop-up vous demandera de séléctionner le rôle ainsi que le niveau de permission. Une fois selectionnés, cliquez sur "Add", la nouvelle règle sera ajoutée aux autres.

---

L'application de demande de congès est un bon **exemple** qui utilise toutes les notions de permissions.

<img class="screenshot" alt="Leave Application Form should be created by an Employee, and approved by Leave Approver or HR User" src="{{docs_base_url}}/assets/img/users-and-permissions/setting-up-permissions-leave-application-form.png">

   1. **La demande doit être créée par un employé.**
     Pour cela, l'employé doit avoir l'autorisation de lire, écrire et créer.

<img class="screenshot" alt="Giving Read, Write and Create Permissions to Employee for Leave Application"  src="{{docs_base_url}}/assets/img/users-and-permissions/setting-up-permissions-employee-role.png">

   1. **Un employé ne doit pouvoir accéder qu'à ses demandes uniquement.**
     Hence, Apply User Permissions should be enabled for Employee Role, and a User Permission record should be created for each User Employee combination. (This effort is reduced for Employee Document Type, by programmatically creating User Permission records.)

<img class="screenshot" alt="Limiting access to Leave Applications for a user with Employee Role via User Permissions Manager" src="{{docs_base_url}}/assets/old_images/erpnext/setting-up-permissions-employee-user-permissions.png">

   1. **Le responsable des ressources humaines doit-être capable de voir toutes les demandes.**
     Créez une permissions pour le responsable des ressources humaines au niveau 0, avec la permission de lire. 
     L'option "Apply User Permissions"doit être désactivée.

<img class="screenshot" alt="Giving Submit and Cancel permissions to HR Manager for Leave Applications. 'Apply User Permissions' is unchecked to give full access." src="{{docs_base_url}}/assets/img/users-and-permissions/setting-up-permissions-hr-manager-role.png">

   2. **L'approbateur doit être capable de voir et de mettre à jour ses demandes de congés.**
     L'approbateur a un accés en lecture et écriture au niveau 0 avec l'option "User Permissions" cochée. Relevant Employee 
     Documents should be enlisted in the User Permissions of Leave Approvers. (This effort is reduced for Leave Approvers 
     mentioned in Employee Documents, by programmatically creating User Permission records.)

<img class="screenshot" alt="Giving Read, Write and Submit permissions to Leave Approver for Leave Applications.'Apply User Permissions' is checked to limit access based on Employee." src="{{docs_base_url}}/assets/img/users-and-permissions/setting-up-permissions-leave-approver-role.png">

   3. **La demande doit être approuvée / rejetée uniquement par l'utilisateur des ressources humaines ou l'approbateur de demandes.**
     Le champs de statut de la demande de congés est définit au niveau 1. L'utilisateur des ressources humaines et l'approbateur 
     des demandes de congés ont les permissions en lecture et écriture au niveau 1 alors que les autres utilisateurs auront
     seulement la permission en lecture au niveau 1.

<img class="screenshot" alt="Limiting read access for a set of fields to certain Roles" src="{{docs_base_url}}/assets/old_images/erpnext/setting-up-permissions-level-1.png">


   4. **L'utulisateur des ressources humaines doit être capable de déléguer les demandes à ses collègues.**
     L'utilisateur des ressources humaines à le droit d'affecter des permissions aux utilisateurs. Un utilisateur avec le rôle "HR"
     doit être capable de définir des permissions sur les demandes de congés pour les autres utilisateurs.      

<img class="screenshot" alt="Let HR User delegate access to Leave Applications by checking 'Set User Permissions'. This will allow HR User to access User Permissions Manager for 'Leave Application'" src="{{docs_base_url}}/assets/img/users-and-permissions/setting-up-permissions-hr-user-role.png">

{next}
