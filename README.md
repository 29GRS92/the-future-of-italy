# The Future of Italy · Primavera 1 2025/26

**Last season, he was playing in Primavera. Today, he scores in Serie A. Could data have spotted him a year earlier?**

This project ranks every young Italian player of the Primavera 1 2025/26 season, position by position, using statistics only.


## Scope

| | |
|---|---|
| Competition | Campionato Primavera 1, 2025/26 season |
| Players | Italian players born between 2006 and 2009 |
| Minimum playing time | 810 minutes (9 full matches) |
| Players ranked | 248 (24 goalkeepers, 69 defenders, 117 midfielders, 38 forwards) |
| Data source | SofaScore |

## Method

1. **Data collection.** Every Primavera 1 player and their season statistics are collected from SofaScore (Python, `curl_cffi`).
2. **Per 90 indicators.** Counting statistics are converted to per 90 minutes so that players with different playing time can be compared.
3. **Score out of 100.** For each indicator, a player gets a percentile score (0 to 100) against the other young Italians at his position. The final score is a weighted average of these scores.
4. **Age bonus.** +3 points for players born in 2008, +5 for players born in 2009.
5. **Benchmarks.** Every player is compared with two averages: young Italians, and the whole Primavera 1 (all players with 810+ minutes).

The SofaScore rating is not used: every point of the score comes from a measurable statistic.

### Weights by position

| Position | Indicators |
|---|---|
| Goalkeepers | Save % 45 · Playing time 15 · Long ball accuracy 10 · Crosses not claimed 10 · Errors leading to a shot 10 · Goals conceded 10 |
| Defenders | Defending 55 (duels, aerial duels, recoveries, clearances and blocks, dribbled past, errors) · Build-up 30 (pass accuracy, final third passes, long balls) · Playing time 15 |
| Midfielders | Passing 31 · Creativity 31 (key passes, goals and assists, dribbles) · Ball winning 23 · Playing time 15 |
| Forwards | Finishing 50 (non-penalty goals, shots on target, conversion) · Playing time 15 · Creativity 15 · Dribbling 12 · Duels 8 |

## Results

| Position | #1 | #2 | #3 |
|---|---|---|---|
| Goalkeepers | Niccolo Fontana (Cesena, 2007) 81.0 | Andrea Vailati (Monza, 2007) 80.4 | Alessandro Anelli (Atalanta, 2008) 77.4 |
| Defenders | Leonardo Bovio (Inter, 2008) 83.3 | Edoardo Sadotti (Fiorentina, 2006) 78.6 | Dario Pelosi (Frosinone, 2006) 77.3 |
| Midfielders | Filippo Cerpelletti (Inter, 2007) 77.7 | Marco Buonaiuto (Monza, 2007) 75.9 | Filippo Bertaccini (Cesena, 2007) 75.8 |
| Forwards | Simone Lontani (Milan, 2008) 83.8 | Nicolò Baldo (Atalanta, 2006) 81.9 | Riccardo Braschi (Fiorentina, 2006) 77.1 |

Full rankings: [`rankings_primavera1_2025_26.csv`](rankings_primavera1_2025_26.csv)

| Goalkeeper #1 | Defender #1 |
|---|---|
| ![](figures/radar_goalkeeper.png) | ![](figures/radar_defender.png) |
| **Midfielder #1** | **Forward #1** |
| ![](figures/radar_midfielder.png) | ![](figures/radar_forward.png) |

## What happened next

| Player | Ranking | Club in 2026/27 |
|---|---|---|
| Simone Lontani | #1 forward | Parma (Serie A), first Serie A goal against Monza |
| Riccardo Braschi | #3 forward | FC Thun (Switzerland) |
| Edoardo Sadotti | #2 defender | Alcione Milano |

## Comparison with the official Team of the Season

5 of the 8 players of the official Team of the Season (Primavera Best Awards 2025/26, Sportitalia) who are in this dataset rank in the top 16% at their position: Anelli (#3 of 24), Galvagno (#4 of 38), Lo Monaco (#6 of 38), Pandolfi (#7 of 117), Montenegro (#12 of 117). The Revelation of the Season, Antonio Arena (Roma, born 2009), is #7 of 38 forwards.

## Repository

| File | Content |
|---|---|
| `futur_de_l_italie_primavera_2526.ipynb` | Full notebook: data collection, indicators, rankings, radars, Best XI (commented in French) |
| `rankings_primavera1_2025_26.csv` | Final rankings for the four positions |
| `figures/` | Radars, Best XI and the LinkedIn carousel |

## Author

**Theo Grasso**, Football Data Analyst. Available from January 2027, open to relocating.
LinkedIn: [linkedin.com/in/theo-grasso](https://www.linkedin.com/in/theo-grasso) · GitHub: [29GRS92](https://github.com/29GRS92)

*Personal, non-commercial project. Data from SofaScore.*
