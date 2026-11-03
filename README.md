---
license: cc-by-4.0
language:
- en
pretty_name: US Lottery Rules and Scores
size_categories:
- n<1K
task_categories:
- tabular-classification
tags:
- lottery
- united-states
- gambling
- consumer-finance
- taxes
- government-data
configs:
- config_name: state_rules
  data_files: us-state-lottery-rules.csv
- config_name: brand_scores
  data_files: us-lottery-brand-scores.csv
---

# US Lottery Rules and Scores

Two small, sourced tables about US lotteries, published by [USA Lottery Reviews](https://usalotteryreviews.com).

| File | Rows | What it holds |
|---|---|---|
| `us-state-lottery-rules.csv` | 53 | Per state: minimum age, state tax on winnings, prize claim deadline, winner anonymity, online sales, start year, where proceeds go. Each figure has its own source URL column. |
| `us-lottery-brand-scores.csv` | 71 | Per reviewed brand (state lotteries, national games, lottery apps, scratch-offs, sweepstakes): an overall score out of 10 and six criterion scores. |

Live, browsable versions with tile maps: <https://usalotteryreviews.com/data>

## Method

- Every figure in the rules table was read from an official page: the state lottery, its regulator, state statute, the state revenue department, or the IRS. The page is named in the `*_source` column.
- A figure is entered **only** if we read it on such a page. **An empty cell means "not yet verified", not "none" and not "zero".** Nothing is estimated or taken from news articles, aggregators or memory.
- Some official lottery sites block automated access, so coverage is incomplete. At the date below, claim deadlines are verified for 28 of 48 lottery states and state tax for 24 of 48.
- Claim deadlines are the general rule on an official page; draw and instant games can differ in some states. State tax is the state rate only: federal tax and local taxes are not included.
- Brand scores follow a published rubric (odds and value 25%, transparency 20%, player protection 20%, ease of play 15%, payouts and claims 10%, reputation 10%): <https://usalotteryreviews.com/methodology>. Scores are editorial judgements and are published with a written justification for each criterion on the brand's review page.

## Columns

`us-state-lottery-rules.csv`: `state`, `abbr`, `has_state_lottery`, `minimum_age`, `state_tax_rate_pct`, `state_tax_source`, `claim_deadline_days`, `claim_deadline_source`, `winner_anonymity` (`allowed`, `conditional`, `not-allowed`), `winner_anonymity_source`, `online_sales` (`yes`, `partial`, `no`), `lottery_since`, `proceeds_go_to`, `proceeds_source`, `last_verified`, `page`.

`us-lottery-brand-scores.csv`: `name`, `category`, `overall_score_10`, `odds_value_score`, `transparency_score`, `player_protection_score`, `ease_of_play_score`, `payouts_claims_score`, `reputation_score`, `official_site`, `last_verified`, `review`.

## Version and date

Version 2026.11.03. Data verified 2–3 November 2026. Updated as more states are verified; see <https://usalotteryreviews.com/changelog>.

## Licence and citation

Creative Commons Attribution 4.0 International (CC BY 4.0). You may copy, share and adapt the data, including commercially, if you credit USA Lottery Reviews and link to <https://usalotteryreviews.com/data>.

> USA Lottery Reviews. *US Lottery Rules and Scores*, version 2026.11.03. https://usalotteryreviews.com/data

Corrections: corrections@usalotteryreviews.com
