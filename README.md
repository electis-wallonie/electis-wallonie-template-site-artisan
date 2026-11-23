# Template site artisan (marque blanche)

Site vitrine une page pour artisans (couvreur, plombier, électricien, peintre, paysagiste…), sans aucune marque. On le duplique pour chaque nouveau client, puis on l'adapte avec le prompt de `PROMPT.md`.

Contenu : en-tête avec téléphone, accroche, 4 prestations, bloc devis, 4 curseurs avant / après, galerie de chantier, atouts, avis Google, pied de page avec zone d'intervention, formulaire de devis en 2 étapes (Web3Forms), bandeau cookies + pixel Meta (facultatif), pages Confidentialité et Mentions légales.

## Démarrer un nouveau client

1. Sur GitHub : **Use this template → Create a new repository** (ou copier le dossier).
2. Remplir la fiche client dans `PROMPT.md`, et l'envoyer à Claude avec le lien du nouveau dépôt et les photos.
3. Vérifier qu'il ne reste aucune balise : `grep -rn "{{" site-web` ne doit rien renvoyer.
4. Dans le dépôt : **Settings → Pages → Source : GitHub Actions**. Le site se met en ligne à chaque modification de `site-web/`.
5. Domaine perso (facultatif) : créer un fichier `CNAME` à la racine contenant le domaine, ex. `client.mavillepro.eu`.

## Organisation

```
site-web/
  index.html              la page
  confidentialite.html    politique de confidentialité (RGPD)
  mentions-legales.html   mentions légales
  css/theme.css           COULEURS ET POLICES : le seul fichier à toucher pour l'habillage
  css/style.css           styles compilés (Tailwind), ne pas modifier
  js/lucide.min.js        icônes
  images/                 logo, favicon et photos (images d'exemple à remplacer)
.github/workflows/deploy.yml   mise en ligne GitHub Pages
```

## Couleurs

Tout se règle dans `site-web/css/theme.css`, au format `R G B` (ex. `#D62828` → `214 40 40`) :

| Variable | Rôle |
|---|---|
| `--brand-primary` | accent : boutons, liens, petits carrés, curseurs |
| `--brand-primary-hover` | accent au survol (un peu plus foncé) |
| `--brand-dark` | titres et fond du bloc Réalisations |
| `--brand-darker` | pied de page et en-tête du formulaire |
| `--brand-light` | fonds clairs des sections et des cartes |
| `--brand-soft` | survol des choix du formulaire |

Exemples déjà utilisés : RD Couverture `30 111 214` / `31 44 122` (bleu), Hoffmann Toiture `214 40 40` / `38 49 61` (rouge et anthracite).

## Images à remplacer (même nom de fichier)

| Fichier | Format conseillé | Usage |
|---|---|---|
| `logo.svg` (ou .png) | hauteur 56 px affichée | en-tête, pied de page, pages légales |
| `favicon.svg` | carré | icône d'onglet |
| `hero.webp` | 1200×900 environ | grande image d'accueil (par défaut : utilitaire blanc à floquer) |
| `prestation-1.jpg` à `prestation-4.jpg` | 4/3 | cartes des prestations |
| `avant-1.jpg` / `apres-1.jpg` … `-4` | 4/3, même cadrage avant et après | curseurs avant / après |
| `chantier-1.jpg` à `chantier-4.jpg` | 4/3 | galerie « Sur nos chantiers » |
| `equipe.jpg` | portrait 3/4 | bloc Garantie |

Si l'extension change (ex. `logo.png`), mettre à jour les liens dans les 3 pages HTML.

## Balises à remplacer

**Identité** : `{{NOM_ENTREPRISE}}`, `{{METIER}}` (ex. Couvreur), `{{METIER_MINUSCULE}}` (ex. couvreur zingueur), `{{FORME_JURIDIQUE}}` (ex. SARL, entreprise individuelle), `{{DIRIGEANT}}`, `{{SIREN}}`
**Contact** : `{{TEL_AFFICHE}}` (06 12 34 56 78), `{{TEL_LIEN}}` (0612345678), `{{EMAIL}}`, `{{ADRESSE}}` (rue, CP, ville), `{{VILLE_SIEGE}}`, `{{CODE_POSTAL}}`
**Secteur** : `{{VILLE}}` (ville cible du référencement), `{{ZONES}}` (communes desservies)
**SEO** : `{{TITRE_SEO}}` (≈ 60 caractères, ex. « Nom - Couvreur à Caen | Toiture, Zinguerie »), `{{DESCRIPTION_SEO}}` (≈ 155 caractères)
**Accueil** : `{{HERO_SURTITRE}}`, `{{HERO_TITRE}}`, `{{HERO_TITRE_ACCENT}}` (partie colorée), `{{HERO_TEXTE}}`, `{{NOTE_GOOGLE}}` (ex. 4,9), `{{NB_AVIS}}`
**Prestations** : `{{PRESTATIONS_TITRE}}`, `{{PRESTATIONS_TITRE_ACCENT}}`, `{{PRESTATIONS_INTRO}}`, puis pour 1 à 4 : `{{PRESTATION_n_TITRE}}`, `{{PRESTATION_n_TEXTE}}`, `{{PRESTATION_n_ICONE}}` (nom d'icône [Lucide](https://lucide.dev/icons))
**Devis** : `{{DEVIS_INTRO}}`, `{{TRAVAUX_1}}` à `{{TRAVAUX_5}}` (choix du formulaire, courts)
**Réalisations** : `{{AVANT_APRES_1_TITRE}}` à `_4_`, `{{CHANTIER_1_LEGENDE}}` à `_4_`
**Garantie** : `{{EQUIPE_TITRE}}`, `{{EQUIPE_SOUS_TITRE}}`, `{{ATOUT_1_TITRE}}`, `{{ATOUT_1_TEXTE}}`, `{{ATOUT_2_TITRE}}`, `{{ATOUT_2_TEXTE}}`
**Avis** : `{{AVIS_1_TEXTE}}`, `{{AVIS_1_AUTEUR}}` à `_3_` (vrais avis Google uniquement)
**Pied de page** : `{{SLOGAN}}`, `{{ANNEE}}`
**Pages légales** : `{{DATE_MAJ}}`

## Réglages techniques (bas de `index.html`, bloc `window.SITE`)

- `web3formsKey` : clé [Web3Forms](https://web3forms.com) créée avec l'email du client. Vide = le formulaire affiche « appelez-nous ».
- `pixelId` : identifiant du pixel Meta. Vide = ni pixel ni bandeau cookies (et le lien « Gérer les cookies » disparaît).

Chaque demande de devis indique sa provenance (Facebook, Google, direct…) grâce aux paramètres `utm_source`, `fbclid` et `gclid`.

## Sections facultatives

- Pas encore d'avis Google : supprimer la section `AVIS GOOGLE`, le badge de note dans l'accueil et le lien « Avis » des deux menus.
- Pas de photos avant / après : supprimer la grille des curseurs, garder la galerie.
- Moins de 4 prestations : supprimer les `<article>` en trop (la grille s'adapte).
