# Réviser le code de test Java : CTAQ

Outil de révision interactif pour **apprendre à écrire de mémoire** le code de test Java vu en cours : JUnit 5, Hamcrest, Mockito, EasyMock, Cucumber et JaCoCo. L'objectif n'est pas seulement de lire le code, mais de le réécrire soi-même et de comprendre le rôle de chaque ligne.

**Application en ligne :** https://claude.ai/artifact/HS8oYbsoovuEMoJepdydvt
**Fichier source :** `quiz-code-ctaq.html` (une seule page, sans dépendance)

---

## Source du cours

Le contenu pédagogique provient du cours de **M. Pascal Poizat**, **Université Paris Nanterre**.

- Module : **CTAQ — Contrats, Tests et Assurance Qualité**
- Support : **« Outils de test »**, version 1.0 (septembre 2026), 55 slides
- Complément : un résumé personnel de l'étudiant (« Cour 5 : xUnit en Java : écrire et exécuter des tests »), construit à partir de ce support

Tout le code et les notions présentés dans le programme viennent de ce support et de ce résumé. Les droits sur le cours appartiennent à son auteur. Ce programme est un outil d'étude personnel, **non officiel**, sans lien avec l'université.

---

## Fonctionnement

Le parcours compte **18 modules** et **72 QCM**. Il existe deux modes, au choix en haut de la page.

### Mode « Ligne par ligne »
1. **Lire** : une ligne de code s'affiche, colorée, avec une explication adaptée à un débutant (mots-clés, fonctions, variables) et parfois un exemple ou un point à retenir.
2. **Réécrire** : la ligne disparaît, tu la réécris de mémoire à partir d'un indice (son rôle).
3. **Vérifier** : le programme compare ta réponse, surligne ce qui manque et barre ce qui est en trop. Tu ne passes à la suite que si la ligne est exacte.
4. **Rappel** : toutes les 3 lignes et en fin de module, une ligne vue plus tôt t'est redemandée.

### Mode « Bloc complet »
Tu réécris une classe, un test ou un extrait entier dans un éditeur coloré façon VS Code (thème sombre).
- L'éditeur s'ouvre avec un **squelette de commentaires repères** : un commentaire par ligne à écrire, avec son rôle et, pour les déclarations, le **nom de la classe ou de la méthode** à utiliser.
- Un bouton **Indice** affiche le premier mot de chaque ligne.
- La correction se fait **ligne par ligne** : lignes justes en vert, lignes fausses avec le détail, lignes manquantes ou en trop signalées.

### QCM
À la fin de chaque module, 2 à 7 questions testent la compréhension, avec une explication pour chaque réponse. Les propositions sont mélangées à chaque fois, et un score s'affiche en fin de quiz.

---

## Contenu des modules

| N° | Module | Notions principales |
|----|--------|---------------------|
| 1 | Les imports | `org`, `junit`, `jupiter`, `platform`, `static`, `*` ; JUnit Jupiter, Platform Suite, Hamcrest, Mockito, EasyMock, Cucumber, `java.util` |
| 2 | Anatomie d'un test | classe de tests, `@Test`, préparer / exécuter / vérifier, `assertEquals`, `assertThrows` |
| 3 | Fixture et cycle de vie | `@BeforeEach`, `@AfterEach`, `@BeforeAll`, `@AfterAll` |
| 4 | Ordre d'exécution | `@TestMethodOrder`, `OrderAnnotation`, `@Order` (import court et long) |
| 5 | Suites de tests | `@Suite`, `@SelectClasses`, `@SelectPackages` |
| 6 | Annotations utiles | `@DisplayName`, `@Disabled`, `@Tag`, `@Timeout`, `@ParameterizedTest`, `@ValueSource` |
| 7 | Hamcrest | `assertThat`, `hasSize`, `hasItem`, `containsInAnyOrder`, `not`, `allOf` |
| 8 | Fil rouge | interfaces `IPriceProvider`, `INotifier`, classe `OrderService` |
| 9 | Dummy | `DummyPriceProvider`, `DummyNotifier` |
| 10 | Fake | `InMemoryPriceProvider` (catalogue en mémoire) |
| 11 | Stub | `StubPriceProvider` (réponses écrites en dur) |
| 12 | Spy | `SpyNotifier` (journal des appels) |
| 13 | Mock | `MockNotifier` (attentes et `verifie()`) |
| 14 | Mockito | `mock`, `when`, `thenReturn`, `verify`, `never`, `any`, `eq`, `contains` |
| 15 | EasyMock | record, replay, verify, `niceMock`, `strictMock` |
| 16 | Gherkin | `Feature`, `Scenario`, `Given`, `When`, `Then` |
| 17 | Étapes et lanceur Cucumber | `@Given`, `@When`, `@Then`, `@Suite`, `@IncludeEngines`, `@ConfigurationParameter` |
| 18 | Couverture JaCoCo | configuration Gradle (Kotlin), commande `./gradlew test jacocoTestReport` |

---

## Règles de vérification

- L'**indentation** et les **espaces multiples** ne sont pas évalués.
- Les **commentaires** (`//`, `#`) ne sont pas à réécrire et sont ignorés.
- Le **nom des classes et méthodes que tu déclares** n'est pas évalué : il est donné en indice, et un autre nom est accepté.
- Tout le reste doit être **exact** : majuscules, guillemets, point-virgule, noms d'API (`assertEquals`, `thenReturn`…), noms utilisés lors d'un appel.

---

## Utilisation

**Clavier**

| Touche | Action |
|--------|--------|
| `Entrée` (mode ligne) | vérifier la ligne |
| `Ctrl + Entrée` (mode bloc) | vérifier le bloc |
| `Entrée` (mode bloc) | nouvelle ligne, indentation conservée |
| `Tab` | insérer 4 espaces |
| `Tab` sur un commentaire repère | efface le commentaire pour écrire ta ligne à la place |

**Navigation**
- Le menu déroulant et la barre de 15+ segments en haut permettent de sauter à un module.
- Ta position est **sauvegardée dans le navigateur** (stockage local). Elle est propre à l'appareil et au navigateur utilisés.

**Conseil de révision** : fais d'abord un module en mode « Ligne par ligne », puis refais-le en « Bloc complet », et vérifie-toi avec le QCM.

---

## Ce qui vient du support, et ce qui a été ajouté

- **Tiré du support / du résumé** : le code des modules 2 à 18 (tests, fixture, suites, annotations, imports Hamcrest et Cucumber, doublures, Mockito, EasyMock, Gherkin, étapes, JaCoCo) et les notions associées.
- **Ajouté pour compléter** (non présent tel quel dans le support) :
  - les imports de Mockito, d'EasyMock, de Cucumber (`io.cucumber...`), de `java.util` et les assertions une par une ;
  - l'exemple de classe `OrdreTest` avec `@Order(1)` et `@Order(2)` ;
  - les explications pédagogiques et les QCM, rédigés pour l'apprentissage.

---

## Points d'attention

- Dans le résumé, l'import des assertions est écrit `import org.junit.jupiter.api.Assertions.*;` **sans `static`**. Le programme demande la version avec `static` (`import static org.junit.jupiter.api.Assertions.*;`), nécessaire pour appeler `assertEquals(...)` directement. À vérifier avec le cours original.
- Les commentaires des slides (`// préparer`, `// vérifier`…) ne sont pas demandés.
- Les blocs et lignes de la page sont sensibles à la casse et à la ponctuation.
- La partie théorique du cours (vocabulaire : collaborateur, bouchon, pilote, état / interaction, C0 / C1…) est couverte par les **QCM**, pas par des exercices d'écriture.

---

## Technique

- Une seule page HTML, JavaScript natif, sans bibliothèque ni connexion réseau requise une fois chargée.
- Éditeur avec coloration syntaxique maison (Java, Kotlin, Gherkin, Bash), couleurs inspirées de VS Code Dark+.
- Vérification par comparaison caractère par caractère (mode ligne) et ligne par ligne (mode bloc).
- Sauvegarde de la progression dans le stockage local du navigateur.
- Fonctionnement vérifié par des tests automatiques sur un navigateur simulé : chargement des 18 modules, acceptation de tous les blocs de code, détection d'erreurs, QCM.

---

## Crédits

- **Cours et code source pédagogique** : Pascal Poizat, Université Paris Nanterre — module CTAQ, « Outils de test », v1.0 (09/2026).
- **Outil de révision** : réalisé à partir du support de cours et du résumé personnel de l'étudiant, avec l'aide de Claude (Anthropic).
