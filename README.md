# NEO Next

A short, free reflection tool for young people thinking about what could come after school — and for the parents, carers, and practitioners around them.

**Live at:** [next.nudgeeducation.online](https://next.nudgeeducation.online)

## What it is

Seven questions. Six archetypes. One personalised next-step page. The whole thing takes about three minutes.

Built for the cohort that wouldn't normally engage with a careers advisor — young people aged 11–18 who aren't currently in mainstream school, often with EBSNA, anxiety, SEND, medical needs, or complex circumstances. NEO Next surfaces non-obvious paths (remote work, neurodivergent-friendly trades, peer-led roles) alongside the familiar ones.

The six archetypes are anchored to the RIASEC career-interests framework (used by O\*NET and most credible careers tools) but renamed for the audience:

| Archetype       | One-line                                                             |
| --------------- | -------------------------------------------------------------------- |
| Maker           | You'd rather build it than write about it.                           |
| Connector       | You notice how other people are feeling before they say anything.    |
| Investigator    | You'd open it up to see how it works.                                |
| Storyteller     | You turn what you see into something other people can feel.          |
| Organiser       | You'd rather have it sorted than have it perfect.                    |
| Pattern-spotter | You see the system underneath things.                                |

Each result links into the relevant strands of the [NEO Curriculum Vault](https://curriculum.nudgeeducation.online).

## Tech

A single static HTML file. No build step, no framework. Self-contained except for two external resources:

- **Google Fonts** (Fraunces + Inter) for typography
- **jsPDF** from cdnjs for the "Download as PDF" button

The cube on the landing page is plain CSS 3D transforms. Sharing uses URL hashes (`#you=maker:investigator`) so a shared link lands directly on the result.

## Email capture

The "Send me the pack" form on the result page POSTs to a Google Form in the admin@nudgeeducation.online workspace. Responses land in the `NEO Next — Follow-up Requests` sheet. The form's submission endpoint and field IDs are visible in the page source — this is intentional, the form accepts anonymous POSTs by design.

If you ever rebuild the form, you'll need to re-fetch the field IDs from the rendered viewform HTML — Google generates them separately from the IDs exposed by the Apps Script `FormApp` API. See the inline comment in `index.html`.

## Hosting

Served as a static site via GitHub Pages from this repo. Custom domain `next.nudgeeducation.online` configured via the `CNAME` file plus a GoDaddy CNAME record pointing at `nudgeeducation.github.io`.

The `.nojekyll` file disables Jekyll processing — this is a vanilla HTML site, not a Jekyll site.

## Operated by

[Nudge Education Ltd](https://nudgeeducation.online), Company Number 10192753. Part of [Nudge Education Online (NEO)](https://nudgeeducation.online), the online alternative provision opening September 2026.

## Licence

MIT — see `LICENSE`.
