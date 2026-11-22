# CHANTIERS — CRConum-V10

État au **22/11/2026**, code jusqu’à `e77890f`.

## Ce qu'est le projet

Voir `CLAUDE.md`. Publication : toujours sur `main` (décision du 13/11/2026).
AGORA installée le 13/11/2026 (`AGORA.md`, section « AGORA » de `CLAUDE.md`) :
chaque décision à trancher est candidate à un bloc.

## Décisions à trancher

Les deux corrections ont été validées par l’utilisateur le 22/11/2026.
Claude a rendu deux verdicts « amendé » au commit `e7d99fe`. Les deux écarts
reproduits ont été corrigés et vérifiés avec des données fictives dans Chromium.
Les blocs [AG-001 et AG-002](AGORA.md#blocs-tranchés) ont été clos le 22/11/2026
à la demande de l’utilisateur. Corrections déployées au commit `85d9073`.
Le téléchargement de secours conserve la valeur brute. Le retrait exige une
confirmation. Le bilan de reformulation affiche la cause et arrête le lot
après un refus d’accès.

## Contrôles et reprise

- **Brouillons** (`c3b1d41`). Sur l’accueil et en v10 à v12, « Annuler »
  conserve le brouillon. « Supprimer et commencer » ouvre un éditeur vide.
  La v13 vérifie l’écriture de la liste fusionnée avant de retirer l’ancienne
  copie. Les échecs de sauvegarde restent visibles. Chromium à 390 px avec
  des brouillons fictifs a couvert annulation, reprise, suppression explicite,
  coexistence des deux formats et reprise après un échec de stockage.
- **Reformuler tout** (`2b98756`). Le bilan compte les réponses appliquées.
  Le bouton « Réessayer » identifie les sections à relancer. Dans Chromium,
  les cinq pages ont passé les cas de réussite, échec partiel, échec complet
  et relance avec des réponses Anthropic fictives.

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
  déborde à 390 px. **Proton Pass sur téléphone : fonctionne** (confirmé par
  l'utilisateur le 13/11/2026, après reconstruction de Pages).
- « Sur `main` » ne veut pas dire « en ligne » : vérifier une construction Pages
  réussie sur le SHA poussé. Le 13/11/2026, aucun push de la session n'en a
  déclenché ; débloqué par l'utilisateur : Settings → Pages, Branch « None »
  puis « main » / root.
