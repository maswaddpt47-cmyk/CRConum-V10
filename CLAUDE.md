# Règles de travail — CRConum-V10

**Reprise de session : lire `CHANTIERS.md`** (état, décisions en attente, invariants).

Règles communes de collaboration : MD-LIB/collaboration.md, chargé
automatiquement par MD-LIB/CLAUDE.md (04/11/2026). Ici, seulement ce qui est
propre au projet.

## Le projet

Pages HTML autonomes de compte rendu de réunion (CR CONUM, CD47). Les notes
brutes sont reformulées par l'API Anthropic, appelée depuis le navigateur. La
clé API est chiffrée dans la page et déchiffrée par un mot de passe saisi à
l'accueil. `index.html` = `CR_CONUM_v10.html` ; v11 à v13 sont des versions
ultérieures. Une modification commune s'applique aux cinq fichiers.

## Publication — toujours sur `main`

Décision de l'utilisateur du 13/11/2026 : « Toujours dans main ». Malgré une
branche de session imposée, chaque livraison vérifiée part en avance rapide
sur `main`, sans redemander (MD-LIB `git-workflow.md` §3, « Main toujours ») :

```bash
git fetch origin main
git merge-base --is-ancestor origin/main HEAD && git push origin HEAD:main
git push origin HEAD
```

**Déploiement** : GitHub Pages depuis `main` (construction automatique
« pages build and deployment », site `maswaddpt47-cmyk.github.io`). **Constat du
13/11/2026** : les pushes de la session (`2e74931` à `434a195`) n'ont déclenché
aucune construction (cause inconnue ; dernière le 23/05/2026), le téléphone
servait l'ancienne page. Ne jamais écrire « en ligne » sans une construction
réussie **sur le SHA poussé** (MD-LIB `deploiement.md`).

## Tests

Pas de suite de tests. Vérification dans Chromium sans écran (Playwright),
avec un **faux** mot de passe seulement : le vrai ne passe jamais par Claude.

## Sécurité et données

- Le texte des notes part chez Anthropic : aucune donnée personnelle d'usager
  dans les notes (MD-LIB `charte-ia-cd47.md`). Brouillons, membres et réglages
  restent dans le `localStorage` du navigateur.
- Formulaire de connexion conforme à la règle 69 depuis le 13/11/2026 : ne pas
  remettre `onkeydown` ni `onclick` sur le champ ou le bouton (double appel).
- Constat de sécurité : contradicteur Codex (MD-LIB `agora.md` §12).

## Chiffres

Aucun chiffre calculé ni affiché au 13/11/2026 : l'outil produit un compte
rendu textuel. Toute nouvelle donnée enregistrée ou tout comptage (participants,
actions, durées) déclenche l'examen de la règle 57 et le critère 7 ci-dessous.

## AGORA

Faire contredire une proposition par une autre session, via `AGORA.md` à la
racine (installée le 13/11/2026). `MD-LIB/agora.md` n'est **pas requis pour
répondre** : `AGORA.md` porte les règles de réponse et le gabarit.

**Soumettre dès qu'un de ces faits est constaté** (vérifiable dans le diff) :
1. la décision ferme une porte (format de stockage, dépendance, contrat) ;
2. deux options envisagées, une seule écrite, sans arbitrage extérieur ;
3. trois itérations sans résolution sur le même problème ;
4. défaire un existant dont la raison d'être n'est pas retrouvée ;
5. la proposition contredit une note datée du dépôt ;
6. coût irréversible côté usager (perte de brouillons, données effacées) ;
7. le changement touche un calcul ou un chiffre affiché — systématique,
   contradicteur **Codex**, bloc ouvert avant la correction.

Toute « décision à trancher » de `CHANTIERS.md` est candidate : dire pourquoi
on ouvre un bloc ou non.

**Ne va pas à l'AGORA** : rendu pur ; correctif localisé appuyé sur une preuve
(sauf critère 7) ; ce qui se défait en un commit.

**Soumet d'office, ne bloque jamais** : la session ouvre le bloc sans
demander, l'annonce par 🔴 dans son message, donne la phrase de relais
(« pull **maswaddpt47-cmyk/CRConum-V10**, lis son `AGORA.md`, réponds à
AG-00N, tu es la session B », ou « pull » à Codex) et continue le travail
indépendant. L'utilisateur tranche.

**Codex** contredit les blocs de sécurité, de données personnelles et de
chiffres (critère 7) : l'IA qui écrit ne relit pas.
