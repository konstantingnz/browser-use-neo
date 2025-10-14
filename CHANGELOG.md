# Changelog
## 0.0.1
- Première version du fork basée sur browser-use 0.8.0.
- Voir README pour la liste complète des modifications principales :
  - Ajout de variables d'environnement manquantes pour la configuration (Azure OpenAI, sélection du modèle LLM, etc.).
  - Modularité du choix du LLM (OpenAI/Azure OpenAI via env vars).
  - Logique unifiée de sélection du modèle, clé API et endpoints (priorité aux variables d'environnement).

## 0.0.2
- Correction : pas de valeur `allowed_domains` par défaut (bug corrigé, la valeur doit être explicitement définie ou gérée en argument de la fonction retry_with_browser_use_agent dans le fichier server.py). 


