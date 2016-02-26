# Permissions utilisateur

Limite l'accès for un utilisateur à un ensemble de documents en utilisant le gestionnaire de permissions.

Les permissions de rôle définissent les actions possible par les utilisateurs d'un rôle sur des types de documents. Vous 
pouvez toutefois definir des permissions plus fines en définissant des permissions "utilisateur". En configurant des
documents sépcifiques dans la liste des permissions de l'utilisateur, vous pouvez limiter l'accès à des documents spécifiques
for cet utilisateurs à la condition que l'option "Apply User Permissions" est cochée dans le gestionnaire des persmissions du rôle.

Pour commencer, rendez-vous sur:
> Setup > Permissions > User Permissions Manager

<figure>
	<img src="{{docs_base_url}}/assets/img/users-and-permissions/user-permissions-company.png"
		class="img-responsive" alt="User Permissions Manager">
	<figcaption>Le gestionnaire de permissions "utilisateur" montre comment les utilisateurs peuvent accéder à une entreprise spécifique.</figcaption>
</figure>

#### Exemple

L'utilisateur 'aromn@example.com' a un rôle "Vendeur" mais nous voulons limiter l'accès aux enregistrements pour l'entreprise 'Wind Power LLC' uniquement.

  1. Nous ajoutons la permission "utilisateur" pour l'entreprise.
	<figure>
		<img src="{{docs_base_url}}/assets/img/users-and-permissions/user-permission-user-limited-by-company.png"
			class="img-responsive" alt="User Permissions For Company">
		<figcaption>Ajout d'une permission "utilisateur" pour combinaison de l'utilisateur 'aromn@example.com' et l'entreprise 'Wind Power LLC'.</figcaption>
	</figure>

  1. Aussi, le rôle "All" n'a que la permission de lire for l'entreprise, avec l'option 'Apply User Permissions' cochée.
	<figure>
		<img src="{{docs_base_url}}/assets/img/users-and-permissions/user-permissions-company-role-all.png"
			class="img-responsive" alt="Role Permissions for All on Company">
		<figcaption>Permission de lecture avec l'option "Apply User Permissions" de cochée pour le type de document "Company".</figcaption>
	</figure>

  1. L'effet combiné des deux règles ci-dessus amène l'utilisateur 'aromn@example.com' a n'avoir un accès en lecture pour l'entreprise 'Wind Power LLC' uniquement.
	<figure>
		<img src="{{docs_base_url}}/assets/img/users-and-permissions/user-permissions-company-wind-power-llc.png"
			class="img-responsive" alt="Effect of Role and User Permissions on Company">
		<figcaption>L'accès est limité pour l'entreprise 'Wind Power LLC'.</figcaption>
	</figure>

  1. Nous voulons que cette permission sur l'utilisateur soit appliquée à d'autres documents comme les devis, les bons de commandes, etc.
Ces formulaires ont un **un champ de liaison avec l'entreprise**. En conséquence, les permissions de l'utilisateur sur 
l'entreprise sont aussi appliqués sur ces documents ce qui permet à l'utilisateur 'aromn@example.com' d'accéder aux documents
de l'entreprise 'Wind Power LLC'.
	<figure>
		<img src="{{docs_base_url}}/assets/img/users-and-permissions/user-permissions-quotation-sales-user.png"
			class="img-responsive" alt="Sales User Role Permissions for Quotation">
		<figcaption>Les utilisateurs avec le rôle "vendeur" peuvent lire, écrire, créer et annuler des Devis
		en se basant sur les permissions "utilisateur" parce que l'option 'Apply User Permissions' est cochée.</figcaption>
	</figure>
	<figure>
		<img src="{{docs_base_url}}/assets/old_images/erpnext/user-permissions-quotation-list.png"
			class="img-responsive" alt="Quotation List limited to results for Company 'Wind Power LLC'">
		<figcaption>La liste des devis est limitéé aux résulats pour l'entreprise 'Wind Power LLC' et l'utilisateur 'aromn@example.com'.</figcaption>
	</figure>

  1. Les permissions "utilisateur" sont appliquées automatiquement en se basant sur les champs de jointure, comme nous l'avons vu pour les devis. 
  Mais, le formulaire de Piste à 4 champs de jointure: le territoire, l'entreprise, le propriétaire de la piste et le prochain contact. 
  Admettons que vous vouliez limiter l'accès des Leads aux utulisateurs en se basant uniquement sur le territoire, meme si vous avez défini des permissions pour les types de documents Utilisateur, Territoire et Entreprise. 
  Vous pouvez le faire simplement en configurant 'Ignore User Permissions' pour les champs de jointure: Entreprise, proprietaire de la piste et le prochain contact.
	<figure>
		<img src="{{docs_base_url}}/assets/img/users-and-permissions/user-permissions-lead-role-permissions.png"
			class="img-responsive" alt="Role Permissions on Lead for Sales User Role">
		<figcaption>Les vendeurs veuvent lire, modifier et créer des Pistes selon les permissions "utilisateur"</figcaption>
	</figure>
	<figure>
		<img src="{{docs_base_url}}/assets/img/users-and-permissions/user-permissions-ignore-user-permissions.png"
			class="img-responsive" alt="Set Ingore User Permissions from Setup > Customize > Customize Form">
		<figcaption>Cochez 'Ignore User Permissions' pour les champs "entreprise", "Proprietaire de la piste" et "prochain contact"
		via Setup > Customize > Customize Form for Lead.</figcaption>
	</figure>
	<figure>
		<img src="{{docs_base_url}}/assets/old_images/erpnext/user-permissions-lead-based-on-territory.png"
			class="img-responsive" alt="Lead List is limited to records with Territory 'United States'">
		<figcaption>Par l'effet des combinaisons précédentes, l'utilisateur 'aromn@example.com' ne peut accéder aux pistes du territoire 'United States' uniquement.</figcaption>
	</figure>

{suite}

