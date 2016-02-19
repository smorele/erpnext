Avant de commencer l'implémentation, familiarisons nous avec la terminologie utilisée et quelques concept d'ERPNext.

* * *

### Concepts de base

#### Compagnie

Représente l'entreprise pour laquelle ERPNext est configuré. Avec la même configuration, vous pouvez créer plusieurs 
enregistrements de compagnie chacune représentant une entité légale. La comptabilité de chaque compagnie va être différente
mais elles partageront les mêmes client, fournisseurs et enregistrement@.

> Setup > Company

#### Client

Représente un client. Un client peut etre où un individu ou une organisation.
Vous pouvez créer de multiples contacts et adresses pour chaque client.

> Selling > Customer

#### Fournisseur

Représente un fournisseur de biens ou de services. Votre compagnie de téléphone est un fournisseur, donc il est votre 
fournisseur de matières premieres. Ici encore, un fournisseur peut être où un individu ou une organisation et avoir 
plusieurs contacts et adresses.

> Buying > Supplier

#### Produit

Un produit, un sous-produit ou un service qui peut être vendu, acheté, fabriqué, ou simplement identifié.

> Stock > Item

#### Compte

Un compte est une rubrique dans laquelle les transactions financières et commerciales sont
exploitée. Par exemple, “frais de voyage” est un compte, “client Zoe”,
“fournisseur Mae” sont des comptes. ERPNext créer des comptes pour les clients et les fournisseurs automatiquement.

> Accounts > Chart of Accounts

#### Adresse

Une adresse représente le détail d'emplacement d'un client ou d'un fournisseur. Elles peuvent être différents comme par 
exemple pour le bureau, l'usine, l'entrepot, le magasin, etc.

> Selling > Address

#### Contact

Un contact appartient à un client, un fournisseur ou est indépendant. Un contact a un nom et des coordonnées comme 
l'email et le numéro de téléphone.

> Selling > Contact

#### Communication

Une liste de toutes les échanges avec un contact ou un prospect. Tous les emails envoyés depuis le systeme sont ajoutés
au tableau de communication.

> Support > Communication

#### Liste de prix

Une liste de prix est l'endroit où sont stockés les différentes tarifications. C'est un nom donné à un ensemble de prix de produits
stockés dans une liste particulière.

> Selling > Price List


> Buying > Price List

* * *

### Comptabilité

#### Année fiscale

Représente une année fiscale ou une année compatable. Vous pouvez utiliser plusieurs années fiscales en même temps. Chaque
année fiscala a une date de départ et une date de fin et les transactions peuvent être enregistrées seulement dans cette 
période. Quand vous fermez une année fiscale les soldes sont transférés dans les soldes "d'ouverture" de la prochaine année
fiscale.

> Setup > Company > Fiscal Year

#### Centre de coût

Un centre de coût est comme un compte, mais la seule différence c'est que la structure réprésente au plus près votre 
entreprise.
Par exemple, dans le plan comptable, vous pouvez séparer vos dépenses par leurs types (voyage, marketing, etc.). Dans
le centre de coût, vous pouvez les séparer par produit ou group (vente en ligne, vente au détail, etc.)

> Accounts > Chart of Cost Centers

#### Journal des écritures

Un document qui contient les entrées du Grand Livre (GL) ainsi que la somme des débits et des credits de ces entrées. Dans 
ERPNext vous pouvez mettre à jour les paiements, les retours, etc., en utilisant les entrées de ce journal.

> Accounts > Journal Entry

#### Facture de vente

Une facture envoyée aux clients pour la livraison d'articles achetés (produits ou services).

> Accounts > Sales Invoice

#### Facture d'achat

Une facture envoyée par le fournisseur pour la livraison des produits commandés (produits ou services).

> Accounts > Purchase Invoice

#### Devise

ERPNext vous permet d'enregistrer des transactions dans plusieurs devises. Il n'y a qu'une seule devise pour votre livre 
de comptes. Si vous entrez vos factures avec des paiements dans différentes devises, le montant en fonction du taux
de conversion indiqué dans la devise est converti.

> Setup > Currency

* * *

### Vente

#### Groupe de clients

Une classification des clients, en général basée sur un segment de marché.

> Selling > Setup > Customer Group

#### Piste

Une personne qui peut être une future source d'affaires. Une piste peut générer des opprtunités. (de: “peut conduire à une vente”).

> Selling > Lead

#### Opportunité

Une potentielle vente. (de: “opportunité pour une affaire”).

> Selling > Opportunity

#### Commande client

un document qui valide les terme de la livraison et le prix d'un article (produit ou service) par le client. Les 
livraisons, les ordres de production et les factures sont créées.

> Selling > Sales Order

#### Territoire

Une classification des zones géographiques pour la gestion des ventes. Vous pouvez définir des cibles pour les 
térritoires et chaque vente est liée au térritoire.

> Selling > Setup > Territory

#### Patenaire

Un tiers ou un revendeur qui vend les produits d'une compagnie en échange d'une commission.

> Selling > Setup > Sales Partner

#### Vendeur

Personne qui négocie avec les clients et finalise les ventes. Vous pouvez definir des objectifs pour les vendeurs et 
les marquer dans les transactions.

> Selling > Setup > Sales Person

* * *

### Achat

#### Ordre d'achat

Un contrat donné à un fournisseur pour livrer les produits dont les coûts, quantités, dates et autres conditions 
sont définis.

> Buying > Purchase Order

#### Demande de materiel

Une demande faite par un utilisateur ou automatiquement générée par ERPNext basée sur les niveaux de commande ou une estimation
de la quantité de produits requise pour une production.

> Buying > Material Request

* * *

### Stock (Inventaire)

#### Entrepot

Un entrepot logistique ou l'on stocke les produits.

> Stock > Warehouse

#### Mouvement de stock

Transfert de materiel depuis un entrepot, vers un ou plusieurs entrepots.

> Stock > Stock Entry

#### Bordereau de livraison

Une liste d'éléments avec des quantités pour la livraison au client. Une livraison réduit la quantité de stock d'un 
article dans l'entrepôt, à partir duquel il est expédié. Une livraison est généralement créé pour une commande client.

> Stock > Delivery Note

#### Bordereau de vente

Une note indiquant qu'une certaine quantité d'articles a été reçu d'un fournisseur, le plus souvent en association 
avec un bon d'achat.

> Stock > Purchase Receipt

#### Numéro de série

Un numéro unique donnée à une unité ou un un article.

> Stock > Serial Number

#### Lot

Un numéro donné à un groupe d'article achétés ou produits.

> Stock > Batch

#### Stock livré

Un tableau qui représente tous les mouvements d'articles d'un entrepot vers un autre. Ce tableau est mis à jour quand
une entrée de stock, un bordereau de livraison, une reception ou une facture de vente sont faits.

#### Rapprochement de stock

Mise à jour de stock pour plusieurs produits à partir d'un tableur (CSV).

> Stock > Stock Reconciliation

#### Contrôle de qualité

Un document préparer pour enregistrer certains paramètres d'un produit au moment de la reception d'un fournisseur ou la
livraison à un client

> Stock > Quality Inspection

#### Groupe d'articles

Classification d'un article.

> Stock > Setup > Item Group

* * *

### Ressources humaines

#### Employé

Enregistrement d'une personne qui est ou a été dans les effectifs de l'entreprise.

> Human Resources > Employee

#### Demande de congé

Enregistrement d'une demande de congé, approuvée ou non.

> Human Resource > Leave Application

#### Type de congé

Un type de congé (ex., congé maladie, congé maternité, etc.).

> Human Resource > Leave and Attendance > Leave Type

#### Gestion des paies

Un outil qui aide à la création de bulletins de paie pour les salariés.

> Human Resource > Salary and Payroll > Process Payroll

#### Bulletin de paie

Enregistrement du salaire mensuel d'un employé.

> Human Resource > Salary Slip

#### Structure du salaire

Un modèle de définition des composants du salaire d'un employé comme les taxes ou autres déductions de la sécurité sociale. 

> Human Resource > Salary and Payroll > Salary Structure

#### Evaluation

Enregistrement de la performance d'un employé sur une période bassée sur certains critères.

> Human Resources > Appraisal

#### Modèle d'évaluation

Un modèle qui présente les différents paramètres pris en compte dans l'évaluation de la performance d'un employé et leur 
coéfficient pour un rôle particulier.

> Human Resources > Employee Setup > Appraisal Template

#### Présence

Enregistrement qui indique la présence ou l'absence d'un employé pour un jour donné.

> Human Resources > Attendance

* * *

### Fabrication

#### Numenclature

Une liste des opération et des produits avec leurs quantités qui sont requis pour la création d'un autre produit.
Une nomenclature est utilisée pour planifier les achats et évaluer le cout du produit.

> Manufacturing > BOM

#### Station de travail

Un endroit ou les opérations de la nomenclature sont réalisées. C'est utile pour calculer le coût directe d'un produit.

> Manufacturing > Workstation

#### Ordre de production

Document qui demande la production d'un article particulier avec la quantité spécifiée.

> Manufacturing > Production Order

#### Outil de planing de production

Un outil pour la creation automatique d'ordres de productions et demandes basée sur les vente en cours sur une période 
donnée.

> Manufacturing > Production Planning Tool

* * *

### Site internet

#### Article de blog

Un court article qui apparait dans la section "Blog" du site généré par le module site internet d'ERPNext. Blog est la 
version courte de “Web Log”.

> Website > Blog Post

#### Page web

Une page web avec une unique adresse (adresse web) sur le site internet généré par ERPNext.

> Website > Web Page

* * *

### Configuration / Customisation

#### Champs personnalisé

Un champ définit par un utilisateur dans un formulaire ou un tableau.

> Setup > Customize ERPNext > Custom Field

#### Valeurs par défaut

C'est la section où vous definissez les valeurs par défaut pour divers paramètres du système.

> Setup > Data > Global Defaults

#### Entête d'impression

Un titre que vous pouvez définir sur une transaction uniquement pour l'impression. Par exemple vous pouvez imprimer un 
devis avec comme titre "Proposition" ou "Devis Pro forma".

> Setup > Branding and Printing > Print Headings

#### Conditions d'utilisation

Description des terms de votre contrat.

> Selling > Setup > Terms and Conditions

#### Unités de mesures

Comment les quantités sont mesurées. Ex., Kg, No., etc.

> Stock > Setup > UOM

{suite}
