# CHANTIERS — CRConum-V10

État au **13/11/2026**, base `b8a8732` (dernier commit de `main` avant cette session).

## Ce qu'est le projet

Pages HTML autonomes de compte rendu de réunion (CR CONUM), reformulation par
l'API Anthropic. La clé API est chiffrée dans la page et déchiffrée par un mot
de passe saisi à l'accueil. `index.html` est identique à `CR_CONUM_v10.html`
(mesuré par `cmp` le 13/11/2026) ; v11 à v13 sont des versions ultérieures.

## Décisions à trancher

1. **Pas de `CLAUDE.md` ni d'`AGORA.md`** : à installer (MD-LIB `agora.md` §13,
   section « Chiffres » de la règle 57). Proposé le 13/11/2026, en attente.
2. **Publication** : aucune règle écrite. Le 13/11/2026, travail poussé sur la
   branche de session `ccr-9cc4c72d-djzns5` avec PR brouillon ; fusion dans
   `main` à décider par l'utilisateur.

## Points à ne pas défaire

- **Formulaire de connexion (règle 69, 13/11/2026)**, dans les 5 pages : champ
  `#mdp-input` dans `<form id="mdp-form" autocomplete="on" action="#">`, avec
  identifiant fixe hors écran (`name="username"`, valeur « CR CONUM - clé
  Anthropic ») et bouton `type="submit"`. Entrée et bouton passent par l'unique
  écouteur `submit` (en fin de script) : ne pas remettre `onkeydown`/`onclick`,
  sinon `startLive()` part deux fois. Vérifié dans Chromium le 13/11/2026 :
  un appel par Entrée, page non rechargée, rien ne déborde à 390 px.
- Consignes Codex (`AGENTS.md`) alignées sur MD-LIB le 13/11/2026 :
  autorisations, tests avant push, fin de tâche, champ de jeton.
