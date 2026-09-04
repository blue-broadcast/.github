# Contribuer à BlueBroadcast

Merci de l'intérêt. Ce guide s'applique à **tous les dépôts** de l'organisation
sauf mention contraire dans le dépôt concerné.

## Où poster quoi

| Sujet | Endroit |
|---|---|
| Idée, proposition de conception, **RFC** (nouveau profil, extension protocole) | **Issue** sur le dépôt concerné, label `enhancement` |
| Question d'usage | **Issue** sur le dépôt concerné, label `question` |
| Bug reproductible | **Issue** sur le dépôt concerné, gabarit *Bug* |
| Correctif ou fonctionnalité | **Pull Request** sur le dépôt concerné |
| Vulnérabilité de sécurité | **PAS d'issue publique** - voir [`SECURITY.md`](SECURITY.md) |

## Licences - à savoir avant de contribuer

| Dépôt | Licence | Ce que ça implique |
|---|---|---|
| `omt-android` - **SDK** (`omt-sdk/`) | **Propriétaire** (CLUF) | pas de contribution externe de code SDK ; issues et retours bienvenus |
| `omt-android` - `sample-app/`, outillage | MIT | PR bienvenues |
| `omtplugin` | GPL-2.0 | toute contribution est sous GPL-2.0 |
| `libomtnet` (fork) | MIT | toute contribution est sous MIT |
| `omt-h264` (proposition) | CC-BY | proposition de spec + démo, destinée à l'amont OMT |

En ouvrant une PR, tu confirmes avoir le droit de soumettre le code sous la
licence du dépôt.

## Pull Requests

1. **Une PR = un sujet.** Décris le *quoi* et le *pourquoi*, pas seulement le *comment*.
2. Respecte le style du dépôt. Pour `omt-android` : commentaires et logs **en
   français**, `./gradlew` doit rester vert (`:omt-sdk:apiCheck` compris pour
   toute modif Kotlin publique).
3. Ajoute/adapte les tests quand le comportement change.
4. Lie l'issue d'origine.

## Style de commit

Conventional Commits (`feat:`, `fix:`, `build:`, `docs:`, `refactor:`…),
messages courts, dans la langue du dépôt.

## La proposition H.264 (`omt-h264`)

C'est une **proposition de standard**. Le but final est une soumission en amont
à [openmediatransport](https://github.com/openmediatransport). Les retours sur
le FourCC, le format de trame et la **négociation de capacités** sont les plus
utiles - ouvre une issue `enhancement` sur `omt-h264`.
