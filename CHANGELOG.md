# Changelog
## 0.0.1
- Voir README pour la liste complète des modifications principales :
  - Ajout de variables d'environnement manquantes pour la configuration (Azure OpenAI, sélection du modèle LLM, etc.).
  - Modularité du choix du LLM (OpenAI/Azure OpenAI via env vars).
  - Logique unifiée de sélection du modèle, clé API et endpoints (priorité aux variables d'environnement).

## 0.0.2
- Correction : pas de valeur `allowed_domains` par défaut (bug corrigé, la valeur doit être explicitement définie ou gérée en argument de la fonction retry_with_browser_use_agent dans le fichier server.py). 

## 0.0.3
- Azure OpenAI : prise en charge des identités managées via `DefaultAzureCredential` et `get_bearer_token_provider`.
- Si aucune clé API n'est fournie, le serveur utilise automatiquement l'identité managée de l'environnement Azure pour l'authentification.
- Permet une configuration plus sécurisée et native sur Azure Web App ou VM.

## 0.0.4
- Ajout de la variable d'environnement `BROWSER_USE_RECORD_VIDEO_DIR` pour surcharger le chemin d'enregistrement vidéo via l'environnement.

## 0.0.5
- Ajout : le chemin d'enregistrement de la vidéo peut maintenant être relatif et inclut automatiquement le nom d'utilisateur de l'utilisateur courant. Cela permet de séparer les vidéos générées par chaque utilisateur dans des sous-dossiers dédiés.

## 0.0.6
- Ajout : nouvelle variable `record_video_file` qui est définie via un appel LLM dans `server.py` pour nommer la vidéo d'enregistrement de façon plus user-friendly.
- Changement : l'output de retry est maintenant un dump JSON contenant une liste avec deux éléments :
  - `content` : tout le contenu de la réponse
  - `artifact` : le chemin local vers la vidéo générée

## 0.0.7
-Patch : Oublie de retrait d'un log qui créeait une erreur systématique en déployé.

## 0.0.8 
-Patch : Mauvaise condition dans retry qui empechait d'accéder à la connection par IAM.

## 0.0.9
-Upload des dossiers (browser-use-downloads / browser-use-user-data-dir / browser-use-downloads) dans le dossier .neo-sandbox afin d'éviter les memory leaks
