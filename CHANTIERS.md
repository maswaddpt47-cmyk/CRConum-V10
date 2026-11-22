# CHANTIERS — CRConum-V10

État au **13/11/2026**, base `7191268` (`main`, en ligne : Pages réussi).

## Ce qu'est le projet

Voir `CLAUDE.md`. Publication : toujours sur `main` (décision du 13/11/2026).
AGORA installée le 13/11/2026 (`AGORA.md`, section « AGORA » de `CLAUDE.md`) :
chaque décision à trancher est candidate à un bloc.

## Décisions à trancher

Aucune au 13/11/2026.

## Pistes

- *Proposée (22/11/2026)* — **Protéger les brouillons à l'ouverture.** Sur la
  page d'accueil et les pages v10 à v12, « Annuler » à la question de reprise
  efface le brouillon (reproduit dans Chromium avec un brouillon fictif).
  En v13, le chargement d'un ancien brouillon remplace la liste existante et
  supprime la source avant l'écriture (reproduit avec un stockage fictif).
  Garder le brouillon tant qu'aucune suppression explicite n'est confirmée.
  En v13, réunir les brouillons sans doublon et vérifier l'enregistrement
  avant de retirer l'ancienne copie. Cela évite de perdre des notes en
  ouvrant l'outil. Prévoir 1 à 2 jours, reprise et essais compris, en
  conservant les formats actuels.

- *Proposée (22/11/2026)* — **Fiabiliser le bilan de « Reformuler tout ».**
  Dans les cinq pages, un appel fictif en échec a déclenché un message
  d'erreur suivi de « 1 section reformulée ✓ », avec un résultat vide.
  Compter les réussites, signaler les sections en échec et permettre de les
  relancer avec leur bouton existant. Cela évite de prendre un compte rendu
  incomplet pour un résultat prêt à relire. Prévoir 2 à 4 h en conservant l'API
  et l'export actuels.

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
  déborde à 390 px. **Proton Pass sur téléphone : fonctionne** (confirmé par
  l'utilisateur le 13/11/2026, après reconstruction de Pages).
- « Sur `main` » ne veut pas dire « en ligne » : vérifier une construction Pages
  réussie sur le SHA poussé. Le 13/11/2026, aucun push de la session n'en a
  déclenché ; débloqué par l'utilisateur : Settings → Pages, Branch « None »
  puis « main » / root.
