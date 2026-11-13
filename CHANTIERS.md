# CHANTIERS — CRConum-V10

État au **13/11/2026**, base `2e74931` (`main`).

## Ce qu'est le projet

Voir `CLAUDE.md`. Publication : toujours sur `main` (décision du 13/11/2026).
AGORA installée le 13/11/2026 (`AGORA.md`, section « AGORA » de `CLAUDE.md`) :
chaque décision à trancher est candidate à un bloc.

## En cours (13/11/2026)

- Règle 69 testée sur téléphone : échec, mais sur l'**ancienne** page (Pages non
  reconstruit). Reconstruction demandée à l'utilisateur, puis nouvel essai.

## Décisions à trancher

Aucune au 13/11/2026.

## Pistes

- *Proposée, en attente (13/11/2026)* — la clé API chiffrée est dans des pages
  publiques : sa solidité ne dépend que du mot de passe (essais hors ligne
  possibles). Faire contredire par Codex (bloc de sécurité) avant de décider
  s'il faut un relais côté serveur.

## Points à ne pas défaire

- **Formulaire de connexion (règle 69, 13/11/2026)**, dans les 5 pages : champ
  `#mdp-input` dans `<form id="mdp-form" autocomplete="on" action="#">`, avec
  identifiant fixe hors écran (`name="username"`, valeur « CR CONUM - clé
  Anthropic ») et bouton `type="submit"`. Entrée et bouton passent par l'unique
  écouteur `submit` (en fin de script) : ne pas remettre `onkeydown`/`onclick`,
  sinon `startLive()` part deux fois. Vérifié dans Chromium le 13/11/2026 avec
  un faux mot de passe : un appel par Entrée, page non rechargée, rien ne
  déborde à 390 px. Proton Pass sur téléphone : non vérifié.
- « Sur `main` » ne veut pas dire « en ligne » : vérifier une construction Pages
  réussie sur le SHA poussé (aucune déclenchée par les pushes du 13/11/2026).
