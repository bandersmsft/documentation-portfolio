# Published work and spot checks

This page exists so you can read my actual writing and verify that it is mine, in about two minutes. Every link was checked on November 6, 2026.

Each row pairs a published article with a public commit of mine that changed it. The commit is the proof, because Microsoft reassigned documentation bylines in a March 2025 reorganization, so the published page no longer carries my name. The commit history does, and it cannot be rewritten.

## Read these first

Three pieces that show the range, from operator troubleshooting to a customer tutorial.

| Published article | What I did | Proof |
| --- | --- | --- |
| [Troubleshoot Azure Monitor metrics](https://learn.microsoft.com/azure/azure-monitor/metrics/metrics-troubleshoot) | Restructured metrics troubleshooting around the operator diagnostic path. | [Commit ad9e797b](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/ad9e797b8139b452d39eb7bcae9e38897ca4ded4), August 9, 2026, 156 lines added and 132 removed across five articles. |
| [Export cost data tutorial](https://learn.microsoft.com/azure/cost-management-billing/costs/tutorial-export-acm-data) | Added guidance for exporting to firewall-protected storage, covering the extra permissions and trusted-service access it requires. | [Commit 778231d5](https://github.com/MicrosoftDocs/azure-docs/commit/778231d5ce1a24c25d55e319d66f63d30f7f085e), July 14, 2023, 63 lines added. |
| [Analyze costs and create budgets](https://learn.microsoft.com/training/modules/analyze-costs-create-budgets-azure-cost-management/) | Authored this seven-unit training module with hands-on exercises and an assessment. It was localized into 17 languages. | Authored October 2019 and maintained through December 2024. One of 31 merged pull requests to Microsoft Learn training. |

## Infrastructure and Kubernetes

| Published article | What I did | Proof |
| --- | --- | --- |
| [Container insights authentication](https://learn.microsoft.com/azure/azure-monitor/containers/container-insights-authentication) | Validated and corrected the authentication guidance for Kubernetes monitoring. | [Commit b30679be](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/b30679be0acd92003ff1dd7a68c9b944813fad19), August 9, 2026, 358 lines added and 281 removed across seven articles. |
| [Default Prometheus metrics scrape configuration](https://learn.microsoft.com/azure/azure-monitor/containers/prometheus-metrics-scrape-default) | Corrected container network metrics references. | [Commit 373ec230](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/373ec2307654791695f3cd99100a45e32657404a), August 18, 2026. |
| [Container insights log schema](https://learn.microsoft.com/azure/azure-monitor/containers/container-insights-logs-schema) | Updated the container log schema reference. | Part of [commit ad9e797b](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/ad9e797b8139b452d39eb7bcae9e38897ca4ded4), August 9, 2026. |
| [Data collection endpoint overview](https://learn.microsoft.com/azure/azure-monitor/data-collection/data-collection-endpoint-overview) | Reconciled endpoint and DNS guidance. | Part of [commit b30679be](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/b30679be0acd92003ff1dd7a68c9b944813fad19), August 9, 2026, 74 lines added. |
| [Azure Monitor metrics platform](https://learn.microsoft.com/azure/azure-monitor/metrics/data-platform-metrics) | Reconciled the metrics overview with adjacent platform, OpenTelemetry, and Prometheus content. | Part of [commit b30679be](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/b30679be0acd92003ff1dd7a68c9b944813fad19), August 9, 2026. |

## Security, access, and private connectivity

| Published article | What I did | Proof |
| --- | --- | --- |
| [Roles, permissions, and security in Azure Monitor](https://learn.microsoft.com/azure/azure-monitor/fundamentals/roles-permissions-security) | Validated and corrected role and permission guidance, part of broader work replacing broad administrator guidance with least-privileged roles. | Part of [commit ad9e797b](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/ad9e797b8139b452d39eb7bcae9e38897ca4ded4), August 9, 2026, 44 lines added. |
| [Private Link security for Azure Monitor](https://learn.microsoft.com/azure/azure-monitor/fundamentals/private-link-security) | Consolidated overlapping private connectivity access-mode guidance. | [Commit 20dc0a7f](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/20dc0a7f2146553e851d3ac828c27762db3c0333), July 13, 2026. |
| [Best practices for Azure Monitor security](https://learn.microsoft.com/azure/azure-monitor/fundamentals/best-practices-security) | Validated security best-practice guidance. | Part of [commit ad9e797b](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/ad9e797b8139b452d39eb7bcae9e38897ca4ded4), August 9, 2026. |
| [Microsoft Entra authentication for Application Insights](https://learn.microsoft.com/azure/azure-monitor/app/azure-ad-authentication) | Corrected a broken reference in the authentication overview. A small change, included because it is precise and verifiable. | [Commit 16938c0f](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/16938c0fd5143b044b98fbe762320359388a978d), June 25, 2026. |

## Information architecture and deduplication

The commit below is the clearest single example of the audit work described in the [content strategy case study](case-studies/content-strategy-and-audit.md). It removed 49 lines and added 15 across three articles, which is what fixing duplication looks like in practice.

| Published articles | What I did | Proof |
| --- | --- | --- |
| [Autoscale best practices](https://learn.microsoft.com/azure/azure-monitor/autoscale/autoscale-best-practices) and [Private Link design](https://learn.microsoft.com/azure/azure-monitor/fundamentals/private-link-design) | Removed duplicated autoscale, Private Link, and platform content, consolidating each concept into its owning article. | [Commit 20dc0a7f](https://github.com/MicrosoftDocs/azure-monitor-docs/commit/20dc0a7f2146553e851d3ac828c27762db3c0333), July 13, 2026, titled "Dedupe Azure Monitor autoscale, Private Link, and platform essentials." |

## Product areas I owned

Landing pages for the content sets I was responsible for. These show scope rather than individual authorship.

- [Azure Cost Management and Billing](https://learn.microsoft.com/azure/cost-management-billing/cost-management-billing-overview). Sole writer for seven years.
- [Azure Monitor](https://learn.microsoft.com/azure/azure-monitor/). Documentation owner across alerts, metrics, logs, data collection, agents, autoscale, health models, and Kubernetes monitoring.
- [Azure AI Video Indexer](https://learn.microsoft.com/azure/azure-video-indexer/). Sole writer across 73 merged pull requests.
- [Azure Carbon Optimization](https://learn.microsoft.com/azure/carbon-optimization/). Sole writer across 25 merged pull requests.
- [System Center](https://learn.microsoft.com/system-center/). Documented Configuration Manager, Operations Manager, Service Manager, and related products across product generations.

## How to check a commit yourself

Open any commit link. The page shows the author, the date, the commit message, and the full diff. The author name reads `Bill Anderson` with the email `banders@microsoft.com` on most of them, and `bandersmsft` on more recent ones where I had switched my Git configuration to a personal address.

A commit identifier is a cryptographic hash of its own content, author, date, and parent. That means it cannot be altered or reassigned the way a byline can. If you want to verify any claim on this page, the commit is the thing to check.

## What this page does not show

My highest-volume work sits in Microsoft private authoring repositories whose pull request URLs return HTTP 404 for anyone outside the organization. The [contribution record](contribution-record.md) gives those counts with their source and date, and keeps them separate from the publicly verifiable figures rather than combining the two.
