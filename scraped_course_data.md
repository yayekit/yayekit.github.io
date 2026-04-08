# Working With Data Platforms

**DataForest Foundational Course**

| Field | Value |
|-------|-------|
| Duration | 80 minutes |
| Modules | 7 |
| Level | All levels |
| Description | Prepared by DataForest Learning & Development |

---

## Chapter 1: Introduction (3 minutes)

### 1. Welcome to DataForest

DataForest builds enterprise data platforms for companies navigating some of the most complex data challenges in their

industries — post-acquisition integration, massive-scale billing reconciliation, healthcare revenue cycle analytics. 

Every engagement is different. The architecture underneath them is not.

This course gives you the conceptual foundation to understand what we build and why — before you sit in your first client

call, review your first pipeline, or write your first ticket.

This course is designed for everyone joining DataForest, regardless of role or technical background. 

You will not be asked to write code or configure a pipeline. 

You will be asked to think about data problems the way DataForest thinks about them: starting with the business question, 

not the technical solution.

By the time you finish this course, you:

-will be able to explain why a company invests in a data platform using real industry examples

-will recognise the architectural patterns DataForest uses across every engagement and understand why they exist

-will know how to identify the categories of data integration challenge that make this work genuinely hard

-will understand what data quality means to a finance director or a PE firm — not just to an engineer

-will be able to navigate a dimensional model and read what it is telling you

-will know where compliance constraints come from and why they shape the pipeline the way they do

-will have practised translating between business knowledge and technical requirements — the skill that sits at the centre

of everything DataForest does.

### 2. Course & assessment structure

How this course is structured?

Seven modules, 84 minutes, one narrative thread.

Each module builds on the last. All of them connect to real DataForest projects.

Individual modules run between 10 and 15 minutes each, which means you can complete the course in a single session or 

across several shorter ones — the modules are designed to stand independently so you can pause and return without losing 

the thread. 

The course is built around three active DataForest client engagements:

RMC-Norkem,a chemical manufacturer integrating three acquired companies; 

NexGen Cloud, a GPU infrastructure platform tracking billions in revenue across multiple APIs; 

and Sagis Diagnostics, a pathology and toxicology lab navigating HIPAA-compliant analytics and insurance claim management.

You will encounter all three throughout the course. The scenarios are drawn from situations that actually happened on these

projects.

**How assessment works**

Each of the first six modules ends with a short scenario-based question — one or two decisions drawn directly from the project

contexts you have just studied. These are formative: you will see immediately whether your reasoning was on track and why, 

but your answers are for your own reflection only and are not recorded anywhere.

The seventh module is different. It is a single branching scenario that runs for approximately 15 minutes and asks you to 

navigate a realistic situation using everything the previous modules covered. When you complete it, your manager and the

L&D team receive a record confirming you have finished the course. No grade is attached — what they see is that you

completed it, and which path through the scenario you took.

---

## Chapter 2: Module 1: Why We Build Data Platforms

### 1. Intro

Before we get into architectures, pipelines, or any technical detail, we need to answer a more basic question: why does any of this exist?

Every data platform DataForest builds — no matter the industry, no matter the stack — was built because someone, somewhere, could not answer a question they needed to answer. And the cost of not knowing that answer had become too high to ignore.

That's the premise this entire course builds on: a data platform gets built when the cost of not knowing something exceeds the cost of building the infrastructure to know it.

Keep that idea in mind. You're going to see it play out three times in the next few minutes — in three real situations from DataForest's active client work.

### 2. Story 1: The PE Acquisition — RMC-Norkem

A private equity firm acquires two chemical companies — RMC and Norkem. On paper, this is a straightforward portfolio expansion. Two businesses, now one. The fund's finance team needs to report combined revenue to its investors.

There's one problem. RMC runs on one ERP system. Norkem runs on another. The two systems were built independently, by different vendors, using different data models. A "customer" in one system is not structured the same way as a "customer" in the other. Revenue figures are stored in different currencies, calculated on different methodologies, and labelled with different field names.

When the finance team asks: what is our combined revenue this quarter? — no one can answer it. Not because the data doesn't exist. It exists in both systems. But it exists in a form that cannot be directly compared or combined without first understanding what each number actually means.

The PE firm is preparing a board report. They need that number. They need to trust it. And right now, they can't have either.

This is the moment a data platform becomes necessary — not as a technical project, but as a business requirement. The cost of not knowing the combined revenue figure is higher than the cost of building the infrastructure to produce it reliably.

DataForest's work on this engagement — which you'll hear more about throughout this course — is built around solving exactly that problem.

### 3. Story 2: The 16.8 Million Records — NexGen Cloud

NexGen Cloud operates a GPU infrastructure platform. Their customers spin up compute resources, use them, and get billed. At scale, that means millions of billing events every month.

During a review of their billing data, something unusual surfaced. 16.8 million billing records could not be matched to any price entry in the system. These weren't small rounding errors or a handful of edge cases. 16.8 million records — representing an unknown but potentially significant amount of revenue — existed in the billing system with no corresponding price.

Were these records legitimate usage that hadn't been priced? A system configuration gap where certain resource types were never set up with a price? A sign of something more serious?

No one knew. Because there was no analytical layer sitting above the raw billing data. There was no system designed to surface patterns like this, flag anomalies, or reconcile what was billed against what was priced. The data was there — it had always been there — but it was sitting in a form no one could interrogate.

The consequence wasn't just an engineering problem to fix. It was months of financial uncertainty for two teams. Finance couldn't close their books confidently. Operations couldn't explain the gap. And every week the question went unanswered, the potential exposure grew.

Again, the same principle: the cost of not knowing — in this case, not knowing whether 16.8 million records represented real revenue risk — eventually exceeded the cost of building a system that could answer the question.

### 4. Story 3: The Denial Revenue Erosion — Sagis Diagnostics

Sagis Diagnostics runs a network of clinical labs. Like every healthcare provider that works with insurance, they submit claims. Some of those claims get denied. A denied claim isn't necessarily lost revenue — it can be appealed, corrected, and resubmitted. But only if someone catches it in time.

The problem at Sagis was visibility. Claims data existed across multiple systems. Denial information came back from insurers in various formats. There was no single place where the right person could look at any given moment and see: these claims have been denied, these ones are still recoverable, and these ones we've already missed the appeal window on.

The result was a slow, quiet erosion of recoverable revenue. No single dramatic failure — just a steady pattern of denied claims that nobody chased, not because no one cared, but because no one could see them clearly enough to act on them.

A data platform doesn't need to be glamorous to be valuable. In this case, the value was simple: make the right information visible to the right person at the right time. When you can see which claims need chasing, you can chase them. When you can't, you can't.

The cost of not knowing, here, was measured in real dollars quietly walking out the door every month.

### 5. The core idea

Three industries. Three different problems. Three different numbers that nobody could answer.

But the same underlying pattern in each case: information existed, somewhere, in some system — but it existed in a form that couldn't be used to make a decision, close a book, or catch a problem in time.

That gap — between data that exists and insight that's usable — is what DataForest builds infrastructure to close.

You don't need to understand the technical details of how we do that yet. What you need to understand right now is why. Because every technical decision you'll learn about in this course — every layer, every test, every design constraint — is in service of one thing: making it possible for someone to get a reliable answer to a question that matters.

That's why we build data platforms.

Before you move on, here's a quick scenario. There's no penalty for getting this wrong — just read it carefully and pick the response that feels right to you.

#### Quiz: You're three weeks into a new engagement. The client is a PE-backed manufacturing business — similar to the RMC-Norkem situation you just heard about. A VP of Finance has flagged something urgent: combined revenue is showing $8.4 million higher than expected following a recent acquisition integration. You have 10 minutes before a board call. You need to give the VP a credible first step. What do you do?

- {'id': '3gwxv2n', 'text': 'Check the Gold table filters — there may be a duplication or misconfigured aggregation in the reporting layer.', 'feedback': "Both A and B are legitimate investigation steps — and in a longer timeline, you'd want to do both. But with 10 minutes and a board call imminent, they're too slow. Pipeline checks and Bronze-level comparisons take time, and they assume the problem is a technical error."}
- {'id': '140lf2t', 'text': 'Go back to Bronze-level source data and compare the raw figures from each ERP directly.', 'feedback': "Both A and B are legitimate investigation steps — and in a longer timeline, you'd want to do both. But with 10 minutes and a board call imminent, they're too slow. Pipeline checks and Bronze-level comparisons take time, and they assume the problem is a technical error."}
- {'id': 'p46rxtq', 'text': 'Ask the domain expert which revenue recognition methodology was approved for the combined entity.', 'feedback': "The $8.4M discrepancy turned out not to be a pipeline bug at all. It was a methodology difference. The domain expert had worked with the PE fund's finance team to approve a specific revenue recognition rule — and the engineer implementing the pipeline had interpreted it differently. No amount of looking at Gold filters or Bronze tables would have surfaced that quickly. The fastest path to the root cause ran through the person who knew what the number was supposed to mean."}

### 6. The takeaway

A data platform doesn't just move data from one place to another. It encodes business decisions — about what to count, how to count it, and what the result should represent. When numbers are wrong, the first question often isn't "what broke in the pipeline?" It's "what business decision is this pipeline trying to reflect, and is it reflecting it correctly?"

That question gets answered by a domain expert, not a SQL query.

Now that you understand why data platforms get built, Module 2 will show you how they're structured — specifically, the three-layer architecture that DataForest uses across every engagement, regardless of industry or tech stack.

See you there.
