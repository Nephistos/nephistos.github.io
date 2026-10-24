# nephistos.github.io

Site racine du compte GitHub **Nephistos**, servi à l'adresse `https://nephistos.github.io/`.

Ce dépôt a un seul rôle : héberger, à la racine du domaine, le fichier qui relie l'application Android **Locus Magnus** à son site web. L'application elle-même vit dans le dépôt [Locus-Magnus](https://github.com/Nephistos/Locus-Magnus) et reste servie à l'adresse `https://nephistos.github.io/Locus-Magnus/`.

## Contenu

```
.nojekyll                      indispensable : sans lui, GitHub Pages ignore le dossier .well-known
.well-known/assetlinks.json    preuve que le site et l'application Android appartiennent au même propriétaire
index.html                     redirige la racine vers Locus Magnus (facultatif)
README.md                      ce fichier
```

## Le fichier `assetlinks.json`

Android lit ce fichier à l'adresse `https://nephistos.github.io/.well-known/assetlinks.json`. S'il est absent ou incorrect, l'application affiche une barre d'adresse de navigateur au lieu de s'ouvrir en plein écran.

Il contient :

- `package_name` : l'identifiant de l'application, `com.emilienlecoffre.locusmagnus`. Il doit être identique à celui saisi dans PWABuilder et ne peut plus changer après la publication.
- `sha256_cert_fingerprints` : les empreintes des clés qui signent l'application. Il en faut deux :
  1. **L'empreinte de votre clé**, fournie par PWABuilder dans le zip du paquet Android (fichier `assetlinks.json` ou `signing-key-info.txt`).
  2. **L'empreinte de Google**, affichée dans la Play Console, sous *Test et publication → Intégrité de l'application → Signature d'application*, une fois le paquet déposé.

Remplacez les deux valeurs `REMPLACER_PAR_…` par ces empreintes (format `AA:BB:CC:…`). Tant qu'une empreinte n'est pas connue, supprimez simplement sa ligne, en veillant à ne pas laisser de virgule après la dernière valeur.

## Vérifier

1. Ouvrez `https://nephistos.github.io/.well-known/assetlinks.json` : le JSON doit s'afficher.
2. Après publication, l'application installée depuis le Play Store doit s'ouvrir en plein écran, sans barre d'adresse.

## Licence

Tous droits réservés.
