# Contributing

This list is curated around reliability claims for Concept Bottleneck Models (CBMs).

## Inclusion Criteria

A paper is a good fit if it changes at least one of these questions:

- Are the concepts semantically grounded, stable, and complete enough for the task?
- Does prediction actually pass through the stated concepts, or can signal bypass the interface?
- Do interventions model realistic human control rather than oracle correction?
- Does the concept interface express uncertainty, ambiguity, perturbation sensitivity, or shift?
- What semantic control is lost when supervision becomes post-hoc, weak, label-free, or language-guided?
- Which classical CBM assumption breaks in continual, multimodal, generative, or adversarial settings?

## What Not To Add

- Application-only papers unless they expose a transferable reliability lesson.
- Minor architecture variants that do not change the claim-evidence standard.
- Generic XAI papers unless they are useful background for concept-based explanation or trustworthy interpretability.
- Papers with unclear metadata or unavailable manuscript links.

## Entry Format

Use this format:

```markdown
- **Paper Title** - Author et al., Venue Year. One-sentence reason the paper matters for CBM reliability.
```

If the paper is a preprint, mark it as a preprint rather than presenting it as settled evidence.

## Review Checklist

Before adding a paper, check:

- Does the title match the linked paper exactly?
- Are venue and year correct?
- Is the link stable?
- Does the paper fit the section where it is being added?
- Does the entry make clear whether the evidence is mature, emerging, or frontier?
