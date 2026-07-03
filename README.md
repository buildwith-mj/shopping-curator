# 🛍️ Shopping Curator — an AI personal shopper you set up in 3 minutes

**Too many options. Too many tabs. Too much time.** Shopping Curator is a prompt-based AI shopping assistant that runs as a [Claude Project](https://claude.ai) — no code, no server, no installation. Tell it what you want, and it brings you real products (with verified links, prices, and sizes) matched to your body measurements, fit preferences, budget, and even your personal color season.

Built and QA'd by a non-developer through real-world use. Now at **v2.0 (Global)**.

## What it does

**Mode 1 — Recommend.** Say *"I want a white t-shirt for summer"* and it searches your favorite stores and returns up to 5 real products: exact product name, link, current price, available sizes, and one line on why each fits *you*.

**Mode 2 — Decide.** Paste 2–5 product links from your cart and ask *"which one?"* It compares garment measurements against your body measurements and gives one confident verdict: *this one, in this size* — plus what to double-check before ordering.

**What makes it trustworthy:**
- ✅ **Evidence-based verification** — a product is only marked "Verified" if the AI actually opened the page and read the price and size range from it. No hallucinated links.
- 🌍 **Your country, your stores** — you tell it where you shop (Nordstrom, Zalando, ASOS, anywhere); it prefers your country's store URLs and tests each new store to tell you honestly what level of service to expect.
- 🔒 **Privacy-aware** — your measurements stay inside your own Claude Project conversation. Nothing is sent anywhere else, and deleting the conversation deletes the data.

## Setup (under 3 minutes)

1. Log in at [claude.ai](https://claude.ai) (free plan works).
2. Go to **Projects → New project** (name it anything, e.g. "Shopping Curator").
3. Open **Set project instructions** and paste the full contents of [`instructions.md`](./instructions.md).
4. In project settings, make sure **Web search is turned ON** — without it, the assistant can't fetch products. ⚠️
5. Start a new chat inside the project and send your profile as the first message:

```
[MY PROFILE]
- Country/Region: 
- Shopping category: (womenswear / menswear / no preference)
- My stores: 
- Height / Weight: 
- Shoulder width: 
- Chest/Bust: 
- Waist: 
- Thigh: 
- Usual size: 
- Preferred fit: 
- Personal color season: (skip if you don't know — totally optional)
- Budget: 
- Notes: 
```

Leave unknown fields blank — but **do fill in Country and Shopping category**. Measurements sharpen size verdicts a lot: shoulders/chest for tops, waist/thigh for bottoms.

## Usage tips

- **Best flow:** Recommend → pick 2–3 favorites → paste them back for a size verdict → order.
- **A link is dead or redirects to the homepage?** Search the exact product name (always included) on that store's site. Names outlive links.
- **"⚠ Link unverified" mark?** The AI couldn't open that page itself — confirm via product-name search before buying.
- **Some stores only give "search keywords" instead of links?** That store blocks automated access (common for app-first marketplaces). The keyword guide is the honest fallback, not a bug.
- **Adding a store mid-chat** works instantly, but Claude Projects don't share memory between chats — add it to the "My stores" line of your profile to keep it.
- **Wrong gender category recommended?** Your "Shopping category" field is probably blank. Fill it and resend your profile.

## Known limitations (honest edition)

- Prices and stock are **as of search time** — always confirm on the product page.
- Search indexing quality varies by country and store. Global brands (Zara, H&M, COS, Uniqlo) work best; closed marketplaces degrade gracefully to keyword guides.
- Size advice is guidance, not a guarantee. When it's a close call, the assistant says so and tells you the deciding factor.
- This is a prompt, not software: verification is instructed, not code-enforced. Occasional misses happen — that's what [Issues](../../issues) are for.

## Repository structure

| File | What it is |
|---|---|
| `instructions.md` | The v2.0 Global project instructions (paste this into your Claude Project) |
| `README.md` | This page — what it is, how to set it up, known limits |

## Feedback & contributing

Found a dead link pattern, a store that misbehaves, or a sizing rule that misfires in your country? **Open an Issue** with the store name, your country, and what happened. Real-world QA is exactly how this project got from v1.0 to v2.0.

## Version history (highlights)

- **v2.0 (Global):** user-owned store roster with onboarding tests, country-aware locale rules, multi-language responses, cm/inch support, size-system conversion cautions, personal color made explicitly optional.
- **v1.4:** evidence rule (price + size range must be read from the fetched page to mark ✓) after a dead link slipped through; gender/category field added after a men's item was recommended to a womenswear user.
- **v1.3:** mandatory link verification, Korean-locale URL priority, third-party seller labeling; removed a brand with no Korean official store.
- **v1.2:** search-driven direct product recommendations.
- **v1.0–1.1:** compare mode, fit-ease rules, personal color rules, privacy rules.

---

Made with ☕ and a lot of dead links by **MJ** ([Build with MJ](https://example.com)) — a translator, not a developer, proving you can ship useful AI tools with prompts alone.
