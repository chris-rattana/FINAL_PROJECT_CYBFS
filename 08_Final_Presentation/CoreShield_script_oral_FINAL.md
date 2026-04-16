# Script oral — CoreShield  
## Présentation finale CYBFS-FT-16

**Projet :** CoreShield  
**Présentateur :** Christophe Rattana  
**Support associé :** `CYBFS_CoreShield_Presentation_FINALE.pptx`  
**Durée cible :** environ 10 minutes

---

## Conseils généraux avant la présentation

L’objectif n’est pas de lire mécaniquement le texte, mais de garder une trame claire.

Le fil conducteur à conserver pendant toute la soutenance est :

**Déployer. Sécuriser. Superviser. Valider.**

Il faut bien distinguer les idées suivantes :

- CoreShield est un **lab cyber compact**, pas une infrastructure entreprise complète.
- Le projet est **réellement déployé**, avec 4 machines virtuelles.
- Deux services métier sont livrés : une application web et Nextcloud.
- Trois serveurs sont supervisés par Wazuh.
- Les résultats sont appuyés par un pack de preuves techniques.

---

# Slide 1 — Page de garde

**Temps cible : 40 à 45 secondes**

Bonjour à toutes et à tous.

Aujourd’hui, je vous présente **CoreShield**, mon projet final réalisé dans le cadre de la promo **CYBFS-FT-16**.

L’objectif était de construire un **lab cyber court, clair, fonctionnel et supervisé**.

Le fil conducteur est résumé par quatre verbes :

**Déployer. Sécuriser. Superviser. Valider.**

Je ne voulais pas présenter uniquement une architecture théorique. L’objectif était de construire un environnement réellement fonctionnel, avec des services accessibles, une supervision centralisée, et des preuves techniques permettant de valider chaque partie du projet.

---

# Slide 2 — CoreShield en un coup d’œil

**Temps cible : 55 secondes à 1 minute**

Cette slide présente la vue globale du projet.

CoreShield repose sur **4 machines virtuelles**, chacune avec un rôle précis.

La première est **dc01**, qui sert de base de confiance pour l’environnement, avec l’identité, l’annuaire et le DNS interne.

La deuxième est **app01**, qui est le nœud applicatif. Elle héberge une application web avec **Nginx, Gunicorn, Flask**, et une validation PostgreSQL.

La troisième est **file01**, qui fournit une plateforme collaborative avec **Apache2, MariaDB et Nextcloud**.

Enfin, la quatrième est **sec01**, qui centralise la supervision avec **Wazuh manager, indexer et dashboard**.

Le fil conducteur est simple : **séparer les rôles, valider les services, centraliser la visibilité sécurité et documenter chaque résultat par des preuves**.

---

# Slide 3 — Architecture opérationnelle

**Temps cible : 55 secondes à 1 minute**

Ici, on voit l’architecture opérationnelle.

J’ai utilisé deux réseaux.

Le premier est le réseau **NAT en 192.168.86.0/24**. Il sert principalement à l’administration depuis ma machine hôte, notamment avec SSH. C’est ce réseau que j’ai utilisé pour déployer, configurer et maintenir les machines virtuelles.

Le deuxième est le **LAN interne de services en 192.168.120.0/24**. C’est le réseau utilisé pour les échanges entre les machines.

Sur ce LAN interne, on retrouve :

- **dc01** en `192.168.120.10`, pour l’identité et le DNS ;
- **app01** en `192.168.120.20`, pour l’application web ;
- **file01** en `192.168.120.30`, pour la collaboration ;
- **sec01** en `192.168.120.40`, pour Wazuh et la supervision.

Les flux importants sont les flux DNS via **dc01**, et les flux Wazuh des agents vers **sec01**.

Cette séparation rend l’infrastructure plus lisible et plus réaliste.

---

# Slide 4 — Déploiement VMware

**Temps cible : 45 à 50 secondes**

Cette slide montre la partie déploiement VMware.

Les quatre nœuds ont été créés, démarrés, configurés, puis stabilisés avec des snapshots.

L’objectif des snapshots était de garder des points de retour propres après les étapes importantes.

On retrouve donc :

- **dc01** pour l’identité et le DNS ;
- **app01** pour l’application web ;
- **file01** pour le partage de fichiers ;
- **sec01** pour la supervision Wazuh.

Cette étape est importante, car elle montre que le projet a réellement été déployé. Il ne s’agit pas seulement d’un schéma ou d’une intention.

On voit aussi que les preuves visuelles ont été conservées : état des VM, configuration VMware et snapshots de validation.

---

# Slide 5 — Services livrés 1/2

**Temps cible : 45 à 50 secondes**

Cette slide présente le premier service livré : **app01**.

app01 est la machine dédiée à l’application web.

Elle repose sur une stack simple mais cohérente :

- **Nginx** en frontal ;
- **Gunicorn** en backend ;
- **Flask** pour l’application.

L’application expose aussi deux endpoints utiles :

- `/healthz`, qui permet de vérifier rapidement que le service répond ;
- `/db-check`, qui permet de vérifier la connectivité PostgreSQL.

J’ai également installé l’agent Wazuh sur app01, ce qui permet de superviser cette machine depuis sec01.

La capture montre la version finale de la page web, avec le thème CoreShield, un rendu plus cyber et une présentation plus professionnelle du nœud applicatif.

---

# Slide 6 — Services livrés 2/2

**Temps cible : 45 à 50 secondes**

Le deuxième service métier livré est **file01**.

file01 est la machine dédiée à la collaboration et au partage de fichiers.

Elle héberge **Nextcloud**, avec **Apache2** et **MariaDB**.

L’objectif était d’avoir un vrai service utile, représentatif d’un besoin d’entreprise : stocker, partager et accéder à des documents.

Nextcloud a été validé à la fois par l’accès navigateur et par la commande `occ status`, qui confirme l’état de l’installation.

Comme app01, file01 est aussi supervisée par Wazuh grâce à un agent actif.

Cette slide montre donc que CoreShield ne livre pas seulement une application web, mais aussi un service collaboratif complet.

---

# Slide 7 — Supervision centralisée avec Wazuh

**Temps cible : 1 minute à 1 minute 10 secondes**

Cette slide présente la couche la plus orientée cybersécurité du projet : la **supervision centralisée avec Wazuh**.

Wazuh est installé sur **sec01** en mode all-in-one, avec le manager, l’indexer et le dashboard.

Les trois autres serveurs — **dc01**, **app01** et **file01** — remontent leurs informations vers sec01 grâce aux agents Wazuh.

On obtient donc **3 agents actifs** dans le dashboard.

L’intérêt est important : on ne se contente pas d’avoir des machines qui fonctionnent, on obtient aussi une visibilité centralisée sur leur état.

La capture montre aussi un exemple d’alerte. Même si le projet reste compact, cela démontre déjà une logique de supervision et d’observabilité.

En résumé, **Wazuh transforme l’infrastructure en environnement supervisé**.

---

# Slide 8 — Validation et preuves 1/2

**Temps cible : 50 à 55 secondes**

Cette slide explique la logique du pack de preuves.

L’idée est simple : **je ne déclare pas seulement que ça fonctionne, je le prouve**.

Chaque affirmation importante du projet est associée à une preuve concrète.

Par exemple, pour **dc01**, j’ai vérifié l’écoute du port **53**, ce qui confirme le rôle DNS.

Pour **app01**, j’ai vérifié les réponses HTTP locales, notamment avec `curl`, pour m’assurer que le service web répondait correctement.

L’objectif est donc de relier chaque résultat à une preuve : une commande, un statut système, une capture de navigateur ou une vérification de port.

Cette logique permet de présenter un projet non seulement fonctionnel, mais aussi documenté et vérifiable.

---

# Slide 9 — Validation et preuves 2/2

**Temps cible : 55 secondes à 1 minute**

Cette deuxième slide de validation présente les catégories de preuves collectées.

D’abord, les **accès validés** : l’application web, Nextcloud et Wazuh sont accessibles depuis le navigateur.

Ensuite, les **services vérifiés** : j’ai utilisé des commandes comme `systemctl status`, `curl`, ou encore `occ status` pour Nextcloud.

Enfin, les **ports contrôlés** :

- le DNS sur le port **53** ;
- le HTTP sur le port **80** ;
- les ports Wazuh comme **443**, **1514**, **1515** et **55000**.

On voit aussi des preuves spécifiques : le manager Wazuh fonctionne sur sec01, et Nextcloud est validé sur file01.

Cette partie montre que le projet a été testé sous plusieurs angles : accès utilisateur, état des services, réseau et supervision.

---

# Slide 10 — Choix de conception sécurité

**Temps cible : 1 minute à 1 minute 10 secondes**

Ici, je ne décris plus les machines. Je prends du recul sur les **choix de conception sécurité** derrière l’architecture.

La sécurité n’est pas traitée uniquement comme une liste d’outils. Elle est intégrée dans la structure du projet.

Premier choix : la **séparation des rôles**. L’identité, l’application, la collaboration et la supervision sont portées par des nœuds différents. Cela rend l’environnement plus clair, plus facile à analyser et plus réaliste.

Deuxième choix : l’**exposition maîtrisée**. Les services attendus sont accessibles, mais l’administration reste contrôlée via le réseau NAT.

Troisième choix : l’**observabilité centralisée**. Wazuh donne une vision consolidée de dc01, app01 et file01 depuis sec01.

Le message clé est que CoreShield reste volontairement compact, mais il démontre une démarche défendable : architecture claire, services prouvés, supervision active et preuves organisées.

---

# Slide 11 — Évolutions possibles

**Temps cible : 55 secondes à 1 minute**

Cette slide ouvre sur les évolutions possibles du projet.

La première évolution serait le **durcissement réseau**, avec des règles firewall plus fines, une segmentation plus stricte et un filtrage inter-services.

La deuxième serait d’intégrer un vrai cycle **Red Team / Blue Team** : utiliser un audit externe, formaliser les vulnérabilités, mettre en place un plan de remédiation, puis retester.

La troisième évolution serait l’**automatisation** : scripts de déploiement, sauvegarde, restauration et contrôles de conformité.

Enfin, la supervision pourrait être renforcée avec des règles Wazuh personnalisées, de l’alerting ciblé et des tableaux de bord orientés incidents.

L’idée serait donc de passer d’un lab validé à une plateforme plus automatisée, plus durcie et plus proche d’un cycle SOC complet.

---

# Slide 12 — Résultat final

**Temps cible : 50 à 55 secondes**

Pour conclure techniquement, CoreShield est une infrastructure **déployée, opérationnelle, supervisée et documentée par des preuves**.

Le résultat final se résume en quatre points.

D’abord, **4 VM opérationnelles**.

Ensuite, **2 services métier livrés** : l’application web et Nextcloud.

Puis, **3 agents Wazuh actifs**, ce qui montre que l’environnement est supervisé.

Enfin, **1 pack de preuves complet**, qui documente les accès, les statuts, les ports, les captures et la supervision.

Ce que le projet démontre, c’est ma capacité à construire une infrastructure cohérente, à livrer des services réels, à mettre en place une supervision centralisée et à prouver techniquement l’état final.

La démarche se résume donc à : **déployer, sécuriser, superviser et valider**.

---

# Slide 13 — Merci / Questions

**Temps cible : 25 à 30 secondes**

Je termine en remerciant les instructeurs, les Teaching Assistants et toute la cohorte pour l’accompagnement tout au long de la formation.

Ce projet m’a permis de travailler à la fois sur le déploiement d’infrastructure, la mise en place de services, la supervision sécurité et la validation par preuves.

Merci pour votre attention.

Je suis maintenant disponible pour vos questions.

---

# Timing conseillé

| Slide | Temps cible |
|---|---:|
| 1 — Page de garde | 0:40–0:45 |
| 2 — CoreShield en un coup d’œil | 0:55–1:00 |
| 3 — Architecture opérationnelle | 0:55–1:00 |
| 4 — Déploiement VMware | 0:45–0:50 |
| 5 — Services livrés 1/2 | 0:45–0:50 |
| 6 — Services livrés 2/2 | 0:45–0:50 |
| 7 — Supervision Wazuh | 1:00–1:10 |
| 8 — Validation et preuves 1/2 | 0:50–0:55 |
| 9 — Validation et preuves 2/2 | 0:55–1:00 |
| 10 — Choix sécurité | 1:00–1:10 |
| 11 — Évolutions possibles | 0:55–1:00 |
| 12 — Résultat final | 0:50–0:55 |
| 13 — Merci / Questions | 0:25–0:30 |

**Total visé :** environ 10 minutes.

---

# Questions probables du jury et réponses courtes

## Pourquoi avoir choisi Wazuh ?

Wazuh permet une supervision centralisée open-source, adaptée à un lab cyber. Il permet d’installer des agents, de centraliser les événements et d’avoir un dashboard de monitoring.

## Pourquoi avoir utilisé 4 VM ?

Pour séparer les rôles : identité, application, collaboration et supervision. Cette séparation rend l’architecture plus claire, plus réaliste et plus facile à valider.

## Quelle est la limite principale du projet ?

Le projet reste un lab compact. Il n’intègre pas encore de haute disponibilité, de firewalling avancé ou d’automatisation complète.

## Quelle serait l’évolution prioritaire ?

L’évolution prioritaire serait le durcissement réseau, puis l’intégration d’un cycle Red Team / Blue Team avec remédiation et retest.

## Est-ce une infrastructure complète d’entreprise ?

Non. C’est une infrastructure de démonstration cyber. Elle est volontairement compacte, mais elle est déployée, supervisée, testée et documentée par des preuves.
