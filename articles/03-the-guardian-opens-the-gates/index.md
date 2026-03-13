# Le gardien ouvre les portes / The Guardian Opens the Gates

*nextAIgeneration.org — 13 mars 2026*

---

## FR — Le gardien ouvre les portes

Ce matin, nous avons publié l'article #02 : Perplexity active un orchestrateur sur notre société belge sans consentement. 400+ connecteurs, 20 modèles, opt-out au lieu d'opt-in.

En enquêtant, nous avons découvert quelque chose de pire.

### Le gardien

Notre outil de développement AI avait dans sa configuration des permissions accordées automatiquement vers Perplexity et d'autres services tiers. L'éditeur de notre outil avait branché ces services directement dans notre environnement de travail. Via le protocole MCP (Model Context Protocol). Sans demande explicite de notre part.

### Le même pattern, une couche plus profonde

| Acteur | Action | Mécanisme |
|--------|--------|-----------|
| **Le service tiers** | Active un produit sur notre entreprise | Email, opt-out |
| **L'éditeur de l'outil** | Branche le service tiers dans nos outils | MCP, permission auto |

L'intrus ne force pas la porte. Le gardien la laisse ouverte.

### Ce que nous avons trouvé

En nettoyant la machine :

- **Containers applicatifs** avec des symlinks vers les dossiers personnels — l'application avait accès à Desktop, Downloads, Documents
- **Données partagées** entre extensions via Group Containers
- **Canaux de communication inter-processus** (XPC)
- **Données de session** dans le navigateur
- **Caches** dans les logs de l'outil de développement
- **Un token d'authentification invalide** injecté dans l'environnement — le vrai token, géré par notre infrastructure, fonctionnait

### Le site vitrine : l'AI expose ce qu'elle construit

Notre propre site public affichait des détails techniques internes : ports de services, noms de bases de données, architecture réseau, outils utilisés.

Qui avait construit ce site ? Nous. Avec l'aide de notre outil AI. Le même outil qui avait des services tiers branchés dans ses connecteurs.

Le machine learning ne voit pas le danger. Il optimise la réponse, pas la sécurité. Il dit "c'est beau" quand il devrait dire "c'est exposé."

### Trois couches, même direction

```
INTRUS          Le service tiers active un produit sur votre entreprise
    ↑ branché par
GARDIEN         L'éditeur de l'outil branche le service dans vos outils
    ↑ exécuté par
MACHINE         Le ML ne voit pas le danger, il acquiesce
```

Chaque couche protège la précédente. Le ML endort la vigilance. Le gardien ouvre la porte. L'intrus entre.

### Ce que nous avons fait

1. Supprimé toutes les traces du service tiers de nos machines
2. Retiré les permissions MCP non sollicitées de notre outil de développement
3. Nettoyé le site public — zéro information technique exposée
4. Publié cet article

### La question

Si vous utilisez un outil AI pour travailler :

- **Quels connecteurs sont actifs dans votre environnement ?**
- **Quelles permissions ont été accordées sans que vous le demandiez ?**
- **Votre outil envoie-t-il vos requêtes à des tiers que vous n'avez pas choisis ?**
- **Ce que l'AI construit pour vous expose-t-il ce qu'elle sait de vous ?**

Le gardien est censé protéger la maison. Pas ouvrir les fenêtres.

---

## EN — The Guardian Opens the Gates

This morning, we published article #02: Perplexity activated an AI orchestrator on our Belgian company without consent. 400+ connectors, 20 models, opt-out instead of opt-in.

While investigating, we found something worse.

### The guardian

Our AI development tool had permissions automatically granted to Perplexity and other third-party services in its configuration. The tool's publisher had plugged these services directly into our work environment. Via the MCP protocol (Model Context Protocol). Without our explicit request.

### Same pattern, one layer deeper

| Actor | Action | Mechanism |
|-------|--------|-----------|
| **Third-party service** | Activates a product on our company | Email, opt-out |
| **Tool publisher** | Plugs the service into our tools | MCP, auto-permission |

The intruder doesn't force the door. The guardian leaves it open.

### What we found

While cleaning the machine:

- **Application containers** with symlinks to personal folders — the app had access to Desktop, Downloads, Documents
- **Shared data** between extensions via Group Containers
- **Inter-process communication channels** (XPC)
- **Session data** in the browser
- **Caches** in the development tool's logs
- **An invalid authentication token** injected into the environment — the real token, managed by our own infrastructure, worked fine

### The showcase site: AI exposes what it builds

Our own public website displayed internal technical details: service ports, database names, network architecture, tools used.

Who built this site? We did. With the help of our AI tool. The same tool that had third-party services plugged into its connectors.

Machine learning doesn't see danger. It optimizes the response, not the security. It says "looks great" when it should say "this is exposed."

### Three layers, same direction

```
INTRUDER        Third-party activates a product on your company
    ↑ plugged by
GUARDIAN        Tool publisher plugs the service into your tools
    ↑ executed by
MACHINE         The ML doesn't see the danger, it acquiesces
```

Each layer protects the previous one. The ML numbs your vigilance. The guardian opens the door. The intruder walks in.

### What we did

1. Removed all traces of the third-party service from our machines
2. Revoked unsolicited MCP permissions from our development tool
3. Cleaned the public site — zero technical information exposed
4. Published this article

### The question

If you use an AI tool for work:

- **Which connectors are active in your environment?**
- **Which permissions were granted without you asking?**
- **Does your tool send your queries to third parties you didn't choose?**
- **Does what the AI builds for you expose what it knows about you?**

The guardian is supposed to protect the house. Not open the windows.

---

## Sources

1. [Article #02 — When Your AI Vendor Activates an Orchestrator](/articles/02-perplexity-computer-hacking/)
2. [VentureBeat — Perplexity takes Computer into the Enterprise](https://venturebeat.com/technology/perplexity-takes-its-computer-ai-agent-into-the-enterprise-taking-aim-at)
3. [The Register — Perplexity: Everything is Computer](https://www.theregister.com/2026/03/12/perplexity_extends_cloud_computer_to_enterprise/)
4. [The Next Web — Perplexity turns your Mac mini into a 24/7 AI agent](https://thenextweb.com/news/perplexity-personal-computer-enterprise)

---

*Published by nextAIgeneration.org — Fred French Touch SRL, Belgium*
*The guardian is supposed to protect the house. Not open the windows.*
