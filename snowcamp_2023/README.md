---
marp: true
theme: snowcamp2023
style: |
  section.titleslide h1 {
    color: #ffffff;
    position: absolute;
    top: 100px;
    left: 400px;
    font-size: 100px;
  }
  section.titleslide h2 {
    color: #ffffff;
    position: absolute;
    top: 200px;
    left: 400px;
    font-size: 50px;
  }
  section.titleslide p {
    color: #494c6f;
    margin: -400px 0 0 320px;
    font-size: 50px;
  }
  section.titleslide img {
    margin-left: 200px;
  }
  section.dividerslide h1 {
    color: #ffffff;
    margin-left: 100px;
    font-size: 100px;
  }
  section.dividerslide h2 {
    color: #ffffff;
    margin-left: 100px;
    font-size: 50px;
  }
# header: 'This is code. Fork it on [github.com/ojacques](https://github.com/ojacques)'
footer: '🐤 [@ojacques2](https://twitter.com/ojacques2), 🐤 [@angegar](https://twitter.com/angegar)'
---

![bg](assets/sc_bg_title.jpg)

<!-- _class: titleslide -->

# Platform Engineering

## Lorsque Kubernetes devient la clé du royaume

Laurent Gil - ATOS  
Olivier Jacques - AWS

<!--
Intro:
Bonjour à tous. Et merci d'être venu à notre conférence sur le Platform Engineering et Kubernetes.

Mais Laurent et moi on se pose la question:

-->

---

![bg 50%](assets/gartner-top-10-2023.png)

<!--
Vous êtes venus parceque que vous avez vu que Platform Engineering fait partie des tendances technologiques 2023, d'après Gartner ?
-->

---

<!-- markdown-link-check-disable -->
# Cycle de l'effervescence [Gartner](https://www.gartner.com/interactive/hc/4017202)
<!-- markdown-link-check-enable -->

<div class='center'>
<img src=assets/gartner-hype-cycle.jpg width=75%/>
</div>

<!--
Vous êtes venus parceque que vous avez vu que le Platform Engineering faisait partie des pratiques au tout début de leur vie sur le cycle de l'efferscence Gartner ?
-->

---

# DevOps est ☠️ ?

![bg right 60% ](assets/tweet_devops_is_dead.jpg)

<!--
Ou même, vous avez vu passer dans votre fil d'actualité que DevOps était mort, et comme votre titre sur votre badge est "DevOps", vous vous demandez par quoi vous allez le remplacer.

-->

---
<div class="container">
<div class="col">

![drop-shadow:0,5px,10px,rgba(0,0,0,.4) width:300px](assets/laurent.jfif)

<!-- markdown-link-check-disable -->
## [Laurent GIL](https://www.linkedin.com/in/laurent-gil/)
<!-- markdown-link-check-enable -->
![height:60px](assets/atos-logo.png)

DevOps Coach,
AWS Solution Architect,
Kubernetes evangelist

</div>

<div class="col">

![drop-shadow:0,4px,10px,rgba(0,0,0,.4) width:300px](assets/olivier.jfif)

<!-- markdown-link-check-disable -->
## [Olivier JACQUES](https://www.linkedin.com/in/olivierjacques/)
<!-- markdown-link-check-enable -->
![height:80px](assets/aws-logo.png)

Sr Cloud & DevOps Architect

</div>

</div>

<!--
Si vous vous posez ces questions, et bien vous êtes dans la bonne salle. Aujourd'hui, Laurent et moi même allons vous parler de l'ingénierie de plateformes (platform engineering), et comment et pourquoi Kubernetes peut fournir de solides fondations.

Je m'appelle Olivier Jacques, et je suis architecte Cloud & DevOps à AWS.
Je m'appelle Laurent Gil, ...

Laurent et moi, nous avons participé à la construction de plateformes, Laurent continue à le faire à Atos, et moi-même j'aide les clients d'AWS à construire leur propre plateforme. La plus grosse que nous ayons construit accueillait jusqu'à 30,000 builders et consistait à leur fournir tout ce qu'il faut pour définir, développer, tester, déployer et opérer les applications de notre entreprise. Cette plateforme - qui nous survécu puisque nous avons quitté l'entreprise depuis - comportait du Kubernetes, mais pas que. Et nous aurons l'occasion d'en reparler tout au long de cette présentation, car, il s'agit bien ici d'un retour d'expérience, et de convictions forgées au fur et à mesure depuis 2017.
-->

---

# Conclusion

(oui, autant partir sur la conclusion)

- Non, DevOps n'est pas mort
- Le Platform Engineering permet d'accélérer l'innovation
- Kubernetes comme plateforme de base

---

<!-- _class: dividerslide -->
![bg](assets/werner.jpg)

<br/><br/><br/><br/><br/><br/><br/>

# "You build it, you run it"
## (Tu le crées, tu l'opères)
## 2016, Dr Werner Vogels, CTO AWS

<!-- 
Je voulais remettre ici cette citation de Dr Werner Vogels, CTO d'AWS. "You Build it, you run it". C'est important, car c'est comme cela que nous opérons à AWS. Cela dit, tout n'est pas dit dans ces 6 mots. Pour opérer ainsi, les ingénieurs d'AWS ont besoin de plateformes. Pour construire et opérer les plus de 200 services distincts que compose AWS à ce jour, notre plateforme est bien évidemment AWS lui-même. Mais pas seulement. Nous avons aussi des plateformes construites au dessus d'AWS, par nos équipes, pour améliorer la productivité de nos équipes, standardiser, sécuriser, éviter de ré-inventer la roue, et surtout innover du mieux suivant ce que nos clients nous demandent. Et c'est là que le Platform Engineering entre en jeu.
-->

---

# "You build it, you run it" - cela veut dire quoi ?

<div class='center'>
<img src=assets/devops.excalidraw.png width="80%"/>
</div>

---

# 2 pizzas pour une équipe

<div class='center'>
<img src=assets/pizza1.excalidraw.png width=50% />
</div>

---

# 2 pizzas pour une équipe

<div class='center'>
<img src=assets/pizza2.excalidraw.png width=70% />
</div>

---

# 2 pizzas pour une équipe

<div class='center'>
<img src=assets/pizza3.excalidraw.png width=50% />
</div>

---

# Solution ?

<div class='center'>
<img src=assets/devopsplatform.excalidraw.png width=60% />
</div>

---

![orthographe](assets/spelling.excalidraw.png)

---

# Les plateformes

<div class='center'>
<img src=assets/platform_auto.jpg width=70% />
</div>

<!--
Les plateformes ne sont pas nouvelles. Par exemple, dans le monde de l'automobile, les plateformes ont révolutionné la façon dont les constructeurs automobiles développent et commercialisent leurs véhicules.
Volkswagen a lancé sa plateforme MQB en 2012. Cette plateforme a permis à Volkswagen de réduire le temps de développement de ses véhicules de 30% et de réduire les coûts de développement de 20%.

Nous devons pouvoir utiliser ce concept dans le monde du cloud. Sauf que... voyons la suite.
-->

---

# Définition - Plateforme

> "Les plateformes sont un moyen de centraliser l'expertise, tout en décentralisant l'innovation au client ou l'utilisateur"

Peter Gillard-Moss, ThoughtWorks

---

# Définition - Platform Engineering

> L'ingénierie des plateformes est la discipline qui consiste à concevoir et à créer des chaînes d'outils et des flux de travail qui permettent aux organisations d'ingénierie logicielle de disposer de capacités en libre-service à l'ère du "cloud-native". Les ingénieurs de plateforme fournissent un produit intégré, souvent appelé "*plateforme interne de développement*", qui couvre les besoins opérationnels de l'ensemble du cycle de vie d'une application.

[Luca Galante, platformengineering.org](https://platformengineering.org/blog/what-is-platform-engineering)

---

# Pourquoi construire une plateforme ?

- Réduire la charge cognitive
- Augmenter la productivité
- Forcer la standardisation

> Grandir les équipes, tout en préservant ce qui permet d'être productif: l'autonomie, avec un minimum de coordination et de l'infrastructure en self-service.

<!--
Les standards ne réduisent pas la créativité, mais ils la boostent. Se mettre d'accord sur certains standards permet de booster la créativité.
-->

---

![bg 110%](assets/team_topologies.png)
![bg drop-shadow:0,4px,10px,rgba(0,0,0,.4) 55%](assets/team_topologies_book.jpg)

---

![bg](assets/sc_bg_divider.jpg)

<!-- _class: titleslide -->
# Réussir une plateforme

---

# Caractéristiques d'une bonne plateforme

- Des utilisateurs !
- Facile à adopter
- Transparente dans sa gouvernance, son fonctionnement
- Responsabilité partagée (Inner Source)
- Flexible et extensible

---

# Un service

<div class='center'>
<img src=assets/service.excalidraw.png width=130% />
</div>

---

# Une plateforme

<div class='center'>
<img src=assets/platform.excalidraw.png height="130%"/>
</div>

<br/><br/>
⚠️ Une plateforme n'est pas un service

> Fournir une base de donnée "clé en main", n'est pas fournir une plateforme. C'est fournir un service.

---

![bg](assets/sc_bg_divider.jpg)

<!-- _class: titleslide -->
# Construire une plateforme
## avec Kubernetes

---

# A propos de Kubernetes

📖 Kubernetes est une plateforme open source extensible et portable pour la gestion de charges de travail (workloads) et de services conteneurisés📖

📖 Kubernetes a également été conçu pour servir de *plateforme* et favoriser la construction d’un écosystème de composants et d’outils facilitant le déploiement, la mise à l’échelle et la gestion des applications.📖

[source](https://kubernetes.io/fr/docs/concepts/overview/what-is-kubernetes/)

---

![bg right 100%](assets/k8sasplatform.excalidraw.png)

# Kubernetes comme plateforme framework

<!--
!!!! - Permet de changer le paradigme de pipeline (push pipeline devient pull pipeline) !!!!
- Bénéficie d'un écosystème très large permettant le monitoring, l'observabilité, la sécurité

-->

- Possède des qualités intrinsèques tel que
  - self service avec ses APIs
  - self-healing
  - robustness
- Simple d'utilisation grace à une approche déclarative
- Extensible par nature avec les controlleurs et les définitions de ressource personnalisé

---

![bg left 100%](assets/k8scontroller.excalidraw.png)

# Qu'est ce qu'un controlleur Kubernetes

**Un controlleur traque un type de ressource définissant un état souhaité afin de faire converger la plateform vers cet état.**

<!--
Et si les ressources étaient de type infrastructure ou encore des applications internes à l'entreprise.
-->

---

<!--
Présentation de l'écosystème qui fait de k8s un outil de choix pour réaliser une plateformz
-->
![bg left 70%](assets/platform-ci.excalidraw.png)

# Pour la CI / CD

- CI
  - [JenkinsX](https://jenkins-x.io/)
  - [Tekton](https://tekton.dev/)
- CD
  - [ArgoCD](https://argo-cd.readthedocs.io/en/stable/)
  - [Flux](https://fluxcd.io/)

---

![bg left 70%](assets/platform-test.excalidraw.png)

# Pour les tests

- kubernetes cluster virtuel (nodes et network partagés entre cluster physique et virtuel)
- Créer et détruire des environnements de test à la volée

---

![bg left 70%](assets/platform-infra.excalidraw.png)

# Pour gérer l'infrastructure

- [Crossplane](https://www.crossplane.io/)
- [AWS ACK Controller](https://aws.amazon.com/fr/blogs/containers/aws-controllers-for-kubernetes-ack/)
- [GCP Config Connector](https://cloud.google.com/config-connector/docs/overview)

---

![bg left 70%](assets/platform-monitoring.excalidraw.png)

# Monitoring des applications

- [Opentelemetry](https://opentelemetry.io/)
- [Grafana](https://github.com/grafana/grafana)
- [Dynatrace](https://www.dynatrace.com/)
- [Datadog](https://www.datadoghq.com/)

---

![bg left 70%](assets/platform-logging.excalidraw.png)

# Collecter les log de manière centrale

- [Fluentd](https://github.com/fluent/fluentd)
- [Loggie](https://github.com/loggie-io/loggie)

---

![bg left 70%](assets/platform-conformite.excalidraw.png)

# Gestion centralisée de la conformité

<!-- Réalisé au niveau de l'API via des webhooks -->

Instrumenter la stack Kubernetes pour forcer la conformité :

- [OPA Gatekeeper](https://github.com/open-policy-agent/gatekeeper) ([policy library](https://open-policy-agent.github.io/gatekeeper-library/website/allowedrepos))

- [Kyverno](https://github.com/kyverno/kyverno) ([policy library](https://kyverno.io/policies/?policytypes=Deployment))

---

![bg left 70%](assets/platform-securite.excalidraw.png)

# Gestion centralisée de la sécurité

- [KubeArmor](https://github.com/kubearmor/kubearmor) : at the system level
- [Trivy-Operator](https://github.com/aquasecurity/trivy-operator)
  
---

![bg](assets/sc_bg_divider.jpg)

<!-- _class: titleslide -->

# Bénéfices d'une plateforme

---

# Facilité d'intégration avec des outils internes

- Créer des définitions de ressource personnalisées
- Créer des controlleurs personnalisées permettant de piloter des outils internes

<!--
(ex: renseigner une base de référence d'application à partir de resources de type déploiment) 
-->

---

# Opérabilité

- Une seul language pour gérer une multitude de problèmes (infrastructure, application, monitoring ...)
- Une CLI commune à toutes les applications pour la recherche de problèmes
- Des fonctionnalités standards utilisés par toutes les équipes
- Portables à travers les clouds providers

---

![bg right:65% 100%](assets/pipelines.excalidraw.png)

# Améliorer le temps de reprise après sinistre (MTTR)

<!--

## Habituellement
 
- Cycle de vie infra séparé du cycle de vie de l'application
- Packagé séparément
- Utilise des languages différents => charge cognitive
- Dépendance entre pipeline (ex: storage, database, DNS,...)
- un pipeline pour l'infrastructure
- un pipeline pour l'applications

## Avec Kubernetes comme plateforme

- K8s et sa capacité à être étendu via des controlleurs
  résoud ces problèmes.
- un seul pipeline pour l'**infrastructure + application**.
- atomicité du déploiement
- **universal control plane**

-->

---

![bg left 90%](assets/pullpipeline.excalidraw.png)

# Passer des pipelines push au pull

<!--
- sécurité:
-   Sur un pipeline push les agents de l'orchestrateur ont souvent des droits étendus. Sur un pipeline pull, c'est l'environnement cible qui a des droits sur la CI.
- Pipeline push scale mal à travers plusieurs clusters
- YAML syntax permet d'utiliser le patterne app of app, ce qui permet de démarrer tout un cluster à partir d'un application bootstrap (mettre un example argocd)
-->

- Amélioration de la sécurité (gestion des permissions)
- Scalabilité des chaînes de déploiement
- Utilisation d'**outils GitOps** (Flux, Rancher Fleet, ArgoCD)

---
<!--
Developers should be able to deploy and run their apps and services end to end. “You build it, you run it”. True DevOps.
-->

Les développeurs doivent être capable de déployer et d'opérer leurs applications et services de bout en bout.

<br/><br/>
"You build it, you run it" - Tu le crées, tu l'opères
...au dessus d'une plateforme💡

---

# Littérature
<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>

![drop-shadow:0,4px,10px,rgba(0,0,0,.4) bg 40%](assets/team_topologies_book.jpg)
![drop-shadow:0,4px,10px,rgba(0,0,0,.4) bg 40%](assets/platform_strategy.png)

---

![Sponsors bg 100%](assets/sponsors.drawio.png)

---

![bg](assets/sc_bg_end.jpg)

<!-- _class: titleslide -->

# Merci

## 🐤 @ojacques2 🐤 @angegar
<br/><br/><br/><br/><img src=assets/feedback.jpg width="30%"/> <img src=assets/qr_code_slides.png width="30%"/>
