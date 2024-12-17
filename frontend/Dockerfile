# Utiliser une image Python comme base
FROM python:3.9-slim

# Installer les dépendances nécessaires pour ffmpeg et nettoyer les fichiers temporaires
RUN apt-get update && apt-get install -y --no-install-recommends \
    ffmpeg \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers de l'application dans le conteneur
COPY . /app 

# Installer les dépendances Python
RUN pip install --no-cache-dir -r requirements.txt

# Exposer le port 5000 pour Flask
EXPOSE 5000

# Définir l'entrée pour le conteneur (lancement de Flask)
CMD ["python", "app.py"]


