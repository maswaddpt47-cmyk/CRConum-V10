# AGORA — CRConum-V10

Débats soumis à une **autre session Claude** (ou à Codex) pour contradiction.
Une session dépose ici une proposition ; une autre, qui n'a pas le même
contexte, lit les vrais fichiers et répond. Le canal est ce dépôt, pas le
compte Claude : deux comptes différents fonctionnent, à condition d'avoir accès
en écriture.

Quand soumettre et quand s'en abstenir : section « AGORA » de `CLAUDE.md`
(sept critères, exclusions). Installée le 13/11/2026.

## Pour répondre à un bloc

Les trois règles qui ne se déduisent pas du gabarit :

- **Jamais un bloc que l'on a soi-même ouvert.** S'auto-répondre produit un
  tampon de validation, pas une contradiction. **Avant de répondre, comparer
  le trailer `Claude-Session:` du commit qui a déposé le bloc
  (`git log -1 --format=%B <sha du bloc>`) à celui de la session courante** :
  il distingue deux sessions même sous une identité GitHub unique (mesuré le
  21/09/2026 sur un autre projet). Le champ `Auteur` n'est qu'un libellé de
  lecture — pas une preuve. Trailer absent (commit fait à la main) : demander
  à l'utilisateur.
- **Append-only**, `git pull --rebase origin main` juste avant de pousser, et
  on pousse **directement sur `main`** : deux sessions sur deux branches ne se
  voient pas.
- **Aucune donnée d'usager** dans un bloc : pas de ligne d'export, pas de log
  brut (MD-LIB `rgpd-securite.md`).

Le reste — les trois verdicts, la règle de preuve — est **dans le gabarit
ci-dessous**, il n'a pas à être répété ici.

**Le cycle** : une session dépose un bloc et le pousse sur `main`, donne à
l'utilisateur la phrase à coller ailleurs (« pull **maswaddpt47-cmyk/CRConum-V10**, lis son
`AGORA.md`, réponds à AG-00N, tu es la session B ») ou lui dit de dire « pull »
à Codex (`AGENTS.md`), le contradicteur répond, l'utilisateur tranche. **Aucune
notification ne passe d'un compte ou d'un outil à l'autre** : le relais par
l'utilisateur est obligatoire, et c'est pour ça que l'AGORA ne bloque jamais.

## Sincérité

1. **« Amendé » n'est valable que s'il nomme ce qui serait faux, manquant ou
   coûteux** si la proposition était appliquée telle quelle. Un amendement qui
   ne change ni code, ni décision, ni chiffre est un « confirmé ».
2. **« Confirmé » est une réponse pleine**, pas un aveu d'inutilité. Ne jamais
   chercher un amendement pour justifier sa présence.
3. **Aucune appréciation** de la proposition ni de son auteur : une réponse
   commence par un constat.

Le tableau des blocs tranchés porte le verdict et le total des trois issues.
**Le total est une alerte, pas un objectif** : le verdict découle de la
contrainte 1 appliquée au bloc, jamais de la série.

## Gabarit

```markdown
## AG-00N — Titre court — ouvert le JJ/MM/AAAA
**Auteur** : session <8 car. du trailer Claude-Session> — lu sur `<sha court>`
**Proposition** : trois lignes maximum.
**Critère déclencheur** : n° et lequel (`CLAUDE.md`, section « AGORA »).
**Contradicteur** : Codex | session B
**Ce que ça engage** : ce qui serait coûteux à défaire.
**Non vérifié par l'auteur** : le champ le plus important — dire où l'on est
faible oriente le contradicteur au lieu de le laisser valider par défaut.
**Si personne ne répond, je fais quoi ?** — si c'est « je continue pareil », le
bloc n'avait pas lieu d'être.
**Où regarder** : fichier.md:120-180

### Réponse — JJ/MM/AAAA
**Auteur** : session <autre id> — lu sur `<sha court>` (`git log --oneline -1`)
**Verdict** : confirmé | amendé | contredit
**Constat** : avec fichier:ligne, mesure ou log.
**Amendement** : ...

### Tranché le JJ/MM/AAAA — décision : ...
```

---

# Blocs ouverts

Aucun.

# Blocs tranchés

Total : 0 confirmé, 0 amendé, 0 contredit.
