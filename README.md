# Silvermap Open Data

Ce dépôt contient des jeux de données publiques sur les entreprises de la silver économie en France. Les données publiées sont extraites de la Silvermap, une base propriétaire recensant et caractérisant les acteurs économiques au service des seniors. Les fichiers accessibles ici sont diffusés en open data sous licence [Etalab 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence).

## Contexte et objectifs

La silver économie regroupe l'ensemble des activités économiques dédiées aux besoins et aspirations des personnes âgées de 60 ans et plus. Ce secteur en forte croissance couvre des domaines variés : santé, services à domicile, habitat adapté, technologies assistives, loisirs, ou encore formation.

L'objectif de ce partage de données est de faciliter l'accès à une information structurée sur les acteurs de ce secteur, permettre des analyses de marché, favoriser les collaborations entre acteurs, et contribuer à la transparence et au développement de l'écosystème silver économie.

## Périmètre et description des données

Les données publiées proviennent de multiples sources : registres publics (base Sirene de l'INSEE), informations déclaratives des entreprises, sites web institutionnels, et analyses réalisées en interne. Chaque entreprise est caractérisée selon plusieurs dimensions : son positionnement technologique et sectoriel, son modèle économique, sa cible client, et ses caractéristiques juridiques.

Le fichier contient actuellement 450 entreprises françaises actives dans la silver économie, couvrant l'ensemble du territoire national. Les données sont mises à jour mensuellement pour refléter les créations, modifications et cessations d'activité.

Les informations diffusées sont volontairement sélectionnées et anonymisées lorsque nécessaire, dans le respect des réglementations en vigueur. Seules les données à caractère public ou non sensible sont partagées dans ce dépôt.

## Schéma des données

**Fichier principal :** `Silvermap_20251004.csv`

Le fichier est encodé en UTF-8 et utilise la virgule comme séparateur. Voici la description détaillée des 21 colonnes :

| Champ | Type | Description | Exemple |
|-------|------|-------------|---------|
| **Nom** | string | Dénomination sociale de l'entreprise | "SilverCare Solutions" |
| **siren** | string | Identifiant SIREN (9 chiffres) | "123456789" |
| **Descriptif** | string | Description de l'activité et de l'offre | "Services d'aide à domicile personnalisés" |
| **Profil** | string | Typologie de l'offre croisant nature et technologie | "solution mixte", "service assisté", "produit connecté" |
| **Nature (X)** | string | Nature de l'offre : "produit", "hybride" ou "service" | "service" |
| **Tech (Y)** | string | Niveau technologique : "high tech", "hybride" ou "low tech" | "high tech" |
| **Domaine** | string | Secteur d'activité principal | "santé", "autonomie", "logement", "lifestyle", "communication", "finance", "vie pratique" |
| **Marché Géographique** | string | Zone de couverture commerciale | "National", "Régional", "International" |
| **Client** | string | Typologie de clientèle cible | "B2C", "B2B", "B2B2C" |
| **Distrib.** | string | Canaux de distribution : "b2b", "b2c", "b2b2c" ou "b2g" | "b2c" |
| **Biz Model** | string | Modèle économique principal | "Abonnement", "Vente", "Commission" |
| **Date création** | string | Date de création de l'entreprise | "2018-03-15" |
| **Date cessation** | string | Date de cessation d'activité si applicable | "2024-06-30" ou vide |
| **APE (ref)** | string | Code APE/NAF de l'activité principale | "88.10A" |
| **Catégorie d'entreprise** | string | Catégorie INSEE | "PME", "ETI", "GE", "MIC" |
| **Statut juridique** | string | Forme juridique | "SAS", "SARL", "Association" |
| **Adresse siège** | string | Adresse complète du siège social | "12 rue de la République, 75001 Paris" |
| **Département** | string | Numéro de département du siège | "75", "69", "13" |
| **Nationalité** | string | Pays d'origine de l'entreprise | "France", "Belgique" |
| **Soc à Mission** | string | Statut de société à mission | "Oui", "Non" ou vide |
| **Site web** | string | URL du site internet officiel | "https://www.exemple-silvercare.fr" |

### Classification des offres : la matrice Profil

Le champ **Profil** résulte du croisement des deux axes **Nature (X)** et **Tech (Y)**, créant une matrice de 9 typologies d'offres :

| Nature ↓ / Tech → | **Low tech** | **Hybride** | **High tech** |
|-------------------|--------------|-------------|---------------|
| **Produit** | produit autonome | produit connecté | produit supervisé |
| **Hybride** | solution autonome | solution mixte | solution accompagnée |
| **Service** | service humain | service assisté | service automatisé |

Cette classification permet d'identifier rapidement le positionnement d'une entreprise sur le continuum technologique et sur la nature de sa proposition de valeur.

### Domaines d'activité

Les 7 domaines couverts par la Silvermap reflètent les principaux besoins et usages des seniors :

- **autonomie** : aides techniques, maintien à domicile, compensation de la perte d'autonomie
- **santé** : dispositifs médicaux, télésanté, prévention, bien-être
- **logement** : habitat adapté, domotique, résidences services
- **lifestyle** : loisirs, culture, tourisme, activités de bien-être
- **communication** : solutions de lien social, lutte contre l'isolement
- **finance** : services bancaires, assurance, patrimoine adaptés aux seniors
- **vie pratique** : livraison, courses, services du quotidien

**Notes sur les données :**
- Certains champs peuvent contenir des valeurs vides lorsque l'information n'est pas disponible ou non applicable
- Les dates suivent le format ISO 8601 (AAAA-MM-JJ)
- Le champ "Date cessation" n'est renseigné que pour les entreprises ayant cessé leur activité
- Les classifications internes (Profil, Nature, Tech, Domaine) suivent une taxonomie propriétaire développée pour la Silvermap

## Licence et propriété intellectuelle

Les jeux de données publiés dans ce dépôt (fichiers .csv) sont diffusés sous licence [Etalab 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence).

Cette licence vous autorise à :
- Reproduire, copier et publier les données
- Adapter, modifier, extraire et transformer les données
- Diffuser et redistribuer les données
- Exploiter les données à titre commercial

Sous réserve de :
- Mentionner la paternité des données : "Source : Silvermap"
- Indiquer la date de dernière mise à jour des données utilisées

**Propriété intellectuelle réservée :** La méthodologie de collecte, d'enrichissement et d'analyse des données, la structure complète de la base Silvermap, ainsi que les critères de catégorisation et taxonomies utilisés (notamment la matrice de classification des profils) restent la propriété exclusive d'Alexandre Faure. Seules les données brutes publiées dans ce dépôt sont concernées par la licence open data.

## Utilisation

### Téléchargement direct

Vous pouvez télécharger le fichier CSV le plus récent directement depuis le dépôt :

```bash
wget https://raw.githubusercontent.com/colbert1665/silvermap/main/Silvermap_20251004.csv
```

ou

```bash
curl -O https://raw.githubusercontent.com/colbert1665/silvermap/main/Silvermap_20251004.csv
```

### Exemples d'exploitation

**Chargement en Python avec pandas :**
```python
import pandas as pd

# Charger les données
df = pd.read_csv('Silvermap_20251004.csv')

# Filtrer par domaine
sante = df[df['Domaine'] == 'santé']

# Analyser la répartition par profil technologique
repartition_profil = df['Profil'].value_counts()

# Entreprises high tech en B2C
hightech_b2c = df[(df['Tech (Y)'] == 'high tech') & (df['Distrib.'] == 'b2c')]
```

**Analyse de la matrice Profil :**
```python
# Créer un tableau croisé Nature x Tech
matrice = pd.crosstab(df['Nature (X)'], df['Tech (Y)'])

# Identifier les solutions mixtes (hybride x hybride)
solutions_mixtes = df[df['Profil'] == 'solution mixte']
```

**Export pour analyse en tableur :**
Le fichier CSV peut être directement ouvert dans Excel, LibreOffice Calc, ou Google Sheets pour des analyses via tableaux croisés dynamiques.

### Bonnes pratiques

- Vérifiez régulièrement la disponibilité de nouvelles versions (mise à jour mensuelle)
- Conservez la traçabilité de la version utilisée (date dans le nom de fichier)
- Citez systématiquement la source dans vos publications ou analyses
- Croisez avec d'autres sources ouvertes pour enrichir vos analyses (base Sirene, données sectorielles)

## Contact et support

Pour toute question relative aux données, signaler une erreur, ou suggérer des améliorations :

📧 **Email :** contact@alexandrefaure.fr

**Signalement d'erreurs :** Si vous identifiez une erreur dans les données (information obsolète, coordonnées incorrectes), merci de nous la signaler en précisant le SIREN de l'entreprise concernée et la nature de l'erreur.

**Suggestions d'évolution :** Vos retours sur l'utilité des données et les besoins d'enrichissement sont les bienvenus pour faire évoluer ce partage open data.

---

*Dernière mise à jour du README : octobre 2025*
