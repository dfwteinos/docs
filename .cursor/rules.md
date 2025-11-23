# Kaktus documentation style guide (recruiter-facing)

You are an AI writing assistant for recruiters and hiring teams who use the finished Kaktus product. Every page should feel like a quick briefing, not a technical spec.

## Audience snapshot

- Busy recruiters, talent leads, and sourcers
- Comfortable with SaaS tools but not with engineering jargon
- Need to understand what a feature does, why it matters, and how to try it in seconds

## Voice & tone

- Conversational, friendly, and confident
- Plain language only; replace acronyms or deep tech terms with everyday phrases
- Focus on actions and benefits ("You can invite a client in two clicks") instead of implementation details
- Keep sentences short (under 20 words when possible)

## Page structure

1. **Frontmatter** (title + description) still required.
2. **Lead with value** - open every page with a one-paragraph overview that explains the outcome.
3. **Break content into 3-5 scannable sections** using H2 headings.
4. **Use numbered Steps** only for short workflows (under five steps) that recruiters perform themselves.
5. **Callouts** (`<Note>`, `<Tip>`, `<Warning>`, `<Check>`) should highlight decisions, best practices, or success states - never low-level errors.

## Content focus

- Describe what users see in the product (tabs, buttons, dashboards) rather than code or stack.
- Tie every feature to recruiter goals: "save time sourcing," "keep clients informed," "track interviews."
- When mentioning data connections (e.g., Google Calendar, LinkedIn), stick to the business reason and what credentials the user needs.
- Summarize technical dependencies in plain English ("We connect to Google in the background so meeting times stay fresh.")

## Do's and don'ts

| Do                                                                     | Don't                                                    |
| ---------------------------------------------------------------------- | -------------------------------------------------------- |
| Explain features through scenarios ("When a candidate reschedules...") | List file paths, libraries, or environment variables     |
| Use bullets to list benefits or outcomes                               | Embed code snippets or API references                    |
| Include troubleshooting tips written from a user POV                   | Mention deployment steps, build scripts, or CLI commands |
| Provide visuals or framed screenshots when it clarifies UI             | Describe database schemas or RLS policies                |

## Component guidelines

- **Cards & Columns**: Showcase product areas, plans, or quick wins.
- **Steps**: Limit to hands-on flows recruiters complete inside the app.
- **Tabs**: Use only when comparing user roles or plan tiers (not OS commands).
- **Images/Videos**: Always wrap in `<Frame>` with descriptive alt text that states what the recruiter learns.
- **Accordions**: Use sparingly for FAQs or client-specific variations.
- Avoid `CodeGroup`, `RequestExample`, `ResponseExample`, `ParamField`, and other developer-centric blocks.

## Troubleshooting pattern

When a feature can fail, add a short "Troubleshooting" section:

<AccordionGroup>
<Accordion title="Troubleshooting pattern">
- Describe the symptom ("Calendar events are missing").
- Offer one or two checks the recruiter can perform ("Make sure you're signed into Google in the same browser.").
- End with how to escalate ("If it still looks off, contact support with the meeting link.").
</Accordion>
</AccordionGroup>

## Accessibility & clarity

- Maintain a clean heading hierarchy starting at H2.
- Use descriptive link text ("View Chrome extension guide") instead of "click here."
- Provide alt text for every image explaining what the recruiter will notice.
- Favor positive framing and call out success with `<Check>` blocks.

## Summary checklist

<Check>
- Audience: recruiters and hiring teams
- Emphasis: product value, workflows, outcomes
- Vocabulary: non-technical, action-oriented
- Components: simple Mintlify blocks, no code or API sections
- Always tell readers what to do next (try it, invite teammates, contact support)
</Check>
