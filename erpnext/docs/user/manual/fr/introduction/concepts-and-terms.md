Avant de commencer l'implémentation, familiarisons nous avec la terminologie utilisée et quelques concept d'ERPNext.

* * *

### Concepts de base

#### Compagnie

Représente la compagnie pour laquelle ERPNext est configuré. Avec la même configuration, vous pouvez créer plusieurs 
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

#### Sales Partner

A third party distributer / dealer / affiliate / commission agent who sells
the company’s products usually for a commission.

> Selling > Setup > Sales Partner

#### Sales Person

Someone who pitches to the Customer and closes deals. You can set targets for
Sales Persons and tag them in transactions.

> Selling > Setup > Sales Person

* * *

### Buying

#### Purchase Order

A contract given to a Supplier to deliver the specified Items at the specified
cost, quantity, dates and other terms.

> Buying > Purchase Order

#### Material Request

A request made by a system User, or automatically generated by ERPNext based
on reorder level or projected quantity in Production Plan for purchasing a set
of Items.

> Buying > Material Request

* * *

### Stock (Inventory)

#### Warehouse

A logical Warehouse against which stock entries are made.

> Stock > Warehouse

#### Stock Entry

Material transfer from a Warehouse, to a Warehouse or from one Warehouse to
another.

> Stock > Stock Entry

#### Delivery Note

A list of Items with quantities for shipment. A Delivery Note will reduce the
stock of Items for the Warehouse from where you ship. A Delivery Note is
usually made against a Sales Order.

> Stock > Delivery Note

#### Purchase Receipt

A note stating that a particular set of Items were received from the Supplier,
most likely against a Purchase Order.

> Stock > Purchase Receipt

#### Serial Number

A unique number given to a particular unit of an Item.

> Stock > Serial Number

#### Batch

A number given to a group of units of a particular Item that may be purchased
or manufactured in a group.

> Stock > Batch

#### Stock Ledger Entry

A unified table for all material movement from one warehouse to another. This
is the table that is updated when a Stock Entry, Delivery Note, Purchase
Receipt, and Sales Invoice (POS) is made.

#### Stock Reconciliation

Update Stock of multiple Items from a spreadsheet (CSV) file.

> Stock > Stock Reconciliation

#### Quality Inspection

A note prepared to record certain parameters of an Item at the time of Receipt
from Supplier, or Delivery to Customer.

> Stock > Quality Inspection

#### Item Group

A classification of Item.

> Stock > Setup > Item Group

* * *

### Human Resource Management

#### Employee

Record of a person who has been in present or past, in the employment of the
company.

> Human Resources > Employee

#### Leave Application

A record of an approved or rejected request for leave.

> Human Resource > Leave Application

#### Leave Type

A type of leave (e.g., Sick Leave, Maternity Leave, etc.).

> Human Resource > Leave and Attendance > Leave Type

#### Process Payroll

A tool that helps in creation of multiple Salary Slips for Employees.

> Human Resource > Salary and Payroll > Process Payroll

#### Salary Slip

A record of the monthly salary given to an Employee.

> Human Resource > Salary Slip

#### Salary Structure

A template identifying all the components of an Employees' salary (earnings), 
tax and other social security deductions.

> Human Resource > Salary and Payroll > Salary Structure

#### Appraisal

A record of the performance of an Employee over a specified period based on
certain parameters.

> Human Resources > Appraisal

#### Appraisal Template

A template recording the different parameters of an Employees' performance and
their weightage for a particular role.

> Human Resources > Employee Setup > Appraisal Template

#### Attendance

A record indicating presence or absence of an Employee on a particular day.

> Human Resources > Attendance

* * *

### Manufacturing

#### Bill of Materials (BOM)

A list of Operations and Items with their quantities, that are required to
produce another Item. A Bill of Materials (BOM) is used to plan purchases and
do product costing.

> Manufacturing > BOM

#### Workstation

A place where a BOM operation takes place. It is useful to calculate the
direct cost of the product.

> Manufacturing > Workstation

#### Production Order

A document signaling production (manufacture) of a particular Item with
specified quantities.

> Manufacturing > Production Order

#### Production Planning Tool

A tool for automatic creation of Production Orders and Purchase Requests based
on Open Sales Orders in a given period.

> Manufacturing > Production Planning Tool

* * *

### Website

#### Blog Post

A short article that appears in the “Blog” section of the website generated
from the ERPNext website module. Blog is a short form of “Web Log”.

> Website > Blog Post

#### Web Page

A web page with a unique URL (web address) on the website generated from
ERPNext.

> Website > Web Page

* * *

### Setup / Customization

#### Champs personnalisé

Un champ définit par un utilisateur dans un formulaire ou un tableau.

> Setup > Customize ERPNext > Custom Field

#### Valeurs par défaut

C'est la section ou vous definissez les valeurs par défaut pour divers paramètres du système.

> Setup > Data > Global Defaults

#### Entête d'impression

Un titre que vous pouvez définir sur une transaction uniquement pour l'impression. Par exemple vous pouvez imprimer un 
devis avec comme titre "Proposition" ou "Facture Pro forma".

> Setup > Branding and Printing > Print Headings

#### Conditions d'utilisation

Description des terms de votre contrat.

> Selling > Setup > Terms and Conditions

#### Unités de mesures

Comment les quantités sont mesurées. Ex., Kg, No., etc.

> Stock > Setup > UOM

{suite}
