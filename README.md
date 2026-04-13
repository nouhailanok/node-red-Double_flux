# Node-RED ML & IoT Projects

Projets réalisés dans le cadre d'un cours sur Node-RED, le Machine Learning et l'IoT.

---

## Membres de l'équipe

| Nom | Projet |
|-----|--------|
| Nouhaila Nokry | Mini Projet |
| Imane Saoudi | Mini Projet |
| Amane Mohamed | Mini Projet |

---

## Projets

### 1. Mini Projet AVANT
**Fichier :** `flows_Mini_Projet_AVANT.json`  
**Équipe :** Nouhaila Nokry, Imane Saoudi, Amane Mohamed

Moniteur de datacenter en temps réel simulant les métriques d'un GPU :
- Charge GPU (%)
- Température (°C)
- Vitesse du ventilateur (RPM)

**Fonctionnalités :**
- Jauges en temps réel
- Graphiques en ligne
- Alerte si température > 60°C
- **Visualisation SVG dynamique** — schéma datacenter interactif avec 3 métriques qui se mettent à jour en temps réel :
  - Couleur de la température change selon les seuils (vert / orange / rouge)
  - Barre de progression pour chaque métrique
  - Ventilateur animé dont la vitesse de rotation suit le RPM réel

**Technologies utilisées :**
- `node-red-dashboard` — gauges et charts
- `ui_template` + **SVG inline** — visualisation graphique dynamique pilotée par les données

---

### 3. Mini Projet APRES
**Fichier :** `Mini_Projet_APRES_.json`  
**Équipe :** Nouhaila Nokry, Imane Saoudi, Amane Mohamed

Version améliorée du Mini Projet avec intégration de **Mosquitto (MQTT)** et **TensorFlow**.

**Fonctionnalités ajoutées :**
- **MQTT (Mosquitto)** — publication et souscription des métriques sur le topic `datacenter/metrics`
- **TensorFlow / Régression linéaire** — prédiction de surchauffe basée sur l'historique des températures (prédiction à 5 secondes)
- Dashboard visuel

**Technologies utilisées :**
- `mosquitto` — broker MQTT local
- `node-red-dashboard` — interface utilisateur
- Régression linéaire sur historique de températures 

**Prérequis :**
```bash
brew install mosquitto
brew services start mosquitto
```

---

## Installation générale

1. Installer Node-RED :
```bash
npm install -g node-red
```

2. Installer les dépendances :
```bash
cd ~/.node-red
npm install ml-regression-simple-linear ml-regression-multivariate-linear
```

3. Importer un flux dans Node-RED :
   - Ouvrir `http://localhost:1880`
   - Menu ☰ → Import → coller le contenu du fichier JSON

---

## Structure du repo
```
node-red-Double_flux/
├── flows_Mini_Projet_AVANT_WITH_SVG.json        # Moniteur datacenter (version de base)
├── Mini_Projet_APRES_avecMQTT_model.json             # Moniteur datacenter + MQTT + TensorFlow
└── README.md
```
