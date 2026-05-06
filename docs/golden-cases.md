# Golden Cases

The golden files are not a benchmark. They are a stable review surface for databases.

The main golden fixture is `fixtures/golden/scoreboard.csv`. The matrix fixture is `fixtures/golden/lane-matrix.csv`. Together they cover `index fit`, `join width`, `constraint risk`, and `plan drift` with different score ranges.

The purpose is to make intentional rule changes show up in review.
