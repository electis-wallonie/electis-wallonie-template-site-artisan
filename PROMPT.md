# Prompt pour adapter le template à une nouvelle entreprise

Copier tout le bloc ci-dessous, remplir la fiche, joindre les photos et le logo, puis l'envoyer à Claude.
Les champs laissés vides sont rédigés par Claude à partir du métier, de la ville et de la fiche Google (sauf les avis, jamais inventés).

---

```
Adapte mon template de site artisan (dépôt GitHub : electis-wallonie/electis-wallonie-template-site-artisan)
pour une nouvelle entreprise. Crée le nouveau dépôt : electis-wallonie/[NOM-DU-DEPOT]

Règles :
- Lis d'abord README.md : il liste toutes les balises {{...}}, les images et les réglages.
- Remplace TOUTES les balises dans index.html, confidentialite.html et mentions-legales.html.
  À la fin, `grep -rn "{{" site-web` ne doit rien renvoyer.
- Mets les couleurs de l'entreprise dans site-web/css/theme.css (déduites du logo ou du véhicule si je n'en donne pas).
- Remplace les images d'exemple par mes photos (redimensionnées en 1200 px max, JPG qualité 80),
  en gardant les noms de fichier du README. S'il manque des photos, dis-moi lesquelles.
- Si je n'ai pas de logo en fichier, redessine-le en SVG d'après la photo du véhicule ou de l'enseigne.
- Textes : français naturel, ton artisan, phrases courtes, rien d'inventé (pas de chiffres, labels
  ou garanties que je n'ai pas donnés). Ne recopie que de vrais avis Google, tels quels.
- Mets à jour le README du nouveau dépôt pour ce client (nom, ville, lien du site, ce qui reste à compléter).
- Si un domaine est indiqué, crée le fichier CNAME.
- Montre-moi le résultat (capture mobile + ordinateur) avant de publier.

FICHE CLIENT
Nom de l'entreprise :
Métier (ex. Couvreur zingueur) :
Forme juridique :
Dirigeant :
SIREN :
Adresse complète :
Téléphone :
Email :
Ville principale (référencement) :
Communes desservies :
Années d'expérience / entreprise familiale / autre argument :
Assurance décennale (oui / non) :
Prestations (4 maximum, par ordre d'importance) :
  1.
  2.
  3.
  4.
Types de travaux pour le formulaire (5 maximum) :
Note Google et nombre d'avis :
Lien de la fiche Google :
3 avis Google à afficher (texte + prénom et initiale) :
Couleurs souhaitées (ou « d'après le logo ») :
Slogan (facultatif) :
Domaine (ex. client.mavillepro.eu) :
Clé Web3Forms (si déjà créée) :
Pixel Meta (si déjà créé) :

PHOTOS JOINTES (indiquer à quoi correspond chacune) :
- logo :
- photo d'accueil (véhicule, équipe ou chantier) :
- prestations 1 à 4 :
- avant / après 1 à 4 :
- galerie chantier 1 à 4 :
- équipe :
```
