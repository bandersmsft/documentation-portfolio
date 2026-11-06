# Infrastructure storytelling: writing for operators who run the cluster

## At a glance

| Item | Detail |
| --- | --- |
| Audience | Kubernetes and cloud operators, platform engineers, and the technical executives who fund their tooling. |
| Problem | Observability guidance was written as feature description when operators needed diagnostic sequence, and the technical values in it had drifted out of date. |
| My role | I owned Azure Monitor documentation covering Kubernetes monitoring, and I validated it against clusters I built myself. |
| Method | Hands-on validation in live clusters, engineering subject matter expert collaboration, and restructuring guidance around the operator decision path. |
| Verified outcome | Public commit history across Azure Monitor, Azure Docs, and Azure Compute, including container, Prometheus, Private Link, and network observability guidance. |

## The problem

Infrastructure documentation fails in a specific way. It describes what a feature is when the reader needs to know what to do next.

An operator reading about agent health does not want a feature tour. They have an agent that is not reporting, and they need an ordered path: confirm installation, check process health, check heartbeat, confirm the data collection rule association, confirm the configuration downloaded, then interpret what they see and take the next action.

The second failure is drift. Infrastructure moves faster than its documentation. The Azure Monitor container guidance I inherited documented a deprecated cAdvisor read-only port as a routine option, pinned Prometheus to legacy major versions, pinned Kubernetes versions several minors behind current, and linked to Prometheus 1.8 documentation in a scrape configuration article. Each of these is individually small. Together they tell a reader that nobody is maintaining this.

## What I did

**I owned the Kubernetes monitoring content and validated it myself.** For roughly the last six months of my Microsoft work I owned Azure Monitor documentation concerning Azure Kubernetes Service. I created and configured Azure Kubernetes Service clusters and used them to test and validate the monitoring procedures I was documenting. I worked with engineering subject matter experts on new feature documentation, on correctness, and on improving weak existing guidance.

The surface included Container Insights, Kubernetes metrics and logging, cluster monitoring, Azure Monitor managed service for Prometheus, Grafana dashboards, Arc-enabled Kubernetes monitoring, and container log collection.

**I restructured troubleshooting around the operator decision path.** For Windows virtual machine and scale-set agent troubleshooting, I organized the guidance as installation, process health, heartbeat, data collection rule association, configuration download, expected results, interpretation, next actions, and verification. That sequence is the diagnostic order an operator actually follows. It also let me turn internal support knowledge into customer-safe guidance without exposing internal-only diagnostics.

**I treated version and port accuracy as a defect class.** I filed and worked tracked items for the deprecated cAdvisor port, the legacy Prometheus version pins, the stale Prometheus documentation link, the Kubernetes version pins, and an OpenTelemetry port documented as a standard path when it was a Microsoft-selected value. That last one matters to an operator building against the endpoint, because a Microsoft-chosen port and a protocol default carry different expectations.

**I covered the network and identity surface operators hit on day one.** My public contributions include Private Link access-mode consolidation, access-mode and role guidance, container log updates, firewall-protected storage access for data export, private endpoint resource references, endpoint and DNS reconciliation, and Kubernetes network observability metric references.

**I wrote launch content for AI infrastructure features.** As sole writer for Azure AI Video Indexer across 73 merged pull requests, I covered Arc deployment, network requirements, private connectivity, firewall-protected storage, a security baseline, and preview-to-general-availability transitions, including Live Analysis for Ignite 2025. As sole writer for Azure Carbon Optimization across 25 merged pull requests, I covered API data export, permissions, quickstarts, a Python export tutorial, and an API changelog documenting version deprecation paths.

## How I validated the work

I verified technical values against the authoritative specification rather than against other articles, establishing the Azure REST API specification repository as the source of truth for portal, Resource Manager, API, and SDK behavior.

I ran the procedures. I built Azure virtual machines and Kubernetes clusters, executed the walkthroughs, tested the API samples and PowerShell examples I published, and escalated product behavior problems I found before release. Across my career I was brought into feature design rather than handed finished software, and I delivered through private preview, public preview, and general availability alongside the implementation.

## Evidence

| Evidence | What it shows |
| --- | --- |
| [Azure Monitor commit history](https://github.com/MicrosoftDocs/azure-monitor-docs/commits?author=bandersmsft) | 410 public commits in Microsoft Azure Monitor documentation. |
| [Kubernetes network observability metrics](https://github.com/bandersmsft/azure-monitor-docs/commit/373ec2307654791695f3cd99100a45e32657404a) | Reference maintenance for Kubernetes network observability metrics. |
| [Private Link access modes](https://github.com/bandersmsft/azure-monitor-docs/commit/20dc0a7f2146553e851d3ac828c27762db3c0333) | Consolidated private connectivity access-mode guidance. |
| [Security, metrics, and container logs](https://github.com/bandersmsft/azure-monitor-docs/commit/ad9e797b8139b452d39eb7bcae9e38897ca4ded4) | Private Link modes, role guidance, and container log updates. |
| [Firewall-protected storage export](https://github.com/bandersmsft/azure-docs/commit/778231d5ce1a24c25d55e319d66f63d30f7f085e) | Storage firewalls, extra permissions, and trusted-service access. |
| [Azure Monitor documentation](https://learn.microsoft.com/azure/azure-monitor/) | The published content set. |
| [Preserved Azure Monitor repository](https://github.com/bandersmsft/azure-monitor-docs) | Personal public fork with imported history. |

## Outcome and evidence boundary

**What this establishes.** I can learn an infrastructure product quickly, build an environment to test it, work with engineers who know it better than I do, and produce guidance an operator can follow under pressure. I did this across observability, containers, networking, identity, APIs, and AI services.

**My Kubernetes boundary, stated precisely.** I created and configured Azure Kubernetes Service clusters to validate monitoring procedures. I am not a Kubernetes expert or an advanced cluster engineer, and my engineering partners were the technical specialists. My longer hands-on history is with Azure virtual machines and test environments, going back to about 2014. Do not read that span as Kubernetes experience.

**What the commits do and do not show.** My contributions to networking and identity articles establish documentation work on storage firewalls, private connectivity, and access control. They do not establish independent firewall deployment or network engineering. A link correction in an authentication article is a link correction, not authorship of the authentication procedure.

**What this does not establish.** It does not establish cluster administration, production infrastructure operations, Kubernetes software development, web application firewall administration, or enterprise identity administration.
