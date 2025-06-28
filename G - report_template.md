# Scrabble Game Analysis Report

This report summarizes statistics gathered from the batch processing of .sgs game files.
The program currently has statistics for {num_games_processed} games.
The games are played between two AI opponents who only consider overall equity
(the score of the play + the leave valuation) when choosing a play.




---

# Scoring Statistics

---

## Overall Score Summary

{score_summary_table}

<br>

{margin_of_victory_table}

### Analysis

{score_summary_narrative}

---

## Scoring by Number of Tiles Played

This section analyzes the relationship between the number of tiles played in a single turn and the average score achieved. As expected, playing more tiles generally leads to a higher score, with a significant jump for 7-tile plays (bingos).

{score_by_tiles_played_table}

\FloatBarrier

![Score by Tiles Played Chart]({score_by_tiles_played_chart_path})

\FloatBarrier

---

## P2 Response Score vs. P1 Opening Complexity

This section explores whether the complexity of Player 1's opening move—measured by the number of *unique* tiles played—has an impact on the score of Player 2's first responding move. A "unique" count means that a word like 'APPLE' has 4 unique tiles (A, P, L, E). This analysis only includes games where both players made a scoring move as their first action.

{opening_response_table}

\FloatBarrier

![Opening Response Chart]({opening_response_chart_path})

\FloatBarrier

---

## P2 Response Score vs. P1 Opening with AEINRST

This section provides a different view on opening move complexity. It analyzes if using common, flexible letters (A, E, I, N, R, S, T) in the opening move affects Player 2's response score. The table and chart show P2's average score based on how many *unique* letters from this group were used by P1.

{opening_aeinrst_response_table}

\FloatBarrier

![Opening AEINRST Response Chart]({opening_aeinrst_response_chart_path})

\FloatBarrier

---

## Optimizing the Opening Move

This section moves from observation to strategy by identifying the characteristics of an opening move that empirically lead to the lowest (best) or highest (worst) response score from Player 2. The analysis considers the interplay between the opening move's length, its number of unique tiles, and its count of unique AEINRST tiles. Only combinations that occurred in at least 10 games are included.

### Best Opening Move Characteristics (To Minimize P2's Score)

These are the top 10 types of opening moves that, on average, result in the lowest score for Player 2's first turn.

{best_openers_table}

### Worst Opening Move Characteristics (To Maximize P2's Score)

These are the top 10 types of opening moves that, on average, give Player 2 the best scoring opportunities.

{worst_openers_table}

### Analysis

{opening_optimization_narrative}

---

## The Impact of an Opening Bingo

This section examines how Player 1's win rate is affected by whether their first move is a bingo.

{opening_bingo_win_table}

\FloatBarrier

![Opening Bingo Win Rate Chart]({opening_bingo_win_chart_path})

\FloatBarrier

### Analysis

{opening_bingo_win_narrative}


---




# Let's Get Physical: Scrabble Board Dynamics


Scrabble is played on a physical board,
but does the physical makeup of the board confer any tactical advantage to either player? Let's take a look.


\FloatBarrier


## Quadrant Usage Analysis

The following table and chart show the distribution of play across the four board quadrants.
The counting method is inclusive, meaning tiles played on the center row/column are
counted in both adjacent quadrants.

### Average Quadrant Usage Table

{quadrant_table}

\FloatBarrier

### Average Quadrant Usage Chart

\FloatBarrier

![Quadrant Usage Chart]({quadrant_chart_path})

\FloatBarrier

---

### Min/Max and Distribution of Quadrant Usage{quadrant_extremes_footnote_ref}

The following table shows the absolute minimum and maximum percentage of tiles played in each quadrant across all games, highlighting the full range of possibilities. The source games for each of these extreme values are listed in the Notes section at the end of this report.

{quadrant_extremes_table}

\FloatBarrier

The box plot below provides a more detailed statistical view. The box represents the central 50% of games (the interquartile range), the line inside the box is the median usage, and the whiskers extend to show the full range from minimum to maximum. This visualization helps in understanding not just the extremes, but also the consistency of usage for each quadrant.

![Quadrant Distribution Chart]({quadrant_distribution_chart_path})

\FloatBarrier

---

### Min/Max Usage of Board Halves{board_halves_extremes_footnote_ref}

Similarly, this table shows the extreme usage values for the top, bottom, left, and right halves of the board. The counting method is inclusive, so tiles on the center row/column are counted in both adjacent halves. The source games for each value are listed in the Notes section.

{board_halves_extremes_table}

\FloatBarrier

---

## Score by Dominant Quadrant

This section investigates whether focusing play in a specific quadrant correlates with higher scores.
For each game, the quadrant with the most tiles played is identified as the "dominant" quadrant.
The table and chart below show the average scores for all games, grouped by their dominant quadrant.

### Average Scores Table

{dominant_quad_table}

\FloatBarrier

### Average Scores Chart

![Dominant Quadrant Scores Chart]({dominant_quad_chart_path})

\FloatBarrier

---

## Quadrant Usage by Opening Orientation

This table shows the average quadrant usage for games based on whether the opening move was played horizontally or vertically.

{opening_orientation_table}

\FloatBarrier

---


## Quadrant Control Strategy Analysis

This section analyzes whether concentrating play in one or two quadrants is a better strategy
than spreading play evenly across the board.
We use the Herfindahl-Hirschman Index (HHI) as a measure of concentration, where a higher score means play was more focused.

### Win Rate by Strategy

The table below groups games into three strategic categories based on their concentration score and
shows the win percentage for Player 1 in each.

{quad_control_table}

### Concentration vs. Score Differential

The scatter plot below visualizes the relationship between the concentration score (HHI) of each game
and the final score differential.

![Quadrant Control Chart]({quad_control_chart_path})

\FloatBarrier

---

## "Comeback" Quadrant Analysis

This section analyzes strategic choices made when a player is trailing by 40 or more points.
It compares the final win rate of moves that open a new, previously untouched quadrant (exclusive of Row 8 and Column H)
versus moves that are played within already active quadrants.

{comeback_table}

\FloatBarrier

---

## Square Usage Heatmap

The following heatmap shows the percentage of games in which a tile was placed on each specific square.
A higher percentage indicates more frequent usage.

![Square Usage Heatmap]({heatmap_path})

{final_footnotes}
