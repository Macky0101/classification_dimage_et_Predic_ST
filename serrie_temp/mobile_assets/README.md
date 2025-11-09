
# Poultry Monitor - Assets Mobiles

Ce dossier contient tous les fichiers nécessaires pour l'application mobile de surveillance des volailles.

## Fichiers :

- `poultry_monitor_model.tflite` : Modèle TensorFlow Lite pour les prédictions
- `app_config.json` : Configuration du système
- `scaler_params.json` : Paramètres de normalisation des données
- `mobile_metadata.json` : Métadonnées pour l'application mobile

## Utilisation :

1. Le modèle attend des données de forme [1, 168, 47] (1 séquence, 168 timesteps, 47 features)
2. Les données doivent être normalisées avec les paramètres dans `scaler_params.json`
3. Les prédictions sont au format [12] valeurs correspondant aux 3 horizons (1h, 6h, 24h)

## Horizons de prédiction :

- 1h : indices [0, 1, 2, 3] → [temp, humidity, nh3, co]
- 6h : indices [4, 5, 6, 7] → [temp, humidity, nh3, co]  
- 24h : indices [8, 9, 10, 11] → [temp, humidity, nh3, co]
