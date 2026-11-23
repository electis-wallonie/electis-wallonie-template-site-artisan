# Questionnaire : site V1 pour un artisan prospecté

But : faire en quelques minutes une première version du site, à montrer à l'artisan pour le convaincre.
Remplis ce que tu as, laisse vide le reste. Seuls les champs ★ sont indispensables.

**Avant d'envoyer :**
1. Sur GitHub, ouvre le template → **Use this template → Create a new repository** (nom conseillé : `metier-ville-nom`, ex. `couvreur-caen-dupont`).
2. Dans le nouveau dépôt : **Settings → Pages → Source : Deploy from a branch → main / (root) → Save**.
3. Copie le bloc ci-dessous, remplis-le, joins les captures du post et les photos, envoie.

---

```
Fais la V1 du site d'un artisan à partir de mon template.
Dépôt du nouveau site (déjà créé depuis le template) ★ : electis-wallonie/

═══ 1. L'ESSENTIEL ═══
★ Nom de l'entreprise (ou prénom + nom de l'artisan) :
★ Métier (ex. couvreur, plombier, peintre, maçon, électricien, paysagiste…) :
★ Ville où il est basé :
★ Téléphone :
Email :

═══ 2. LE POST FACEBOOK ═══
Texte du post (copier-coller tel quel) :
Captures d'écran jointes (post, profil, page) : oui / non
Photos de chantier jointes : oui / non — combien :
Lien du profil ou de la page Facebook :

═══ 3. CE QU'IL FAIT ═══
Prestations (autant que tu en connais, je compléterai jusqu'à 4 avec les plus courantes du métier) :
Secteur / communes desservies (sinon je mets « [ville] et alentours ») :
Spécialité ou point fort (ex. ardoise, salle de bain clé en main, urgences 7j/7) :

═══ 4. SI TU LES AS (BONUS) ═══
Années d'expérience :
Entreprise familiale / seul / nombre de personnes :
Assurance décennale : oui / non / je ne sais pas
Devis gratuit : oui / non / je ne sais pas
Note Google + nombre d'avis :
2 ou 3 avis clients réels (texte + prénom) :
Logo : joint / visible sur le véhicule / pas de logo
Couleurs (ex. celles du camion, du logo) :
SIREN :
Adresse :
Domaine souhaité (ex. nom.mavillepro.eu) :

═══ RÈGLES POUR LA V1 ═══
- Lis README.md du dépôt (balises, images, couleurs), puis remplace TOUTES les balises {{...}}
  dans les 3 pages : `grep -rn "{{" site-web` doit être vide à la fin.
- Rien d'inventé sur l'artisan : pas d'années d'expérience, d'avis, de note, de garantie,
  de certification ou de chiffre que je n'ai pas donnés. Les textes de présentation peuvent
  être rédigés à partir du métier et de la ville, sur un ton simple et artisan.
- Ce qui manque, on l'enlève proprement plutôt que de laisser un trou :
  · pas d'avis ni de note → supprime la section Avis, le badge de note et le lien « Avis » des menus ;
  · pas de photos avant/après → supprime les curseurs avant/après ;
  · moins de 4 photos de chantier → adapte la galerie, ou supprime-la s'il n'y en a aucune ;
  · pas de photos du tout → garde la photo d'accueil du template (utilitaire blanc) et remplace
    les photos de prestations par des blocs de couleur avec une grande icône ;
  · pas d'email → retire les liens email (pages légales : « par téléphone ») ;
  · pas de SIREN / adresse → remplace par « [à compléter] » uniquement dans les pages légales
    et le bas de page, pour que ce soit visible sur la V1.
- Garantie / assurance : n'en parle que si je l'ai confirmé ; sinon, réécris les 2 blocs « atouts »
  avec des arguments neutres (devis clair, chantier propre, interlocuteur unique, réactivité).
- Couleurs : celles que j'indique, sinon déduites du logo, du véhicule ou des photos ;
  à défaut, une palette sobre adaptée au métier.
- Logo : si j'en joins un, utilise-le ; s'il est visible sur une photo, redessine-le en SVG ;
  sinon fais un logo texte simple (nom + métier) aux couleurs choisies.
- Photos : recadre en 4/3, 1200 px max, JPG qualité 80, en gardant les noms du README.
- Le formulaire de devis reste sans clé Web3Forms sur la V1 (il invite à appeler) : c'est normal.
- Pousse sur la branche main, vérifie que le site s'affiche, et fais une capture mobile + ordinateur.

═══ À ME RENDRE ═══
1. Le lien du site en ligne.
2. Ce qui manque pour passer en V2 (liste courte).
3. Un message court et naturel à envoyer à l'artisan en réponse à son post ou en privé,
   avec le lien : je t'ai fait une maquette de site, gratuite, dis-moi ce que tu en penses.
```
