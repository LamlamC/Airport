# Projet Applicatif M2 - Gestion de Vols et Recommandations

Ce projet a été réalisé dans le cadre du Master 2 Management, Data & IA. Il vise à concevoir un système de gestion intelligent pour un aéroport (Charles de Gaulle) en utilisant MongoDB et Python via Jupyter Notebook.

## 👥 Membres du groupe

- CASTELLI Ornella
- KHALLOULI Nadia
- CHOUMOUL Lamya
- MOUNGAD Massilia
- GUEYE Samira Bourgi

## 🎯 Objectif

- Gérer les vols, passagers, services, bagages et réservations dans une base MongoDB
- Implémenter un algorithme de recommandation de destinations basé sur le profil des passagers
- Effectuer toutes les opérations CRUD à travers des fonctions Python
- Structurer un code facilement migrable vers une API ou microservice

## 🧰 Technologies utilisées

- Python 3
- MongoDB Atlas
- pymongo
- Jupyter Notebook

## 🗃️ Collections MongoDB

- `flights` : infos vols (id, horaires, statut...)
- `passengers` : données passagers + profil
- `bookings` : réservations (classe, siège)
- `baggage` : suivi des bagages (poids, position)
- `services` : services liés au vol (embarquement, contrôle)

## 🔄 Fonctionnalités principales

- Ajout / lecture / modification / suppression dans chaque collection
- Recommandation de destinations personnalisées
- Préparation de message d’email personnalisé

## 🚀 Lancer le projet

1. Cloner le dépôt
2. Installer les dépendances :
   ```
   pip install pymongo
   ```
3. Lancer le notebook `projet_applicatif_M2_algorithme.ipynb`
4. Modifier l’URI MongoDB si besoin

## 🔮 Exemple de recommandation

```json
{
  "passenger": "P002",
  "message": "Bonjour Nadia, vous pourriez aimer ces destinations : Tokyo, Dubai",
  "suggestions": ["Tokyo", "Dubai"]
}
```

## 📁 Arborescence suggérée

```
📁 projet-applicatif/
│
├── 📄 README.md
├── 📄 projet_applicatif_M2_algorithme.ipynb
├── 📄 Projet_M2_MongoDB_Jupyter.docx
├── 📁 data/
│   └── fichiers JSON, .csv (si applicable)
└── 📁 screenshots/
    └── captures MongoDB Compass
```

## 📌 Remarque

Ce projet est un prototype académique. Il peut être facilement intégré à une API Flask ou FastAPI pour évoluer vers une application déployable.


## 🌐 Tester l'algorithme via une API (FastAPI)

Après avoir lancé l'API FastAPI (si vous avez migré le notebook en microservice), vous pouvez tester la recommandation directement depuis l'interface interactive Swagger :

1. Exécuter le serveur FastAPI :
   ```
   uvicorn main:app --reload
   ```

2. Aller dans votre navigateur à :
   👉 http://127.0.0.1:8000/docs#/default/get_personalized_recommendation_recommendation__passenger_id__get

3. Cliquer sur **Try it out**

4. Entrer un ID de passager, par exemple :
   ```
   P001
   ```

5. Cliquer sur **Execute**

Vous obtiendrez une réponse avec une suggestion de destination personnalisée.

