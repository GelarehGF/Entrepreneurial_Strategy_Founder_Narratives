# Strategy Codebook — Paper 4

**10 categories · 251 trigger phrases · 23–29 phrases per category**

Theoretical grounding: effectuation theory (Sarasvathy, 2001), bricolage theory (Baker & Nelson, 2005), lean startup methodology (Ries, 2011), and recent configurational entrepreneurship research (Combs et al., 2024; Schmidt et al., 2024).

---

## 1. `pivot`

**Definition:** Fundamental redirection of the venture's product, market, or business model in response to negative feedback or new information. The founder changes direction rather than adjusting within the same direction.

**Trigger phrases (representative):**
pivot, we pivoted, ended up pivoting, changed direction, shifted focus, changed course, moved into, moved away from, repositioned, adjusted strategy, reworked the model, changed approach, adapted the business, shifted the product, redirected, transitioned to, scrapped the idea, refined direction, switched focus, went in a different direction, take a different angle, reinvent ourselves, go entirely new directions, shift the target market, change the trajectory, we had to change, that didn't work, we changed everything

---

## 2. `experimentation`

**Definition:** Small-scale trial of a hypothesis before full commitment. The founder tries something to learn whether it works, with the option to stop cheaply.

**Trigger phrases (representative):**
test it, run a test, trial and error, we tested, we experimented, pilot, pilot project, beta, prototype, MVP, minimum viable product, validate, proof of concept, iterate, try it out, see if it works, experiment with, test the market, small-scale test, run an experiment, low-risk test, test the assumption, test the idea, try before we commit, fail fast, learning experiment

---

## 3. `customer_discovery`

**Definition:** Direct engagement with potential customers to validate demand, uncover pain points, or refine the value proposition. Talking to buyers before building.

**Trigger phrases (representative):**
talk to customers, customer interviews, understand the pain point, get out of the building, validate demand, market research, customer feedback, user research, discovery, listen to customers, survey customers, interview users, learn from customers, test with customers, customer conversations, understand the user, find the customer, talk to potential buyers, identify customer needs, customer problem

---

## 4. `resource_substitution`

**Definition:** Using at-hand or unconventional resources in place of the resources conventionally required. Bricolage in Baker & Nelson's sense.

**Trigger phrases (representative):**
made do with, used what we had, bootstrapped, improvised, cobbled together, no budget so we, in place of, substitute, workaround, creative solution, use existing resources, repurpose, leverage what we have, low-cost alternative, free tools, barter, traded services, non-cash, sweat equity, hack together, jury-rigged, makeshift, found a way without

---

## 5. `sequencing`

**Definition:** Deliberate ordering of strategic moves across time. Deciding what to do first, second, and later rather than doing everything at once.

**Trigger phrases (representative):**
first we then we, phase one, phase two, step by step, milestones, the order was, we waited to until, staged the launch, sequence, prioritize, one thing at a time, tackle first, build the foundation first, start with x then y, do this before that, phased approach, roadmap, build sequentially, in stages

---

## 6. `scaling`

**Definition:** Growing the venture through increased volume, geographic expansion, or team expansion. Doing more of what already works.

**Trigger phrases (representative):**
scaled up, grew fast, expanded, 10x, hired more, went nationwide, open new offices, increase volume, growth, rapid growth, scale the business, scale up, scaling, scale our team, geographic expansion, new markets, new regions, double in size, grow revenues, expand operations, increase capacity, more customers, build out, replicate the model

---

## 7. `optimization`

**Definition:** Improving existing operations for lower cost, higher throughput, or better margins, without changing the fundamental business model. Efficiency, not redirection.

**Trigger phrases (representative):**
more efficient, reduced cost, streamlined, improved margins, cut waste, faster turnaround, better unit economics, optimize, operational efficiency, process improvement, reduce overhead, automate, lean operations, improve productivity, increase throughput, decrease cost, improve conversion, reduce churn, improve retention, better systems, repeatable process

---

## 8. `capability_building`

**Definition:** Developing new skills, expertise, or organizational capacity that did not previously exist inside the venture. Learning that upgrades what the team can do.

**Trigger phrases (representative):**
learned how to, taught ourselves, built expertise in, trained the team, developed the skill, figured out how, became proficient, upskilled, hired for capability, built internal capability, developed the competency, knowledge building, skill development, organizational learning, build the team's ability, invest in learning, develop the technology, build the platform

---

## 9. `partnering`

**Definition:** Collaborative relationships with external parties (customers, suppliers, other startups, investors, institutions) for mutual benefit. Working with someone outside the venture.

**Trigger phrases (representative):**
partnered with, joint venture, worked with, collaboration, teamed up, alliance, co-developed, went to market with, strategic partnership, partner, collaborator, worked together, joined forces, aligned with, brought in, contracted with, outsourced to, referral partnership, channel partner, distribution partnership, licensing agreement, co-founders, advisor network

---

## 10. `legitimation`

**Definition:** Establishing credibility, reputation, or acceptance from external audiences. Getting recognized, endorsed, certified, or trusted.

**Trigger phrases (representative):**
built credibility, recognized as, trusted by, positioned as the go-to, awards, certification, endorsement, reputation, thought leadership, press coverage, media recognition, industry validation, accreditation, testimonials, social proof, brand building, authority, established name, known for, respected in the industry, featured in, invited to speak

---

## Exclusion Rules

Three exclusion rules govern boundaries where prior typologies have been ambiguous:

1. **Financial vs. talent:** "We could not afford to hire X" → `financial` (binding constraint is capital, not labor market)
2. **Capability vs. talent:** "We didn't know how to do X" → `capability_building` (binding constraint is internal knowledge, not recruitment)
3. **Self-imposed constraint vs. strategy:** "We chose not to do X for ethical reasons" → coded as `self_imposed` constraint, not as strategy

---

## Coding Protocol

- **Unit of analysis:** individual sentence
- **Method:** regex-based multi-label matching with word boundaries (`\b`)
- **Multi-label:** a sentence may carry 0 to N strategy labels
- **Primary label:** when multiple labels present, the first match by codebook order is designated primary for sequence analysis
- **Minimum sentence length:** 40 characters (fragments excluded)
- **Maximum sentence length:** 400 characters (used in validation sampling)

---

## References

- Baker, T., & Nelson, R. E. (2005). Creating something from nothing: Resource construction through entrepreneurial bricolage. *Administrative Science Quarterly, 50*(3), 329–366.
- Combs, J. G., Gruber, M., & Zahra, S. A. (2024). Four approaches to new venture creation. *Journal of Business Venturing, 39*(2), 106366.
- Ries, E. (2011). *The lean startup*. Crown Business.
- Sarasvathy, S. D. (2001). Causation and effectuation. *Academy of Management Review, 26*(2), 243–263.
- Schmidt, J., Priem, R., & Zanella, P. (2024). Customers, markets, and five archetypical value creation logics. *Journal of Management, 50*(6), 2317–2352.
