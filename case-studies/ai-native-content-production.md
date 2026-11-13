# AI-native content production: daily practice, custom tooling, and the review boundary

## At a glance

| Item | Detail |
| --- | --- |
| Audience | Content leaders deciding how to use AI in production without losing technical accuracy. |
| Problem | Documentation work scaled faster than a manual authoring model could absorb, and naive AI drafting produces plausible text that fails technical verification. |
| My role | I operated AI-assisted workflows daily, designed one autonomous documentation pipeline, and directed AI agents to build my own agent tooling. |
| Method | Prompts, orchestration logic, Model Context Protocol integrations, validation scripts, acceptance tests, quality gates, logging, and human review on every output. |
| Verified outcome | Approximately 90 percent of my day-to-day work was AI-assisted in my final nine months, and no AI system ever merged a pull request on my behalf. |

## The problem

Generative models write fluent documentation quickly. Fluent and correct are different properties. A model will state a port number, a service limit, an API version, or a role requirement with complete confidence and no basis. In infrastructure documentation that failure mode is expensive, because readers act on the instruction.

The practical question is not whether to use AI. It is how to get the speed while making every technical claim verifiable before it ships.

## What I did

### Daily practice

During my final nine months at Microsoft, approximately 90 percent of my day-to-day work was AI-assisted. I used Visual Studio Code as the harness and switched between Claude and GPT models by task rather than defaulting to one vendor. Inside that harness I operated company-developed search, answer-engine, GitHub, and documentation agents, connected to numerous Model Context Protocol servers.

The work covered repository search, documentation editing, pull-request creation and packaging, screenshot capture, testing, browser automation, data analysis, and workflow design. Some agents acted as assistants on a single step. Others executed multi-step processes end to end. Most workflows ran sequentially, and some long-running tasks ran overnight.

### What I designed, and what I only operated

This distinction matters, so I state it plainly.

**I operated and evaluated the company agents.** I tested them, used them daily, filed bug reports with the AI tooling support team, and gave improvement feedback that fed their reliability. I did not design those underlying agent products.

**I designed Uptime.** Uptime is an autonomous documentation pipeline I conceived and directed AI agents to build, refined with my team for the Microsoft 2026 Hackathon. I was the technical systems designer and owner. I specified system behavior, requirements, and constraints, directed AI coding agents through the implementation, integrated the components, operated and tested the pipeline, analyzed failures, directed fixes, and set the acceptance and quality gates.

I designed its module contract: a JSON-schema result envelope, a worker specification, phase checkpoints, capability declarations, admission control, and an immutable release with SHA-256 provenance pinning across ten build-pinned files. At the release gate it ran 11 test suites and 117 assertions green.

In one session I diagnosed seven distinct pipeline defects and directed the fixes. Three are worth naming because they show the failure modes this class of system actually has. A leaked browser debugging connection hung the host process after a capture that had already succeeded. A startup liveness gate killed healthy workers at the 300-second mark. A drift between the installed command-line version and the active version blocked all task admission.

By the Hackathon, Uptime had produced a large number of pull requests, each reviewed by a human subject matter expert before merge, that updated hundreds of stale screenshots in off-hours runs. That cleared low-priority screenshot debt and left writers and reviewers free for higher-value work.

**I directed the build of my own tooling.** I directed AI agents to create a personal Visual Studio Code extension and 50 packaged agent skills covering reporting, work-item workflow, pull-request review, screenshot procedure, and content analysis. I directed AI agents to build Model Context Protocol server integrations, a deterministic multi-account Git credential helper that eliminated recurring interactive authentication failures, and a persistent agent memory architecture scoped to user, session, and repository with enforcement at three layers.

### Production workflows the tooling ran

**Browser capture and annotation.** I directed AI agents to build a Playwright pipeline against the live Azure portal that navigates, confirms arrival, fits the window through a deterministic composition loop, captures, measures the page, sanitizes personally identifiable information, resolves geometry, and renders annotated output in roughly 12 seconds. I replaced a fragile estimated window-chrome origin with a device-scale viewport capture, which made callout placement exact at any display scaling. The composition loop resizes, measures, evaluates, and adjusts across bounded iterations using deterministic pixel signals rather than calling a vision model on each pass, a choice I made for cost and repeatability.

**Screenshot freshness at scale.** I ran a ledger-driven program covering 1,528 screenshots across 274 files and 17 subservices, batched into roughly 51 planned pull requests with resumable, chunked unattended runs. The estimated baseline was about 4.2 hours saved per pull request against a manual authoring model. I set the publication gate: procedure validation, browser-chrome removal, crop-only processing, fit-to-content framing, and full-resolution comparison against the current source.

**Technical accuracy verification.** I ran a version-aware schema verification pilot that converted contract drift into bounded, human-reviewable pull requests. It covered broken Resource Manager schema URLs, incorrect ports, stale Prometheus versions, and obsolete compatibility guidance.

### The review boundary

I manually reviewed every piece of AI-generated work. No AI system ever merged a pull request on my behalf. When a change needed judgment I did not have, I assigned the generated pull request to a subject matter expert for additional review.

Privacy was a gate rather than a cleanup step. Tenant and customer identifier sanitization ran with schema-validated identity evidence, and a run that could not prove sanitization did not publish. One recorded defect is instructive. A privacy pass failed to expose resource-name replacement gaps in its own report, which is exactly the kind of silent failure a gate has to catch.

## Evidence

| Evidence | What it shows |
| --- | --- |
| [Azure Monitor commit history](https://github.com/MicrosoftDocs/azure-monitor-docs/commits?author=bandersmsft) | Public commits in the repository these workflows targeted. |
| [Azure Docs commit history](https://github.com/MicrosoftDocs/azure-docs/commits?author=bandersmsft) | 3,404 public commits across the broader Azure documentation set. |
| [FinOps toolkit commits](https://github.com/microsoft/finops-toolkit/commits?author=bandersmsft) | Public open-source contribution history. |

## Outcome and evidence boundary

**What the record supports.** Internal work-item records document the screenshot freshness program, the retrievability evaluation, the schema verification pilot, the hackathon user acceptance testing, and the specific defects and recoveries named above. The published documentation and public commit history show the output that reached customers.

**What is not publicly linkable.** Uptime, the browser capture pipeline, the agent skills, and the work-item records are internal. Microsoft owns that code. I did not retain it and no longer have access, so I describe methods and results rather than offering source.

**The status of Uptime.** Uptime was fully developed and team-tested, and it was ready for adoption by the documentation organization. I was laid off two days after the hackathon work completed and I do not know whether Microsoft deployed it. I do not claim production operation or organization-wide rollout.

**My coding boundary.** This is AI-assisted systems development and agentic workflow engineering. I developed hundreds of Python and PowerShell scripts with coding-agent support, specified requirements and acceptance tests, reviewed and tested the results, and debugged failures with agent assistance. I do not independently author production code unaided, and I am not a production software engineer. I state this plainly because a content leader who overstates engineering depth gets found out in the first technical conversation.