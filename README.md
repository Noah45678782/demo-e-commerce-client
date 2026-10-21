# Démo — Drive Intermarché personnalisé (côté client)

Ouvrir `index.html` dans un navigateur (desktop, aucune installation). Client fictif **Jean**, magasin **Intermarché Express Nice Cessole**.

L'interface reprend le drive actuel (en-tête, menu Rayons, fiche produit, panier, Mon compte) et ajoute :

- **Profil de consommation** (Compte › *Mon profil conso*) : déduit des 6 dernières commandes (foyer, nombre de personnes,
  préférences de consommation, budget, marques, temps de cuisine), modifiable à tout moment, avec retour au profil déduit.
  Il pilote les recommandations, l'ordre des remplacements et les recettes (aperçu en direct sur la page).
- **Remplacements anticipés** : quand on ajoute un produit souvent en rupture sur le drive (taux non affiché au client), la plateforme propose
  tout de suite 3 remplacements classés selon le profil. Le client peut les accepter, les refuser ou les modifier
  (retirer, réordonner, choisir d'autres produits). Les consignes apparaissent dans le panier et à la validation.
- **Local & nouveautés du magasin** : spécialités de Nice (socca chips, olives de Nice AOP, blettes, pissaladière, tourte de blettes,
  pan bagnat, vin de Bellet…) et nouveautés propres au magasin, sur l'accueil et dans le menu Rayons.
- **Bandeau du magasin** sous « Livraison offerte » : messages qui défilent et lien Instagram, définis par le point de vente
  dans `STORE_BANNER`, en tête du script.
- **Recettes** (30, dont 11 niçoises) : classées selon tous les critères du profil (foyer, nombre de personnes, préférences,
  budget, marques, temps de cuisine). Les recettes niçoises n'apparaissent que si le profil inclut « Produits locaux ».
  Chaque recette indique préparation, cuisson, difficulté, matériel, étapes avec les quantités et une astuce. On choisit le
  nombre de personnes, on coche ce qu'on a déjà, et la recette ajoute les produits au panier (avec remplacements si besoin).
  - **Deux montants** : *approvisionnement* (produits entiers achetés au drive) et *coût de la recette* au prorata des quantités
    utilisées, par personne. Les fruits et légumes vendus au poids sont vendus à la pièce : poids moyen × prix au kilo.
  - **PDF** : téléchargement de la recette (jsPDF 2.5.1, licence MIT, intégré au fichier : fonctionne hors connexion).
  - **Vidéo** : lecteur animé avec un avatar chef, sous-titres et voix de synthèse du navigateur (simulation, pas une vraie vidéo).

Produits, prix, taux de rupture et producteurs sont fictifs. Ils se modifient dans `RAW`, `ORDERS`, `RECIPES` et `DERIVED`.
