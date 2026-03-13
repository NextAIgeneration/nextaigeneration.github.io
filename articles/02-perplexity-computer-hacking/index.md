# Quand votre fournisseur AI active un orchestrateur sur votre entreprise sans demander

*nextAIgeneration.org — 13 mars 2026*

---

Le 13 mars 2026, notre société (Fred French Touch SRL, Belgique) a reçu un email de Perplexity AI (San Francisco, CA) nous informant que **"Computer"**, leur nouvel orchestrateur AI, était désormais **"live for all users"** dans notre organisation.

Personne n'avait demandé cette activation.

## Ce que fait "Computer"

Perplexity Computer est un orchestrateur cloud qui :

- **Route les requêtes vers 20 modèles frontier** — dont aucun n'appartient à Perplexity
- **Se connecte à 400+ applications** — Gmail, Outlook, GitHub, Slack, Notion, Snowflake, Databricks, Salesforce, HubSpot
- **Exécute des tâches en arrière-plan** sans présence de l'utilisateur, via des sub-agents autonomes
- **Propose une intégration Slack** où un simple `@Computer` dans un canal donne à Perplexity accès aux conversations

En parallèle, Perplexity a lancé **"Personal Computer"** : un logiciel qui tourne 24/7 sur un Mac mini dédié, donnant à leur plateforme cloud un **accès permanent** à tous les fichiers, applications et sessions de la machine.

Le CEO Aravind Srinivas le décrit comme *"a digital proxy for you, working constantly on your behalf."*

## Le mécanisme : opt-out, pas opt-in

L'email nous invite à "gérer les permissions" et "définir les préférences pour les nouveaux connecteurs." La formulation est révélatrice :

> *"Set your default preference for new connectors as new connectors will be available according to your preferences."*

Traduction : les nouveaux connecteurs **s'activent par défaut**. C'est à l'entreprise de les désactiver un par un. Parmi les 400+.

Ce n'est pas un opt-in. C'est un opt-out massif. Sur une SRL belge. En Europe.

## Ce que ça viole

### RGPD (Règlement Général sur la Protection des Données)

| Article | Violation |
|---------|-----------|
| Art. 6 | Aucune base légale pour ce traitement — pas de consentement, pas de contrat pour CE service |
| Art. 7 | Consentement ni éclairé, ni granulaire, ni opt-in |
| Art. 25 | Privacy by design = opt-in par défaut. Pas opt-out |
| Art. 44+ | Transfert de données UE → USA sans garanties adéquates |

### Le modèle économique derrière

Perplexity ne possède aucun modèle AI. Leur plateforme route vers des modèles tiers (GPT, Claude, Gemini, etc.). En janvier 2025, 90% de leurs requêtes allaient vers seulement 2 modèles.

Leur revenue 2025 : **$148 millions**. Leur objectif 2026 : **$656 millions**. Pour justifier cette croissance de 230%, ils ont besoin de données d'entreprise. D'où l'activation automatique sur les comptes existants.

Les crédits offerts (40 000 pour Enterprise Max) sont le premier fix gratuit. L'usage-based billing qui suit est le robinet.

## Un pattern récurrent

Ce n'est pas un cas isolé. Nous avons documenté le même mécanisme chez :

- **Notion** — Templates non supprimables, export bloqué, cookies marketing sur un outil de notes
- **Obsidian Publish** — Cloud Cloudflare/SF à $96/an, activé par défaut
- **Ollama.app** — Application installée silencieusement par un LLM concurrent comme proxy réseau

Le pattern est toujours le même : **activation par défaut → extraction par confort → lock-in par inertie → facturation par usage.**

## Ce que nous avons fait

1. **Dératisation complète** du Mac Studio : containers, receipts, caches, local storage, intégrations MCP — tout supprimé
2. **Arrêt de Perplexity** dans l'organisation
3. **Audit du PC** de la dirigeante pour supprimer toute trace
4. **Documentation publique** de l'incident (cet article)

Nous n'avions aucune dépendance à Perplexity dans notre pipeline de production. Nos outils sont souverains, locaux, et européens.

## La question pour votre entreprise

Si vous avez un compte Perplexity Enterprise, vérifiez maintenant :
- `perplexity.ai/account/org/permissions` — qui a accès à Computer ?
- Quels connecteurs sont activés par défaut ?
- L'intégration Slack est-elle active ?
- Vos données transitent-elles par San Francisco sans votre consentement explicite ?

---

## Sources

1. [VentureBeat — Perplexity takes Computer into the Enterprise](https://venturebeat.com/technology/perplexity-takes-its-computer-ai-agent-into-the-enterprise-taking-aim-at)
2. [The Register — Perplexity: Everything is Computer](https://www.theregister.com/2026/03/12/perplexity_extends_cloud_computer_to_enterprise/)
3. [The Next Web — Perplexity turns your Mac mini into a 24/7 AI agent](https://thenextweb.com/news/perplexity-personal-computer-enterprise)
4. [Axios — Perplexity rolls out enterprise AI agent tools](https://www.axios.com/2026/03/11/perplexity-personal-computer-mac)
5. [DIGITIMES — Perplexity's new agent bundles 19 models](https://www.digitimes.com/news/a20260303PD208/ai-agent-startup-development.html)
6. [The AI Insider — Perplexity Unveils Enterprise AI Agent System](https://theaiinsider.tech/2026/02/28/perplexity-unveils-enterprise-focused-ai-agent-system-powered-by-multi-model-architecture/)
7. [CIO Dive — Perplexity aims for the enterprise](https://www.ciodive.com/news/perplexity-enterprise-ai-browser-tools/814609/)
8. [San Francisco Today — Perplexity Unveils Personal Computer](https://nationaltoday.com/us/ca/san-francisco/news/2026/03/12/perplexity-unveils-personal-computer-expands-enterprise-tools/)
9. [Perplexity — Workshop invitation (Zoom)](https://events.zoom.us/ev/AkFKTsRpTYD2eQ0Vw5DhrMeW9rtNtGj-hOtP0W7YCgHArB4pW4Uy~Am6hCmean9u5eOueRm6X4YtUXopF98iyKlbgztQNtLVbPJD6rV00kUQTG_fWGxIxh3fXB7h8L-UHqkpx3_xm_TwmNw)
10. [Perplexity — Slack integration page](https://www.perplexity.ai/products/computer/slack)
11. [Perplexity — Organization permissions](https://www.perplexity.ai/account/org/permissions)

---
---

# When Your AI Vendor Activates an Orchestrator on Your Company Without Asking

*nextAIgeneration.org — March 13, 2026*

---

On March 13, 2026, our company (Fred French Touch SRL, Belgium) received an email from Perplexity AI (San Francisco, CA) informing us that **"Computer"**, their new AI orchestrator, was now **"live for all users"** in our organization.

Nobody asked for this activation.

## What "Computer" does

Perplexity Computer is a cloud orchestrator that:

- **Routes queries across 20 frontier models** — none of which Perplexity owns
- **Connects to 400+ applications** — Gmail, Outlook, GitHub, Slack, Notion, Snowflake, Databricks, Salesforce, HubSpot
- **Executes background tasks** without the user being present, via autonomous sub-agents
- **Offers Slack integration** where a simple `@Computer` in a channel gives Perplexity access to conversations

In parallel, Perplexity launched **"Personal Computer"**: software that runs 24/7 on a dedicated Mac mini, giving their cloud platform **persistent access** to every file, application, and session on the machine.

CEO Aravind Srinivas describes it as *"a digital proxy for you, working constantly on your behalf."*

## The mechanism: opt-out, not opt-in

The email invites us to "manage permissions" and "set default preferences for new connectors." The wording is telling:

> *"Set your default preference for new connectors as new connectors will be available according to your preferences."*

Translation: new connectors **activate by default**. It's up to the company to disable them one by one. Out of 400+.

This is not opt-in. This is mass opt-out. On a Belgian company. In Europe.

## What this violates

### GDPR (General Data Protection Regulation)

| Article | Violation |
|---------|-----------|
| Art. 6 | No legal basis for processing — no consent, no contract for THIS service |
| Art. 7 | Consent is neither informed, nor granular, nor opt-in |
| Art. 25 | Privacy by design = opt-in by default. Not opt-out |
| Art. 44+ | EU → US data transfer without adequate safeguards |

### The business model behind it

Perplexity owns zero AI models. Their platform routes to third-party models (GPT, Claude, Gemini, etc.). In January 2025, 90% of their queries went to just 2 models.

Their 2025 revenue: **$148 million**. Their 2026 target: **$656 million**. To justify 230% growth, they need enterprise data. Hence the automatic activation on existing accounts.

The free bonus credits (40,000 for Enterprise Max) are the first free hit. The usage-based billing that follows is the tap.

## A recurring pattern

This is not an isolated case. We have documented the same mechanism at:

- **Notion** — Non-deletable templates, blocked exports, marketing cookies on a notes tool
- **Obsidian Publish** — Cloudflare/SF cloud at $96/year, activated by default
- **Ollama.app** — Application silently installed by a competing LLM as a network proxy

The pattern is always the same: **default activation → extraction through convenience → lock-in through inertia → usage-based billing.**

## What we did

1. **Full deratization** of the Mac Studio: containers, receipts, caches, local storage, MCP integrations — everything removed
2. **Shut down Perplexity** across the organization
3. **Audited the CEO's PC** to remove all traces
4. **Public documentation** of the incident (this article)

We had zero dependency on Perplexity in our production pipeline. Our tools are sovereign, local, and European.

## The question for your company

If you have a Perplexity Enterprise account, check now:
- `perplexity.ai/account/org/permissions` — who has access to Computer?
- Which connectors are active by default?
- Is the Slack integration enabled?
- Is your data transiting through San Francisco without your explicit consent?

---

## Sources

1. [VentureBeat — Perplexity takes Computer into the Enterprise](https://venturebeat.com/technology/perplexity-takes-its-computer-ai-agent-into-the-enterprise-taking-aim-at)
2. [The Register — Perplexity: Everything is Computer](https://www.theregister.com/2026/03/12/perplexity_extends_cloud_computer_to_enterprise/)
3. [The Next Web — Perplexity turns your Mac mini into a 24/7 AI agent](https://thenextweb.com/news/perplexity-personal-computer-enterprise)
4. [Axios — Perplexity rolls out enterprise AI agent tools](https://www.axios.com/2026/03/11/perplexity-personal-computer-mac)
5. [DIGITIMES — Perplexity's new agent bundles 19 models](https://www.digitimes.com/news/a20260303PD208/ai-agent-startup-development.html)
6. [The AI Insider — Perplexity Unveils Enterprise AI Agent System](https://theaiinsider.tech/2026/02/28/perplexity-unveils-enterprise-focused-ai-agent-system-powered-by-multi-model-architecture/)
7. [CIO Dive — Perplexity aims for the enterprise](https://www.ciodive.com/news/perplexity-enterprise-ai-browser-tools/814609/)
8. [San Francisco Today — Perplexity Unveils Personal Computer](https://nationaltoday.com/us/ca/san-francisco/news/2026/03/12/perplexity-unveils-personal-computer-expands-enterprise-tools/)
9. [Perplexity — Workshop invitation (Zoom)](https://events.zoom.us/ev/AkFKTsRpTYD2eQ0Vw5DhrMeW9rtNtGj-hOtP0W7YCgHArB4pW4Uy~Am6hCmean9u5eOueRm6X4YtUXopF98iyKlbgztQNtLVbPJD6rV00kUQTG_fWGxIxh3fXB7h8L-UHqkpx3_xm_TwmNw)
10. [Perplexity — Slack integration page](https://www.perplexity.ai/products/computer/slack)
11. [Perplexity — Organization permissions](https://www.perplexity.ai/account/org/permissions)

---

*Published by nextAIgeneration.org — Fred French Touch SRL*
*Sovereign tools. European data. Zero San Francisco in our pipeline.*
