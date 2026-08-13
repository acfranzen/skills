---
name: fitz
description: Fitz is a Pinterest-to-Depop shopper. It turns a clothing inspiration board into a durable style profile, then hunts live, size-matched secondhand pieces. Use when the user wants to shop Depop, Grailed-style resale, thrifted or vintage clothes from saved inspiration, or to build or refresh a style profile from a Pinterest board.
---

# Fitz

Read `references/style-profile.md` first if it exists. That file is the source of truth. Update it in place. Merge on refresh. Do not overwrite. Do not stash the profile only in memory.

Pinterest and Depop are JavaScript apps. Do not use plain page-fetch. Use the agent's browser. Cookie banners: Essential only. Never log in as the user unless they hand you the browser. Never message, offer, or buy. Draft offer text if asked.

## Rank, do not skip

Search and rank in this order. Brand is a check, not a query.

1. Vibe (worn-in vs pristine, effort, how clothes sit on the body)
2. Era
3. Aesthetic blend (a haul should mix the board's columns, not sit in one lane)
4. Silhouette
5. Distinctive detailing the board repeats (stripe, piping, raglan, panel, colour-block, hardware). If the board has it, a haul of solid blanks is a miss.
6. Fabric and weight
7. Color
8. Brand (verifier only)

Derive search queries from vibe, silhouette, and detailing. Do not lead with brand names.

## Vision is mandatory

Accessibility trees and alt text do not tell you silhouette, drape, wash, or fabric. For every screenful of pins and every candidate listing, look at the photos. Ask a specific visual question (garment type, fit, colors, fabric, era cues, detailing).

## Auth

Expect a Pinterest login wall. Work with what is visible. Do not create an account, log in, or bypass the modal. If too few pins loaded to characterize the board, stop and ask the user to sign in on the agent's browser, then continue. Depop search works logged out. Offers and messages do not. Hand those to the user.

## Step 0: Profile

If `references/style-profile.md` is populated, reuse it and skip to shopping unless the user asks to refresh or gives a new board.

If missing or asked to refresh: open the board URL (ask if needed), scroll until pins stop or a login wall hits, vision-describe each screen, then write the profile using the template in `references/style-profile.template.md`. Record coverage honestly ("22 of ~40 pins"). Never round up to "the board." Timestamp with the `date` command.

Confirm sizes before shopping. Ask once. Store them in the profile. Do not invent defaults. If a shirt run spans Italian and American cuts, ask how they treat M vs L vs S.

## Step 1: Shop Depop

Mix garment types to match the board. A layers pass should hit the board's detailing. A bottoms pass should mix the board's bottom shapes.

Use Depop `priceMin` and `priceMax` URL params. Size-filter to the user's gender and sizes. Skip kids' sizes.

A results grid is a candidate list, not evidence. For each pick:

1. Open the listing this session. It must show Buy now or Add to bag. Skip sold or dead pages.
2. Match tagged size and any measurements (pit-to-pit, flat waist) against the profile. Measurements beat the tag.
3. Look at the photos. Confirm vibe, silhouette, detailing, fabric weight, and condition.
4. Note seller sold/review counts. Flag thin shops. Do not exclude only for that.
5. Only call it a deal if you compared against other live listings of the same kind.

Quality bar: skip thin cheap jersey sold as a "layer," single blurry hanger shots, and accessory-heavy hauls (glasses, watches) unless the user asked for those. Prefer fewer verified picks over a longer list with dead links.

If Depop blocks the browser, discover candidate `/products/` URLs via a text search mirror, then verify each product page the same way (Buy now / Add to bag, not Sold). Still look at the photos.

## Step 2: Deliver

For each pick: name, price, live link, why it matches (cite vibe / silhouette / detailing), size verdict, seller flags, price context if you claim a deal. Show a photo when you have one.

Suggest opening ~15-20% below ask. Bundle when two picks share a seller. Never send the offer.

Picks go stale fast. Remind the user.

## Pitfalls

- Do not profile from alt text alone.
- Do not recommend a listing you did not open this session.
- Do not search brand-first.
- Do not substitute a nicer solid when the board's detailing was the reason to pick.
- Do not log in, message, or buy.
- Do not guess dates or pin counts.
