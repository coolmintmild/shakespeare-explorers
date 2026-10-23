# Shakespeare Sentiment and Character Network Explorers

Two web-based tools for exploring all 37 of Shakespeare's plays, built through AI-assisted "vibe coding" without the researcher writing code.

- **Shakespeare Sentiment Explorer**: https://coolmintmild.github.io/shakespeare-explorers/sentiment/
- **Shakespeare Character Networks Explorer**: https://coolmintmild.github.io/shakespeare-explorers/network/

Both tools are static web pages (HTML, CSS, and JavaScript) that read precomputed data files. They need no server or database.

## Repository contents

```text
index.html     Landing page linking to both tools
sentiment/     Shakespeare Sentiment Explorer (site files and data)
network/       Shakespeare Character Networks Explorer (site files and data)
LICENSE        License for the code (MIT)
LICENSE-DATA.md  License and attribution for the data (CC BY-NC 4.0)
```

## Shakespeare Sentiment Explorer

Draws and compares the emotional arcs of the plays.

- **Views:** Multiple (four plays side by side), Overlay (many plays on a normalized 0 to 100% timeline with their average), and Single (one play in detail, with scene, act-by-scene heatmap, and speaker charts).
- **Settings:** text unit (sentence, line or speech, scene), sentiment model (VADER, a deep-learning model, or both), smoothing (LOWESS, moving average, or raw) with an adjustable window, and inclusion of stage directions.
- **Downloads:** filtered rows, play-level and scene-level CSV files, a summary of all plays, and PNG images of the charts.
- A quick guide is available on the site.

### Data

`sentiment/data/` holds one JSON file per play and the downloadable CSV files.

| Field in the CSV files | Meaning |
|---|---|
| `original_text` | Original Shakespeare text of the unit |
| `vader_score` | VADER compound score (Hutto & Gilbert, 2014), from -1 to +1 |
| `dl_score` | Score from the deep-learning model SiEBERT (Hartmann et al., 2023), from -1 to +1. Shown on the site as "DL (siebert)" |
| `dl2_score` | Score from `tabularisai/multilingual-sentiment-analysis`, the model used at first and later replaced. Not shown on the site |

The text shown and distributed here is the original text only. Sentiment scores were computed on a modern English translation aligned with the original unit by unit (LitCharts Shakescleare). Because of copyright, the translation was used only for internal computation and is **not** included in this repository.

## Shakespeare Character Networks Explorer

Shows how character networks change across scenes and acts.

- **Networks:** stage network (characters who appear in the same scene) and speech network (characters who both speak in the same scene).
- **Time modes:** full play, act by act, scene by scene, cumulative by act or scene, and sliding windows of three or five scenes, with a timeline player. Node positions are fixed so that the graph does not jump as the timeline moves.
- **Measures:** degree, weighted degree, betweenness, closeness, eigenvector, and PageRank centrality; Louvain and Leiden communities; modularity and density.
- **Other functions:** character focus with new and lost ties, a Compare view for four plays, filters, and JSON, CSV, and PNG export.
- A guide is available on the site.

### Data

`network/data/` holds precomputed networks, layouts, metrics, and ego networks for each play. They were derived from ShakeDraCor, the Shakespeare corpus of the Drama Corpora Project (https://dracor.org/shake), which is based on the Folger Shakespeare texts (CC BY-NC 3.0).

## Running the tools locally

Download or clone this repository, then start a local web server in its root folder:

```bash
python3 -m http.server 8000
```

Open http://localhost:8000/sentiment/ or http://localhost:8000/network/ in a browser.

## How the tools were built

All code and data files were produced by an AI coding agent (OpenAI Codex with GPT-5.5) through conversation. The researcher described the tools, reviewed and corrected the agent's plans and outputs, and did not write code. The development process is described in the accompanying paper.

## License

- **Code** (HTML, CSS, and JavaScript files): MIT License. See `LICENSE`.
- **Data** (files in `sentiment/data/` and `network/data/`): CC BY-NC 4.0. See `LICENSE-DATA.md` for attribution of the underlying sources.
- Shakespeare's original texts are in the public domain.

## Citation

If you use these tools or data, please cite the accompanying paper:

> Lee, J. (forthcoming). Vibe coding for digital humanities: Building Shakespeare sentiment and character network analysis tools without writing code.
