# Futures prop firm rules, as data (50K accounts)

A small, hand-checked, open dataset of the rules of popular **futures prop firm** 50K evaluation accounts: profit target, trailing drawdown (and where it locks), daily loss limit, consistency rule, minimum and maximum days. One row per account type, with a link to the firm's own help-center page as the source.

- `rules.json` – structured data, with notes and sources
- `rules.csv` – the same, for spreadsheets

**Snapshot:** October 2026 (`last_updated` in the JSON). Firms change rules often. Treat this as a starting point and **always confirm on the firm's website** before paying for anything. This is education, not investment or financial advice.

Firms covered: Apex Trader Funding (4.0 and legacy), Lucid Trading (Flex and Pro), Tradeify (Select), Topstep (Trading Combine) and MyFundedFutures (Pro).

## Use it

```python
import json
rules = json.load(open("rules.json"))["accounts"]
for a in rules:
    print(a["name"], a["profit_target"], a["max_drawdown"], a["daily_loss_limit"])
```

## Want to see what the rules do to your odds?

The rules above feed a free simulator that estimates your pass rate with your own win rate and risk, and a set of explainers with numbers from our own simulations:

- Simulator and lab: https://fondeoreal.com/en/?utm_source=github&utm_medium=repo&utm_campaign=prop-firm-rules
- Daily loss limit, trailing drawdown and consistency rules explained with data: https://fondeoreal.com/en/prop-firm-lab/?utm_source=github&utm_medium=repo&utm_campaign=prop-firm-rules

## Contributing

Found a rule that changed? Open an issue with a link to the firm's official page and we will update the data.

## License

Data under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit: "FondeoReal (fondeoreal.com)".
