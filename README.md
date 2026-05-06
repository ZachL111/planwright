# planwright

`planwright` explores databases with a small SQL codebase and local fixtures. The technical goal is to validate indexing choices with sqlite3 fixtures and plan expectations.

## Why It Exists

I want this repository to be useful as a quick reading exercise: fixtures first, implementation second, verifier last.

## Planwright Review Notes

`stale` and `recovery` are the cases worth reading first. They show the optimistic and cautious ends of the fixture.

## Features

- `fixtures/domain_review.csv` adds cases for index fit and join width.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/planwright-walkthrough.md` walks through the case spread.
- The SQL code includes a review path for `index fit` and `plan drift`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Architecture Notes

The implementation keeps the scoring rule plain: reward signal and confidence, preserve slack, penalize drag, then classify the result into a review lane.

The SQL checks add a separate view over the domain review fixture.

## Usage

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Tests

That command is also the regression path. It verifies the domain cases and catches mismatches between the CSV, metadata, and code.

## Limitations And Roadmap

The fixture set is small enough to audit by hand. The next useful expansion is malformed input coverage, not extra surface area.
