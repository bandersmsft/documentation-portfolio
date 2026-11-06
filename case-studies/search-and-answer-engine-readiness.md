# Search and answer-engine readiness: making content retrievable by people and by models

## At a glance

| Item | Detail |
| --- | --- |
| Audience | Buyers and operators who search, and the AI answering systems that now stand between them and the content. |
| Problem | Content can be accurate, published, and still never retrieved, or retrieved and still insufficient to answer the question. |
| My role | I ran question-driven retrieval evaluation on a production documentation set and delivered search-oriented content improvements. |
| Method | Reference questions with expected answers, LLM-as-a-judge scoring, structural evaluation criteria, and human review. |
| Verified outcome | Table-chunking violations fell from 227 to 216 and heading-hierarchy violations from 187 to 156, with 366 words removed across 20 articles while preserving 1,427 authored artifacts. |

## The problem

Search visibility used to end at the ranked result. It no longer does. A buyer asks a question, a model retrieves some chunks, and the answer it gives either cites you or does not. If your content is not retrieved, you are invisible. If it is retrieved but the chunk lacks the context to answer, the model fills the gap from somewhere else.

That makes retrievability a content structure problem rather than a keyword problem. A table split across a chunk boundary loses its header row and becomes meaningless. A heading hierarchy that skips levels destroys the structural signal a retriever uses. A procedure that depends on context three sections earlier cannot answer anything on its own.

## What I did

### Question-driven retrieval evaluation

I built evaluation around the questions customers actually ask rather than around keywords. I ran a pilot that triaged ten real customer questions through an AI answering workflow, then expanded it into a broader question-driven evaluation the following month.

For each question I developed or used an expected answer and explicit reference criteria. I ran the retrieval and answering workflow, then compared observed output against those expectations. This is golden-set evaluation applied to documentation.

I used an LLM as a judge to score generated answers against the expected results, alongside explicit evaluation criteria and human oversight. I did not treat the judge as the final authority. It ranked and flagged, and I reviewed.

### What I evaluated for

I assessed three things that a ranking position does not tell you.

**Retrieval correctness.** Did the system find the right source articles at all.

**Context sufficiency.** Did the retrieved chunks carry enough context to answer the question, or did the answer depend on material that was never retrieved.

**Structural interference.** Did the content structure itself impede retrieval or degrade answer quality. The criteria I worked against included chunk autonomy, heading hierarchy, disambiguation between similarly named concepts, and context completeness.

### Turning failures into content changes

When an answer failed, I traced it to a structural cause and fixed the content. I ran this as controlled experiments with explicit stop and scale criteria rather than as an open-ended editorial rewrite, because editorial churn without a stopping rule consumes a team and proves nothing.

I also ran a lossless concision evaluation, which tests whether content can be shortened without losing authored substance. Removing words improves chunk density only if the information survives, so the evaluation measured both.

### Classic search work

My search-oriented content work predates the answer-engine era. The pull-request record documents dedicated search work for Azure Cost Management and Billing, including a search optimization pass in December 2018, a reserved instance update made specifically for better search performance in May 2019, and a further search update in October 2020.

Alongside that, I delivered the structural work that search depends on across Billing, Microsoft Customer Agreement, FinOps, Reservations, and Azure Monitor: landing-page updates, table-of-contents reorganization, metadata, page titles, redirects, internal links, and cross-references. The Platform subservice retirement described in the [content strategy case study](content-strategy-and-audit.md) was a navigation and redirect migration as much as an ownership change, because a reorganization that breaks inbound links trades one problem for a worse one.

## Evidence

| Evidence | What it shows |
| --- | --- |
| [Azure Docs commit history](https://github.com/MicrosoftDocs/azure-docs/commits?author=bandersmsft) | 3,404 public commits, including the search, metadata, navigation, and redirect work. |
| [Azure Monitor commit history](https://github.com/MicrosoftDocs/azure-monitor-docs/commits?author=bandersmsft) | The repository where retrievability evaluation was applied. |
| [Cost Management and Billing overview](https://learn.microsoft.com/azure/cost-management-billing/cost-management-billing-overview) | A published entry point from the content set I optimized. |
| [Azure Monitor documentation](https://learn.microsoft.com/azure/azure-monitor/) | The published set evaluated for retrievability. |

## Outcome and evidence boundary

**Verified measurements.** The structural improvements are measured: table-chunking violations from 227 to 216, heading-hierarchy violations from 187 to 156, and 366 words removed across 20 articles while preserving 1,427 authored artifacts. Two tracked work items record the retrievability pilot and its expansion.

**What those numbers are and are not.** They are content-structure and retrievability measures. They are not claims of organic search growth, answer-engine referral traffic, or improved model answer accuracy. I am not going to convert a structural metric into a traffic metric, because they are different measurements and the substitution would not survive scrutiny.

**Direct evidence versus transferable practice.** Direct evidence covers question-driven retrieval evaluation, reference answers and expected criteria, LLM-as-a-judge scoring, answer sufficiency assessment, chunk autonomy, heading hierarchy, structural remediation, and delivered search-oriented content improvements on a very large documentation property. Building a company search and answer-engine practice from the ground up, including the audit and the prioritized growth plan, is adjacent work I have the method for but have not owned as a marketing program.

**Tools I do not claim.** I have not used Google Analytics 4, Search Console, Ahrefs, or Semrush. My measurement experience is documentation telemetry, customer satisfaction scoring, content freshness, and page views, reported through roughly ten years of Power BI report authoring on established datasets. I can learn the standard search stack quickly, and I would rather say that than imply a tool history I do not have.

**What this does not establish.** It does not establish independent keyword research ownership, backlink or external link strategy, organic acquisition campaign ownership, conversion rate optimization, or Schema.org and knowledge-graph implementation.
