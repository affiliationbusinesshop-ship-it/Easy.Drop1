# easy.drop by EasyDrop — Site livré (FR / US / UK)

Site statique à 3 marchés, un dossier par marché, prêt à héberger (Netlify, Vercel, GitHub Pages, Hostinger...).

## Structure

```
index.html                → Landing page FR (easydrop.fr) — 45€
us/index.html              → Landing page US (easydrop.com/us) — $45
uk/index.html              → Landing page UK (easydrop.com/uk) — £45

merci.html / us/merci.html / uk/merci.html   → Pages de confirmation post-achat + bloc affiliation EBX
mentions-legales.html / us/legal-notice.html / uk/legal-notice.html
cgv.html / us/terms.html / uk/terms.html      → Placeholders à compléter avant mise en ligne

assets/style.css          → Feuille de style unique (vert #1A7A4C + noir/blanc, police Inter)

emails/fr/*.html            → 4 emails FR : confirmation, J+3, J+7, J+14
emails/us/*.html             → 4 emails US : confirmation, D+3, D+7, D+14
emails/uk/*.html             → 4 emails UK : confirmation, D+3, D+7, D+14
```

## Différences entre les 3 marchés

| | FR | US | UK |
|---|---|---|---|
| Prix | 45€ | $45 | £45 |
| Modules | 11 (Module 0 « Cadre légal » inclus) | 10 (pas de module légal — absent de la formation US) | 10 (pas de module légal — absent de la formation UK) |
| Toggle | FR actif → US / UK | US actif → FR / UK | UK actif → FR / US |
| Copy | Française, tutoiement | Anglais natif US | Anglais natif UK |

Le module « Cadre légal » n'existe que dans `Easy.Drop FR.pdf` (micro-entreprise, URSSAF). Il n'apparaît donc que sur la landing page FR, conformément aux 3 formations livrées (`Easy.Drop FR.pdf`, `Easy.DropUS.pdf`, `Easy.DropUK.pdf`).

## Ce qui est fait
- 3 landing pages one-page, mobile-first, structure identique (hero, problème, solution, modules, crédibilité, FAQ, CTA final, footer).
- Toggle FR/US/UK discret en haut à droite sur chaque page, fonctionnel dans les deux sens.
- Prix identique en valeur (45) affiché dans la devise du marché, jamais mélangé.
- Contenu des modules aligné sur les 3 PDF fournis (nombre de modules, absence du module légal en US/UK).
- Pages de confirmation post-achat (3) avec bloc affiliation EBX.
- 12 templates d'emails (4 FR + 4 US + 4 UK) prêts à copier-coller dans Systeme.io / Brevo / ConvertKit.

## Ce qu'il reste à brancher
1. **Paiement** : créer 3 produits (FR 45€ / US $45 / UK £45) dans Stripe, Gumroad ou Systeme.io, puis remplacer les `data-checkout-link="PASTE_STRIPE_OR_GUMROAD_LINK_FR/US/UK"` sur les boutons CTA de chaque `index.html`.
2. **Livraison du PDF** : héberger les 3 PDF de formation et remplacer `PASTE_PDF_FR_LINK` / `PASTE_PDF_US_LINK` / `PASTE_PDF_UK_LINK` dans les pages `merci.html` et les emails de confirmation correspondants.
3. **Automatisation email** : importer les 12 templates dans ton outil d'emailing, un déclencheur par marché (achat FR/US/UK), délais J+3/J+7/J+14 (ou D+3/D+7/D+14).
4. **Mentions légales / CGV / Terms** : compléter les informations réelles pour chaque marché (SIRET pour la FR, structure d'entreprise pour US/UK) — les pages actuelles sont des placeholders à ne pas publier telles quelles.
5. **Nom de domaine** : pointer `easydrop.fr` vers la racine, `easydrop.com/us` vers `us/`, `easydrop.com/uk` vers `uk/` (ou sous-domaines dédiés).

Le lien et le code affilié EBX (`ebx.army/aff-business` / `EBX-AFF-BUSINESS`) sont identiques sur les 3 marchés, partout où le brief le demande.
