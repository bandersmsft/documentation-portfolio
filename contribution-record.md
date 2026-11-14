# Contribution record

This page is the numbers behind the portfolio, in one place. It is derived from a complete export of my merged pull requests taken on September 22, 2026, while I still had repository access, plus a public commit audit run the same day.

I keep the full row-level export privately and can share it with a specific employer on request. It is not published here because the pull request titles contain internal identifiers, test-harness names, and customer support case numbers.

## Totals

| Measure | Value | Source |
| --- | --- | --- |
| Public commits, live in Microsoft repositories | 4,036 | Re-checked November 6, 2026 |
| Merged pull requests, private authoring repositories (my own export) | 2,292 | Export of September 22, 2026 |
| Distinct repositories | 33 | Same export |
| Date range | June 2016 to September 2026 | Same export |
| Public commits at audit, including three since-removed repositories | 4,289 | Public commit audit of September 22, 2026 |
| Peak year | 356 merged pull requests in 2024 | Same export |

Two notes on reading these. The pull request export begins in June 2016 because that is when this work moved to Git, so it does not represent the years before that. The public commit count and the pull request count measure different things, which is why they do not reconcile: commits land in public mirror repositories, while pull requests were raised in separate private authoring repositories.

## By product area

| Product area | Merged pull requests | Period |
| --- | ---: | --- |
| Azure documentation, primarily Cost Management and Billing | 1,746 | November 2016 to February 2026 |
| Azure Monitor | 148 | November 2025 to September 2026 |
| System Center | 105 | June 2016 to December 2017 |
| Azure AI Video Indexer | 73 | March 2025 to August 2026 |
| Azure REST API reference | 49 | March 2019 to January 2026 |
| Partner Center | 36 | January 2022 to March 2025 |
| Microsoft Learn training | 31 | October 2019 to December 2024 |
| Documentation legal and policy | 29 | March 2021 to January 2026 |
| Azure Carbon Optimization | 25 | March 2025 to January 2026 |
| Contributor and authoring support | 10 | June 2020 to January 2026 |
| Azure Compute | 6 | August 2024 to January 2026 |
| FinOps toolkit, open source | 6 | June 2024 to November 2024 |
| Twenty further repositories, one to five each | 28 | March 2018 to September 2026 |

The Azure Monitor figure covers only the period after that content moved to its own repository in November 2025. My Azure Monitor ownership ran longer than that date range suggests, and the earlier work sits inside the Azure documentation total above it.

## By year

| Year | Merged pull requests |
| --- | ---: |
| 2016 | 90 |
| 2017 | 100 |
| 2018 | 88 |
| 2019 | 158 |
| 2020 | 261 |
| 2021 | 281 |
| 2022 | 284 |
| 2023 | 343 |
| 2024 | 356 |
| 2025 | 180 |
| 2026 | 151 |

The 2025 and 2026 figures are lower for a reason worth stating. My output shifted toward larger audit, consolidation, and automation work in those years, which produces fewer and bigger changes. The July 2026 month alone removed more lines than it added while closing 52 accuracy and deduplication findings.

## By work type

These counts come from keyword analysis of pull request titles, so they are a floor rather than a precise total. A title does not always say what the change did.

| Work type | Merged pull requests |
| --- | ---: |
| Migration or transfer | 98 |
| REST API, Resource Manager, Bicep, or schema | 63 |
| Tutorials | 48 |
| Security and least-privilege guidance | 44 |
| General availability, launch, or release | 34 |
| Deprecation or retirement | 30 |
| Quickstarts | 17 |

## Public commits by repository

From the audit of September 22, 2026. The status column reflects a re-check on November 6, 2026.

| Repository | Commits | Status on November 6, 2026 |
| --- | ---: | --- |
| [MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs/commits?author=bandersmsft) | 3,404 | Live |
| [MicrosoftDocs/azure-monitor-docs](https://github.com/MicrosoftDocs/azure-monitor-docs/commits?author=bandersmsft) | 410 | Live |
| MicrosoftDocs/SystemCenterDocs | 197 | Repository removed |
| [MicrosoftDocs/entra-docs](https://github.com/MicrosoftDocs/entra-docs/commits?author=bandersmsft) | 94 | Live |
| [MicrosoftDocs/azure-compute-docs](https://github.com/MicrosoftDocs/azure-compute-docs/commits?author=bandersmsft) | 68 | Live |
| [MicrosoftDocs/dataexplorer-docs](https://github.com/MicrosoftDocs/dataexplorer-docs/commits?author=bandersmsft) | 59 | Live |
| MicrosoftDocs/azure-ai-docs | 31 | Removed from Microsoft, preserved at [bandersmsft/azure-ai-docs](https://github.com/bandersmsft/azure-ai-docs) |
| MicrosoftDocs/azure-security-docs | 25 | Repository removed |
| [MicrosoftDocs/SupportArticles-docs](https://github.com/MicrosoftDocs/SupportArticles-docs/commits?author=bandersmsft) | 1 | Live |

**Why the commit links above point at Microsoft while the proof links elsewhere point at my forks.** Microsoft's copy is the independent corroboration, and it works today. My synced fork is the durable copy. A commit identifier is a cryptographic hash of its own content and history, so it cannot be fabricated into Microsoft's repository, which is what makes the identifier meaningful. The [published work page](published-work.md) explains how to check either one.

**What this means for the 4,289 figure.** It was accurate on the audit date and I state it with that date. As of November 6, 2026, about 4,067 of those commits are still publicly reachable. The 222 commits in the two removed repositories were recorded in a dated audit and can no longer be independently re-derived. The 31 commits in the third survive because a personal fork preserved the history.

## How to verify any of this

**Commit counts.** Open any live link in the table above. The count appears at the top of the page and needs no account.

**A specific change.** See the [published work and spot checks](published-work.md) page, which lists individual articles and commits that resolve today.

**Pull request counts.** These came from private authoring repositories whose URLs return HTTP 404 for anyone outside Microsoft. The export is my own record, not external proof, which is why this page separates it from the public commit figures rather than adding the two together.

## Preserved personal copies

Where a Microsoft repository has been removed, a personal public fork is the only remaining path to the history. These forks exist and were verified on November 6, 2026.

| Fork | Parent | Default branch |
| --- | --- | --- |
| [bandersmsft/azure-docs](https://github.com/bandersmsft/azure-docs) | MicrosoftDocs/azure-docs | `master` |
| [bandersmsft/azure-monitor-docs](https://github.com/bandersmsft/azure-monitor-docs) | MicrosoftDocs/azure-monitor-docs | `main` |
| [bandersmsft/azure-ai-docs](https://github.com/bandersmsft/azure-ai-docs) | MicrosoftDocs/azure-ai-docs, now removed | `main` |
| [bandersmsft/azure-compute-docs](https://github.com/bandersmsft/azure-compute-docs) | MicrosoftDocs/azure-compute-docs | `main` |
| [bandersmsft/SupportArticles-docs](https://github.com/bandersmsft/SupportArticles-docs) | MicrosoftDocs/SupportArticles-docs | `main` |
| [bandersmsft/finops-toolkit](https://github.com/bandersmsft/finops-toolkit) | microsoft/finops-toolkit | `dev` |

**These forks were synced on November 6, 2026 and are identical to their Microsoft parents**, confirmed by comparing branch tips. The author-filtered commit counts now match upstream exactly: 410 for `azure-monitor-docs`, 67 for `azure-compute-docs`, and 1 for `SupportArticles-docs`.

One exception. The author filter returns no matches on `finops-toolkit` for either the Microsoft repository or my fork, because those contributions were merged in a way that did not preserve me as commit author. That work is evidenced instead by the six merged pull requests and the project README, which credits me by name.

**The System Center gap.** System Center has no personal fork, and the Microsoft repository is now gone. Those 197 commits covered the 2005 to 2016 era, which was the only surviving public evidence of my pre-Azure decade. What remains is the pull request record in my private export, 105 entries with dates and titles, and the [published System Center documentation](https://learn.microsoft.com/system-center/). I state this as a loss rather than working around it.

## A note on bylines

Microsoft reassigned documentation bylines during a March 2025 reorganization. Articles I owned for years now carry other names, so the published page is not proof of authorship. Git commit history is cryptographically chained and cannot be rewritten the same way, which is why every verification path on this page runs through commits.
