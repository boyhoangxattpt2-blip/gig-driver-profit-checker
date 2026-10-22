# Gig Driver Profit Checker

**Real money, not shiny payout.** A free, mobile-first profit calculator for delivery couriers and gig drivers in the United States and Canada.

**[Try the working interactive demo](https://boyhoangxattpt2-blip.github.io/gig-driver-profit-checker/)** · [Download the offline HTML](https://raw.githubusercontent.com/boyhoangxattpt2-blip/gig-driver-profit-checker/main/index.html)

## The question

> Would you rather take $20 for a long delivery, $12 for a medium delivery, or $9 for a short one?

A flashy payout number hides deadhead miles, waiting at a restaurant, and vehicle expenses. This tool compares **net dollars per hour**, not gross delivery pay.

## Three hypothetical offers, one real calculation

US example only. All three assume a combined vehicle operating cost of **$0.35/mile**, no tolls, and a required net hourly target of **$18/hour**.

| Offer | Payout | Total distance (including empty return) | Total time (including wait) | Net earnings | Net/hour | Decision |
|---|---:|---:|---:|---:|---:|---|
| A | $12 | 8 mi | 35 min | $9.20 | $15.77 | Skip |
| B | $9 | 3 mi | 25 min | $7.95 | **$19.08** | Accept |
| C | $20 | 15 mi | 55 min | $14.75 | $16.09 | Borderline |

**The smallest payout is the highest net hourly return in this example.** Verdicts are based on the tool's displayed thresholds and are guidance, not promises.

How it works:

```text
Operating cost = entire distance * all-in cost per distance unit
Net earnings   = payout (including tips) - operating cost - additional tolls/parking
Net per hour   = net earnings / (total minutes / 60)
Gross per hour = payout / (total minutes / 60)
```

The input includes total driving (pickup, drop-off, empty return) and all time (driving, waiting, parking). The vehicle cost is a single editable **all-in** figure covering fuel, maintenance, tires, and depreciation; do not add fuel again. US uses USD/mi; Canada uses CAD/km, with its own editable assumptions and **no automatic FX conversion**. Figures are estimates, not financial, tax, mileage, insurance, or legal advice.

## A little app made by Muse AI

I work in courier logistics and gave **Muse** a detailed problem statement: turn delivery payout, distance, time, and expense assumptions into a single-file mobile tool. Muse created the HTML/CSS/JavaScript implementation and an accompanying set of logic tests. I then downloaded the generated `index.html` and independently opened it in a browser, tested all three offers, checked zero-minute validation, inspected the locale switch, and published it here.

**Evidence, not hype:**

- Muse reported **49/49** internal logic assertions passing (self-reported).
- Independent live-page browser tests matched the expected A/B/C net and hourly results above.
- A zero-minute input is rejected instead of dividing by zero.
- The Canada button switches currency/distance labels and its per-km default without a fabricated exchange rate.
- Public HTML is a standalone file (~30 KB): no backend, account, cookies, analytics, or external JS/CSS required for calculator operation.
- Your entered offers stay in your own browser; this site does not upload them.

## Build your own tiny tool

Try this prompt in Muse and replace the bracketed part with your own problem:

> Act as my personal app builder and create a single standalone index.html file (embedded CSS and JavaScript, no external libraries, no tracking, no cookies, works offline) for this idea: [describe your idea in 2-3 sentences, whom it serves, the 3-5 inputs, and the one result it should calculate]. Make it mobile-first and accessible, validate inputs (no negative numbers, NaN, or division by zero), show a transparent math breakdown, include three clearly hypothetical examples, test it in code, fix failures, and deliver the usable file.

The **full detailed builder requirements** can be reconstructed from the HTML and documented in [the original assignment](#project-origin); reproducibility does not require this tool's source to be secret.

### Try Muse, if eligible

If you are a **new eligible Muse user**, you can visit [muse.ai/join](https://muse.ai/join) and redeem invite code **`03THHA`** in Muse Settings within 48 hours of joining. At the time this was built, eligible redemptions awarded **1 billion bonus Muse tokens to each of us**. **Disclosure:** I receive the same bonus if you successfully redeem my referral code. Availability and program rules can change. This demo and repository are independently created; not sponsored by or affiliated with Meta or any delivery platform.

## Free forever, editable, portable

Clone/download `index.html` and open it locally to use it without an internet connection. Change the examples, defaults, styling, and formulas if you want; review the code before using it. No API key, ads, or subscription is needed to use the calculator.

## Project origin

Created October 22, 2026, in a live collaboration between a delivery worker, Muse (the AI builder), and independent browser QA. The aim is to show a small, **real utility**, not to advertise AI with empty claims. For anyone experimenting with agent-built software: always audit and verify the working artifact before sharing.

### En bref (Canada francophone)

**Quel trajet rapporte le plus apres les frais ?** Entrez le paiement, les kilometres totaux **y compris le retour a vide**, le temps total avec l'attente, et le cout reel de votre vehicule par km. Le calculateur indique le revenu net par heure en **CAD/km**, sans conversion de devise. Trois offres fictives sont incluses. [Essayer le calculateur gratuit](https://boyhoangxattpt2-blip.github.io/gig-driver-profit-checker/). L'interface principale est en anglais.

---

Built with Muse AI · independently tested and published by the repo owner · © 2026
