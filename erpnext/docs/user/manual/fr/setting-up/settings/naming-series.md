# Conventions de nommage

### 1. Introduction

Les enregistrements sont généralement des données principales ou “Transaction”. Une données principale est un enregistrement
qui a un nom par exemple, un client, un fournisseur, un employé et. Une transaction est un enregistrement qui a un numéro.
Les devis, les factures sont par exemple des transactions. On créer des transactions grâce aux données principales.

ERPNext autorise à préfixer les transactions, chaque préfixe formant une série. Par exemple, des transactions de la serie
INV12 auront comme numéro INV120001, INV120002 etc.

Vous pouvez avoir plusieurs seriees par transaction. C'est par exemple commun d'avoir des series séprarées pour
chaque année fiscale. Par exemple dans les factures de ventes vous pourriez avoir:

  * INV120001
  * INV120002
  * INV-A-120002

etc. Vous pourriez aussi avoir une serie pour chaque type de client ou pour vos différents points de vente.

### 2. Gérer les noms pour les documents

Pour configurer une série, rendez-vous sur:

> Setup > Tools > Update Numbering Series

Dans ce formulaire,

  1. Selectionnez la transaction pour laquelle pour voulez créer la serie. Le système va mettre à jour la serie courante 
  dans le champs texte.
  2. Editez les series avec un prefixe unique pour chaque série. Chaque préfixe doit être sur une nouvelle ligne.
  3. Le premier préfixe contiendra le prefixe par defaut. Si vous voulez que l'utilisateur choisisse une série précise plutot 
  que celle par defaut, cochez la case “User must always select”.

Vous pouvez aussi mettre à jour le debut d'une série en entrant le nom de la série et le point de départ dans la section “Update Series”.

### 3. Exemple

Voici comment configurer la série de nommage.

<img class="screenshot" alt="Naming Series" src="{{docs_base_url}}/assets/img/setup/settings/naming-series.gif">

{suite}

