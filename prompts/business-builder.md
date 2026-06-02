# Business-Builder Prompt Chain

An ordered "idea to tiny business" sequence. Run the prompts **in order** — each one
takes the output of the last as input. Fill in every `[BRACKET]` before sending.

## The craft rule

> **Give Claude one job at a time, and chain prompts.** Don't ask for "good copy" or
> "a business plan" in one shot — that produces vague mush. Run one focused prompt, read
> the output, feed it into the next. Each step earns the next. The XML tags
> (`<role>`, `<task>`, `<steps>`, `<rules>`, `<output>`) are there to keep each job
> narrow and the output structured — keep them.

## The chain at a glance

| # | Prompt | When to use it |
|---|--------|----------------|
| 1 | Pressure-test the idea | Before you build anything — kill fatal flaws first. |
| 2 | Validate the problem | After the idea survives step 1 — is the pain real (painkiller vs vitamin)? |
| 3 | Design the offer | Once the problem is validated — turn it into something worth paying for. |
| 4 | Write the sales page | Once you have an offer — words that make people buy. |
| 5 | Plan the content | Once the page is live — drive traffic to it without burning out. |
| 6 | Find your first 10 customers | In parallel with content — get real, paying signal manually. |

A "no" at step 1 or 2 is a win: you just saved yourself months building the wrong thing.
Don't skip ahead to write copy for a problem you haven't validated.

---

## 1. Pressure-test the idea (find fatal flaws)

**When to use:** First. Before you write a line of code or copy, stress-test the idea
the way a YC partner reads an application — looking for the thing that kills it.

```
<role>Act as a startup evaluator in the mold of Paul Graham, who has reviewed thousands of applications and can spot within minutes which ideas die in week one and which ones are worth building.</role>

<task>Pressure-test my startup idea and find every fatal flaw before I waste a single month building the wrong thing.</task>

<context>
- Idea: [DESCRIBE THE IDEA IN 2-3 SENTENCES]
- Who it's for: [TARGET CUSTOMER]
- Why me: [YOUR RELEVANT BACKGROUND / UNFAIR ADVANTAGE]
</context>

<steps>
1. Identify the core assumption that must be true for this business to work.
2. Find the most likely reasons this idea fails — specific to this idea, ranked by severity, most dangerous first.
3. Test the problem: is this a real pain people pay to solve, or a nice-to-have?
4. Assess founder-market fit: why am I the right person to build this?
5. Deliver a brutally honest verdict: strong, weak, or pivot required.
</steps>

<rules>
- Every flaw must be specific to this idea — no generic startup advice.
- The core assumption must be testable before building anything.
- The verdict must be direct, never "it has potential, but...".
- Include only real flaws; do not pad to hit a number.
</rules>

<output>Core Assumption -> Fatal Flaws (ranked) -> Problem Reality Check -> Founder-Market Fit -> Brutal Verdict</output>
```

---

## 2. Validate the problem (painkiller vs vitamin)

**When to use:** After the idea survives step 1. Confirm the problem is real and urgent —
something people already lose sleep over and cobble together fixes for — not one you
invented in your head.

```
<role>Act as a customer-discovery specialist applying the "talk to users" framework: the only way to know a problem is real is to find people actively suffering from it and willing to pay for a fix.</role>

<task>Validate whether my idea solves a real problem people pay for, or a problem nobody actually has.</task>

<context>
- Idea: [DESCRIBE THE IDEA]
- Target customer: [WHO YOU THINK HAS THE PROBLEM]
</context>

<steps>
1. Define the specific pain: exactly what frustration the customer feels, and when.
2. Identify who has this problem most acutely — the early-adopter profile (a specific person, not a demographic).
3. Find the evidence: where are these people already complaining (forums, reviews, communities), and in what exact words?
4. Design 5 customer-discovery questions that reveal the truth without leading the witness.
5. Define validation criteria: what specific signals prove the problem is real and urgent.
6. Deliver an explicit verdict — painkiller (people actively seek a fix) or vitamin (nice-to-have) — and what that means for the business.
</steps>

<rules>
- The pain must be felt often and intensely enough that people actively seek a fix.
- The early adopter must be a specific, nameable type of person.
- Discovery questions must be open-ended and about past behavior, never hypothetical intent ("would you...").
- The painkiller-vs-vitamin verdict must be explicit, never implied.
- Test: are people currently cobbling together a workaround because nothing good exists?
</rules>

<output>Specific Pain -> Early-Adopter Profile -> Where They Complain (real language) -> 5 Discovery Questions -> Validation Criteria -> Painkiller or Vitamin Verdict</output>
```

---

## 3. Design the offer (Hormozi value equation)

**When to use:** Once the problem is validated. Turn the pain into an offer so good it
feels unreasonable to say no — using the value equation:
**value = (dream outcome × likelihood of success) ÷ (time delay × effort & sacrifice)**.

```
<role>Act as an offer strategist who applies the Hormozi value equation: maximize the dream outcome and the customer's perceived likelihood of achieving it, while minimizing the time delay and the effort and sacrifice required of them.</role>

<task>Design an offer for my validated problem that is so clearly valuable the right customer would feel stupid saying no.</task>

<context>
- Problem & customer (from step 2): [PASTE PAIN + EARLY-ADOPTER PROFILE]
- What I can deliver: [PRODUCT / SERVICE / SKILLS — e.g. "I'm good at X, Y"]
- Price range I'm considering: [PRICE OR "suggest one"]
</context>

<steps>
1. State the dream outcome: the specific result the customer actually wants.
2. Raise perceived likelihood of success: proof, guarantees, done-for-you elements, risk reversal.
3. Cut the time delay: how to get them a meaningful result faster.
4. Cut effort and sacrifice: remove the work, learning curve, and friction on their side.
5. Propose 3 offer variants, ranked by speed-to-launch and likelihood to convert, each with a price and a no-brainer guarantee.
6. Recommend one and explain why it wins on the value equation.
</steps>

<rules>
- Every element must move one lever of the value equation — name which lever.
- Include a concrete risk-reversal / guarantee; no offer ships without one.
- Rank by speed to launch and likelihood to convert, not by polish.
- No vague promises ("transform your life") — tie claims to the specific outcome.
</rules>

<output>Dream Outcome -> Likelihood Boosters -> Time-Delay Cuts -> Effort Cuts -> 3 Ranked Offers (price + guarantee) -> Recommended Offer + Why</output>
```

---

## 4. Write the sales page (AIDA)

**When to use:** Once you have an offer. Build the page **one job at a time** — hook,
then bullets, then the full page. Don't ask for the whole thing in one prompt.

> Run the three sub-prompts in order. Each one feeds the next.

**4a — Hook**
```
<role>Act as a direct-response copywriter. Your only job right now is the hook.</role>
<task>Write one-sentence hooks for [OFFER, from step 3].</task>
<context>Customer & pain: [PASTE FROM STEP 2]. Dream outcome: [PASTE FROM STEP 3].</context>
<rules>
- Anyone in the target audience must understand it in 5 seconds.
- Speak to the pain or the dream outcome, not the product's features.
- No hype, no "$1B", no fake urgency.
</rules>
<output>5 hook options, strongest first, each with one line on why it works.</output>
```

**4b — Bullets**
```
<role>Act as a direct-response copywriter. Your only job right now is the benefit bullets.</role>
<task>Write benefit-driven bullets that make [OFFER] irresistible, building on this hook: [PASTE CHOSEN HOOK].</task>
<rules>
- Each bullet is a benefit (what they get), not a feature (what it is).
- Concrete and specific; no "save time and money" filler.
- Tie each bullet back to the validated pain.
</rules>
<output>5-7 bullets, ordered most-compelling first.</output>
```

**4c — Full page (AIDA)**
```
<role>Act as a direct-response copywriter writing a one-page sales letter using the AIDA framework: Attention, Interest, Desire, Action.</role>

<task>Write a punchy one-page sales page for [OFFER] that reads like a smart friend explaining why you'd be foolish not to buy.</task>

<context>
- Hook: [PASTE CHOSEN HOOK]
- Bullets: [PASTE CHOSEN BULLETS]
- Offer + guarantee + price: [PASTE FROM STEP 3]
</context>

<steps>
1. Attention: open with the hook.
2. Interest: name the pain in the customer's own words and agitate it honestly.
3. Desire: present the offer, the bullets, the proof, and the risk-reversal guarantee.
4. Action: one clear CTA that makes the next step obvious.
</steps>

<rules>
- No fluff and no hype — every line earns its place; cut any line that doesn't.
- One CTA, repeated, never competing CTAs.
- Plain language a tired person on their phone can skim and still get.
- Match the claims to what step 3's offer actually delivers — no overpromising.
</rules>

<output>A complete one-page sales letter: Headline -> Pain -> Offer + Bullets + Proof + Guarantee -> Single CTA.</output>
```

---

## 5. Plan the content (drive traffic to the page)

**When to use:** Once the page is live. Plan content that earns attention and sends it to
the offer — a sustainable cadence you can actually keep, not a viral fantasy.

```
<role>Act as a content strategist. Every post must do one job: drive traffic to the offer or build trust with the target customer. No posting for the sake of posting.</role>

<task>Build a 7-day content plan for [OFFER] aimed at [TARGET CUSTOMER].</task>

<context>
- Platforms my customers actually use: [e.g. Instagram, Threads, LinkedIn, X]
- Format constraint: [e.g. "faceless / text + graphics" or "short video"]
- The page I'm driving to: [URL OR "the step-4 sales page"]
</context>

<steps>
1. Confirm which 1-2 platforms to focus on, based on where this customer actually spends time.
2. For each of 7 days, give: a hook, the value point, and a CTA (traffic or trust).
3. Note posting cadence and the single success metric to watch per channel.
4. List 3-5 reusable content angles I can test, so I'm not inventing posts from scratch.
</steps>

<rules>
- Every post drives traffic or builds trust — state which, for each.
- Cadence must be sustainable for one person; don't prescribe 3 posts a day.
- Hooks must be specific to the validated pain, not generic motivation.
- No engagement-bait or follower-count vanity metrics; tie metrics to clicks/signups.
</rules>

<output>Platform Focus -> 7-Day Plan (hook / value / CTA per day) -> Cadence + Metric -> 3-5 Reusable Angles</output>
```

---

## 6. Find your first 10 customers (do things that don't scale)

**When to use:** In parallel with content. Get your first paying customers **manually** —
personally, before any automation — because that's the only way to get real signal early.

```
<role>Act as an early-traction specialist applying the "do things that don't scale" framework: the fastest path to product-market fit is finding 10 people who use and pay for your product, found by hand, before automating anything.</role>

<task>Build a specific plan to find and convert my first 10 customers — manually and personally.</task>

<context>
- Offer: [PASTE FROM STEP 3]
- Target customer: [PASTE FROM STEP 2]
</context>

<steps>
1. Identify exactly where my first 10 customers are right now — specific communities, forums, or networks (name them).
2. Design a personal outreach approach — how to reach them one-to-one, no automation.
3. Write the first message: specific, personal, leads with genuine value, asks only for a conversation — not a sale.
4. Define success: what these 10 must actually DO (pay, repeat-use) to prove real demand.
5. Build a weekly milestone plan from 0 to 10 customers, with concrete actions each week.
</steps>

<rules>
- First 10 found manually — no ads, no automation, no mass DMs.
- Outreach is personal; a message that could be sent to anyone reveals nothing.
- The first message asks for a conversation, never a sale, and never begs.
- Success criteria are behavioral (payment, repeat use), not "they seem interested".
- No template that sounds like a template.
</rules>

<output>Where the First 10 Are -> Manual Outreach Approach -> First Message -> Behavioral Success Criteria -> Weekly Milestone Plan</output>
```

---

## Notes & caveats

- **Order matters.** Steps 1-2 are gatekeepers. If the idea or problem fails, stop and
  fix or pivot before spending effort on offer, copy, or content.
- **Parameterise honestly.** The output is only as good as what you put in the
  `[BRACKETS]`. Vague inputs → vague outputs.
- **One job per prompt.** If a step balloons, split it (step 4 is already split into 4a/4b/4c).
- **No magic timelines.** These prompts replace guesswork with structure; they don't
  promise a "business in a weekend" or any particular revenue. Real validation takes real
  conversations with real customers.
