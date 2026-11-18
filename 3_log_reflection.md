## Part 2 & 3: Interpretation Auditor & Colour Check

| # | AI Claim | Colour | How I Checked | Verdict |
| :-: | :--- | :---: | :--- | :---: |
| 1 | "Sweetener D saw the largest relative price surge at 19.41%, rising from PKR 152.00 to PKR 181.50 per kg." | **Green** |# Audit Table, Confused Classmate & Reflection
 Recomputed `(181.50 - 152.00) / 152.00 * 100 = 19.41%` directly from CSV. | **Accepted** |
| 2 | "For all four items, the mean and median differ by less than 1 PKR, showing roughly symmetric distributions." | **Amber** | Verified absolute differences in Python (all < 0.85 PKR); valid explanation. | **Accepted** |
| 3 | "Oil B's 15.28% increase was driven by global edible oil supply chain disruptions and import tariff hikes." | **Red** | Checked dataset columns; no data exists on supply chains, imports, or tariffs. | **Rejected** |
| 4 | "Pulse C remained the most price-stable item, changing by only 3.69% between January 1 and March 19." | **Green** | Recomputed `(210.50 - 203.00) / 203.00 * 100 = 3.69%` (lowest change). | **Accepted** |
| 5 | "Because Staple A's mean is below its median, household purchasing power in City 1 dropped faster." | **Red** | No income or household budget data exists in the file; claim is unsupported. | **Rejected** |

## Part 4: Confused Classmate Transcript Excerpt

> **Classmate (AI):** I still don't get why anyone uses the median. The mean adds up every single price and divides equally, so isn't the mean *always* the true typical price?
>
> **Sheraz:** Only when prices are balanced without weird spikes. Imagine five shops sell Staple A for 110, 111, 112, 112, and 113. Both mean and median are around 111.6. Now suppose one clerk accidentally types 1,130 instead of 113. What happens to the mean?
>
> **Classmate (AI):** It jumps to around 315. But why does that make the median better?
>
> **Sheraz:** Exactly—nobody paid 315. The median lines the five prices up (`110, 111, 112, 112, 1130`) and picks the middle one (`112`). That middle number reflects what a normal customer actually pays.
>
> **Classmate (AI):** Oh, so the mean gets dragged toward extreme numbers because it sums actual rupee amounts, whereas the median only cares about the middle position?
> **Sheraz:** Spot on. Use the mean when every number is verified; use the median when a single typo would distort what "typical" looks like.

---

## Part 5: Reflection

In my first draft, I initially wrote that "prices became unaffordable for households" before tightening the text. That went beyond what the data allows: the dataset only tracks nominal item prices per kilogram in two anonymous cities—it contains no wage or income figures. Keeping the final note strictly focused on price levels and dispersion ensured every sentence stayed within the evidence.

---

## AI Use Log

- **Gate 1 (Before AI):** Computed all item means, medians, percentage changes, and the Week 2 flagged-value comparison in Python first, then wrote and hashed `1_attempt.md` (`ea74587cc2e3`) prior to querying any AI.
- **Gate 2 (Role Used):** Used AI strictly as an *Interpretation Auditor* (Part 2) and *Confused Classmate* (Part 4). Did not copy AI-generated prose into `1_attempt.md`.
- **Gate 3 (Verification):** Recomputed every number cited by the AI; flagged and rejected two unsupported causal/external claims.
