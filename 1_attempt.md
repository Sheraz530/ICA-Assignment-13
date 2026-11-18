# Attempt Before AI — Week 3

**Commit Hash (SHA-256, first 12 chars):** `ea74587cc2e3`

## Part 1A: Summary Statistics & Reporting Choice

| Item | Mean (PKR/kg) | Median (PKR/kg) | Opening Avg (2026-01-01) | Closing Avg (2026-03-19) | First-to-Last Change | Statistic to Report & Why |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Staple A** | 111.17 | 111.75 | 104.00 | 117.50 | +12.98% | **Median + % Change:** Mean and median are nearly identical; median protects against future entry typos while % change shows the trend. |
| **Oil B** | 324.83 | 324.00 | 301.00 | 347.00 | +15.28% | **Mean + % Change:** Prices climb smoothly every week with no extreme spikes so the mean reflects the progression accurately.
| **Pulse C** | 205.92 | 206.00 | 203.00 | 210.50 | +3.69% | **Median:** Prices oscillate tightly between 200.0 and 213.5 PKR/kg; the median sits right at the recurring mid-point. |
| **Sweetener D** | 166.75 | 166.75 | 152.00 | 181.50 | +19.41% | **Mean/Median + % Change:** Both averages are identical (166.75); reporting the +19.41% jump is vital so the rise is not masked. |

---

## Part 1B: Week 2 Flagged-Value Sensitivity Check (Staple A)

- **With Flagged Value (`1145.0` typo included):** Mean = **PKR 154.10/kg** | Median = **PKR 111.75/kg**
- **Without Flagged Value (Cleaned `114.5`):** Mean = **PKR 111.17/kg** | Median = **PKR 111.75/kg**
- **Explanation:** Including a single decimal-shift typo inflates the mean by **+PKR 42.93/kg (+38.6%)**, making Staple A look artificially expensive. The median remains **PKR 111.75/kg** because it depends solely on the middle rank order, ignoring extreme values.

# Part 1C: Draft Referee's Note (Labelled `O` / `E` / `C`)

**Referee's Note: Did Staple Prices Really Rise, or Are Both Neighbours Looking at Different Things?**

Over the twelve weekly observations from 1 January to 19 March 2026 across City 1 and City 2, prices rose for all four tracked items in the teaching dataset `[O]`. Sweetener D recorded the sharpest first-to-last increase at 19.41% (from an average of PKR 152.00/kg to PKR 181.50/kg), followed by Oil B at 15.28% (PKR 301.00 to PKR 347.00/kg) and Staple A at 12.98% (PKR 104.00 to PKR 117.50/kg), while Pulse C rose modestly by 3.69% (PKR 203.00 to PKR 210.50/kg) `[O]`. Across the full period, the mean and median sit close together for every item: PKR 111.17 vs PKR 111.75 for Staple A, PKR 324.83 vs PKR 324.00 for Oil B, PKR 205.92 vs PKR 206.00 for Pulse C, and PKR 166.75 vs PKR 166.75 for Sweetener D `[O]`. Because the cleaned series has no extreme spikes and moves steadily upward, the mean and median tell almost the same story about the overall level `[E]`. Where neighbours talk past each other is when one cites a period-wide average while the other compares January's opening price against March's closing price `[E]`. Moreover, if a single uncleaned entry error enters the log—such as a decimal-shift typo turning PKR 114.50 into PKR 1,145.00—the mean jumps to PKR 154.10 while the median stays unchanged at PKR 111.75 `[O]`. Therefore, quoting the median protects against unverified spikes, while pairing it with the first-to-last percentage change shows the actual direction of travel `[E]`.
