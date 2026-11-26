**English** | [日本語](2026-go-codegolf-benchmark.ja.md)

# go/codegolf benchmark: code size under a fixed search budget

## Overview

- A benchmark built from 32 problems from a 2015 internal Google code-golf contest, run across eight programming languages.
- Each problem–language cell rewards the shortest passing program relative to the moving best-known size. The historical human comparison uses three languages.
- The score measures compactness on supplied tests and specific runtimes. Historical human records, ranked model runs, and oracle reference runs use different conditions.

## Six practical takeaways

- Thirty-two problems across eight languages make 256 cells. A ranked model gets a fresh session with 30 minutes per cell.
- Models receive the statement and full tests, and can execute candidates in the sandbox. Submission tests determine eligibility.
- Each passing cell scores (best-known bytes / submitted bytes)², and an unsolved cell scores zero. Overall averages all 256 cells.
- The matched human comparison averages 96 JavaScript, Python and C++ cells. GPT‑6.2 Astra at max scored 92.265%, versus 87.533% for the human records.
- Across those 96 cells, the shortest ranked model entry beats the human record in 62, ties in 20, and trails it in 14, excluding the oracle.
- Proposed use. For a controlled comparison, pin the result data, runtime, reference sizes, time budget, tools and reasoning setting.

## Publication and review scope

Bin Jin (bjin / @binjin), go/codegolf benchmark. On November 27, 2026 JST, reviewed the project’s rules and leaderboard and recalculated the aggregates from the published result data. Candidate solutions and sandboxes were not run.

## Evidence and limitations

- The four historical languages are JavaScript, Python, C++ and Haskell. Ruby, Raku, Racket and GolfScript extend the set. Haskell contributes to the model Overall score, and the main historical comparison uses JavaScript, Python and C++. The human row has no displayed Overall score.
- Reference lengths may come from humans, ranked models, or an unranked oracle. Oracle runs had internet access, additional solution material including hidden human entries, and no comparable time limit. A shorter reference can lower other scores without altering their solutions.
- Human records combine submissions from the week-long contest and later challenges. Model settings can vary by entry, and original languages use historical runtimes such as Python 2.7. Test-set-specific solutions are permitted by the rules. Production maintainability, security and behavior beyond the tests require separate evidence.

## Application and low-cost check

Proposed and untried. Recompute both aggregates from the pinned result file, document the denominator and handling of missing entries, and report absolute passing-cell counts separately. For a fresh evaluation, use identical model settings and judge environments where feasible.

## Related notes

- [FrontierHarness evaluation](2026-frontierharness-eval-v1-1.md)
- [Claude Code verification practices](2026-claude-code-verification-practices.md)

## Sources

- [Official leaderboard](https://bjin.github.io/go-codegolf-benchmark/#leaderboard)
- [Official benchmark rules](https://bjin.github.io/go-codegolf-benchmark/#about)
- [Pinned leaderboard data](https://github.com/bjin/go-codegolf-benchmark/blob/e962571532c03f4ef4d64d9f371e0770216f7975/data.json)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
