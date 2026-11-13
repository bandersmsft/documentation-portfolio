# Content strategy and audit: fixing a large observability documentation set

## At a glance

| Item | Detail |
| --- | --- |
| Audience | Cloud operators, site reliability engineers, platform teams, and the support organization that serves them. |
| Problem | A large Azure Monitor documentation set had accumulated duplication, contradictions, stale technical values, and unclear ownership. |
| My role | I audited the content, turned findings into a prioritized and tracked program, and shipped the fixes. |
| Method | Severity-rated audit findings, a published prioritization model, tracked work items, and release-aligned delivery. |
| Verified outcome | In one peak month I closed 52 accuracy and deduplication findings worth 55 story points, inside a total of 79 closed work items and 33 merged pull requests. |

## The problem

Azure Monitor spans alerts, metrics, logs, data collection, agents, autoscale, health models, and containers. Each area had its own history, its own writers, and its own release cadence. The result was a documentation set where the same concept was explained several times in different words, and where two articles sometimes gave a reader conflicting answers.

Duplication is not only an editorial problem. When two articles describe the same procedure differently, a reader cannot tell which one is current. When an article states a service limit that another article contradicts, the reader has no way to resolve it. Both cases drive support cost and erode trust in the documentation.

Stale technical values made this worse. The set documented a deprecated cAdvisor read-only port as a routine option, pinned Prometheus to legacy major versions, pinned Kubernetes versions several minors behind current, and carried broken Azure Resource Manager schema URLs that returned HTTP 404.

## What I did

**I ran a structured audit instead of an editorial pass.** I treated duplication and contradiction as defect classes with severity, not as style preferences. Each finding became its own tracked work item with a stated reason, for example an 80 percent duplication overlap at medium severity between an Azure Monitor resource-monitoring article and an Azure Resource Manager activity log article.

**I made ownership explicit.** Many problems existed because articles sat in a catch-all area with no clear owner. I reassigned Azure Monitor Platform articles to the owning Metrics, Data Collection, Logs, and Fundamentals areas and retired the Platform subservice. That work included redirects, navigation, metadata, and assets, so readers and search engines kept working while reviewer routing improved.

**I published a prioritization model rather than working from intuition.** I ranked candidate work by customer satisfaction score first, then content freshness, then page views. I added support signals on top of that ranking, using the internal knowledge base and direct input from support representatives to identify recurring customer issues.

**I built the intake path the program needed.** I created a Power Automate intake route for Azure Monitor documentation requests so that product manager and customer requests entered a tracked queue instead of arriving as individual messages.

**I added a recurring quality gate.** After auditing merged delivery history against published release notes, I found six omitted entries and restored them. I then instituted a monthly release-notes quality gate so the omission could not recur silently.

**I absorbed an orphaned backlog.** When a colleague left, I took ownership of the entire Azure Monitor backlog and triaged it to closure rather than letting it decay.

## How I validated the work

I verified technical values against authoritative sources rather than against other prose articles. I established the Azure REST API specification repository as the source of truth for portal, Resource Manager, API, and SDK behavior, which let me treat prose that disagreed with the specification as a defect with a fix rather than as a difference of opinion.

I validated procedures in live environments. I created and configured Azure virtual machines and Azure Kubernetes Service clusters to test the monitoring procedures I documented, so corrections reflected observed product behavior.

## Evidence

| Evidence | What it shows |
| --- | --- |
| [Azure Monitor commit history](https://github.com/MicrosoftDocs/azure-monitor-docs/commits?author=bandersmsft) | 410 public commits in Microsoft's Azure Monitor documentation repository. |
| [Preserved Azure Monitor repository](https://github.com/bandersmsft/azure-monitor-docs) | A personal public fork preserving the repository snapshot and imported history. |
| [Azure Monitor documentation](https://learn.microsoft.com/azure/azure-monitor/) | The published content set this work maintained. |
| [Private Link access-mode consolidation](https://github.com/bandersmsft/azure-monitor-docs/commit/20dc0a7f2146553e851d3ac828c27762db3c0333) | A representative deduplication commit consolidating overlapping access-mode guidance. |
| [Security and metrics freshness pass](https://github.com/bandersmsft/azure-monitor-docs/commit/ad9e797b8139b452d39eb7bcae9e38897ca4ded4) | Private Link modes, role guidance, and container log updates in one freshness pass. |

## Outcome and evidence boundary

**Verified outcomes.** The July 2026 delivery record shows 79 closed work items worth 100 story points and 33 merged pull requests across 198 changed files, with 1,145 lines added and 1,477 removed. Of those, 52 closed findings worth 55 story points were accuracy and deduplication fixes across alerts, agents, virtual machines, logs, metrics, Private Link, and autoscale. The following month I retired nine pages for a decommissioned portal experience and turned four separate product manager and customer requests into shipped guidance within days. The net removal of more lines than I added is the point rather than a side effect, because the work reduced surface area while improving accuracy.

**What the public record supports.** Public commit history and published documentation show the shipped changes. The Platform subservice retirement, the audit findings, and the delivery counts come from internal work-item and monthly reporting records that are not publicly linkable.