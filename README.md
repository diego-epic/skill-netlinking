# 🔗 netlinking-audit — Claude Skill

**Audit netlinking automatisé pour campagnes d'achat de liens** (Rocketlinks, Develink, Linkbroker, Getfluence, WhitePress, etc.)

Ce skill Claude permet d'auditer un site média candidat avant l'achat d'un backlink et produit une recommandation structurée **Go / Watch / No-Go** avec scoring, calibrée par rapport au profil de votre marque cliente.

---

## ✨ Ce que fait le skill

- **Phase 0 — Cadrage marque** : collecte automatique du profil de votre marque (Ahrefs DR, Semrush AS, Majestic TF/CF, profil d'ancres) pour calibrer l'audit en relatif et non en absolu
- **Audit en 9 étapes** : pré-qualification SERP, santé organique, autorité thématique, profil de liens entrants/sortants, qualité éditoriale, GSC si dispo, risques, validation commerciale
- **Grille de scoring pondérée** (0-10 sur 9 familles de critères) → verdict Go / Watch / No-Go
- **Détection des red flags éliminatoires** : actions manuelles, PBN, domaines recyclés, voisinages toxiques
- **Rapport Markdown** prêt à archiver dans un registre d'achats
- **Compatible MCP** : utilise Firecrawl, Claude in Chrome, web_search et GSC quand disponibles

---

## 📦 Installation

### 1. Télécharger le skill

Téléchargez le fichier `netlinking-audit.skill` depuis la dernière [Release](../../releases/latest).

### 2. Préparer votre Claude

Sur [claude.ai](https://claude.ai) :

1. Allez dans **Settings > Capabilities**
2. Activez **Code execution and file creation**
3. Activez **Skills**

### 3. Uploader le skill

1. Allez dans **Customize > Skills**
2. Cliquez sur **"+"** puis **"+ Upload skill"**
3. Sélectionnez le fichier `netlinking-audit.skill` téléchargé
4. Le skill apparaît dans votre liste — activez-le via le toggle

> **Astuce** : si l'upload échoue, renommez `netlinking-audit.skill` en `netlinking-audit.zip` (le contenu est identique) et réessayez.

---

## 🚀 Utilisation

Le skill se déclenche automatiquement dès que vous mentionnez dans une conversation :

- *"Je veux auditer ce site avant d'acheter un lien sur Rocketlinks"*
- *"Est-ce que [URL] vaut le coup en netlinking ?"*
- *"Aide-moi à choisir entre ces 3 spots sur Develink"*
- *"Je prépare une campagne netlinking pour [marque]"*

### Exemple de prompt

```
Je lance une campagne netlinking pour [nom de marque] (secteur, niveau YMYL)
sur Rocketlinks. J'ai déjà la recherche de médias ouverte dans Chrome
et Claude in Chrome est actif.

Déclenche le skill netlinking-audit. Workflow attendu :

1. Phase 0 — Profil marque : navigue sur mon site, déduis la thématique
   et demande-moi mes métriques Ahrefs / Semrush / Majestic (screenshot
   ou navigation directe via Claude in Chrome si je donne permission).

2. Phase 1 — Sélection : parcours la liste de médias ouverte, extrais les
   candidats pertinents et pré-filtre selon mon profil marque.

3. Phase 2 — Audit : pour les 3-5 meilleurs candidats, déroule la séquence
   complète et produis pour chacun une fiche Go / Watch / No-Go avec score.

4. Livrable : tableau comparatif + fiche détaillée par candidat,
   classés par rapport score/prix.
```

---

## 🧰 Outils MCP recommandés (optionnels)

Le skill fonctionne avec les MCPs suivants quand ils sont connectés à votre Claude :

- **Firecrawl** — scraping rapide des articles candidats pour analyse éditoriale
- **Claude in Chrome** — navigation sur vos comptes Ahrefs / Semrush / Majestic (avec permission)
- **web_search** — opérateurs `site:`, vérifications de réputation
- **Google Search Console** — diagnostic profond si vous avez accès au GSC du média candidat
- **DataForSEO** — vérification trafic et profil de liens

Sans MCP, le skill fonctionne aussi sur la base de screenshots et données copier-coller.

---

## 📂 Structure du skill

```
netlinking-audit/
├── SKILL.md                          # Instructions principales (méthode + grille)
└── references/
    ├── brand-profiling.md            # Procédure Phase 0 (collecte profil marque)
    ├── serp-operators.md             # Bibliothèque opérateurs Google site:
    ├── red-flags.md                  # Catalogue des red flags par sévérité
    └── scoring-rubric.md             # Grille de scoring détaillée 0-10
```

---

## 🤝 Contribution

Suggestions, retours d'usage, ajout d'opérateurs SERP ou de red flags : ouvrez une issue ou une PR.

---

## 📜 Licence

MIT — usage libre, commercial inclus. Crédit apprécié mais non requis.

---

## 👤 Auteur

Créé par [@diego-epic](https://github.com/diego-epic) — consultant SEO/GEO freelance.

Si ce skill vous est utile, une ⭐ sur le repo aide d'autres SEOs à le trouver.
