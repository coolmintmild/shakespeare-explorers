# Data License

The data files in `sentiment/data/` and `network/data/` are licensed under the
**Creative Commons Attribution-NonCommercial 4.0 International License
(CC BY-NC 4.0)**: https://creativecommons.org/licenses/by-nc/4.0/

You may share and adapt the data for non-commercial purposes, provided that you
give appropriate credit (see the citation in `README.md`; author: Jonghyun Lee) and indicate whether
changes were made.

## Sources and attribution

- **Sentiment data.** The text included is Shakespeare's original text, which
  is in the public domain. Sentiment scores were computed on a modern English
  translation (LitCharts Shakescleare), which was used only for internal
  computation and is not included in this repository. Scores were produced
  with VADER (Hutto & Gilbert, 2014) and SiEBERT (Hartmann et al., 2023);
  `dl2_score` comes from `tabularisai/multilingual-sentiment-analysis`.
- **Network data.** Derived from ShakeDraCor, the Shakespeare corpus of the
  Drama Corpora Project (https://dracor.org/shake; Fischer et al., 2019),
  which is based on the Folger Shakespeare texts from the Folger Shakespeare
  Library, released under CC BY-NC 3.0
  (https://creativecommons.org/licenses/by-nc/3.0/). The non-commercial
  condition of that license also applies to the derived network data here.

## References

- Fischer, F., Börner, I., Göbel, M., Hechtl, A., Kittel, C., Milling, C., &
  Trilcke, P. (2019). Programmable corpora: Introducing DraCor, an
  infrastructure for the research on European drama. Digital Humanities 2019,
  Utrecht. https://doi.org/10.5281/zenodo.4284002
- Hartmann, J., Heitmann, M., Siebert, C., & Schamp, C. (2023). More than a
  feeling: Accuracy and application of sentiment analysis. International
  Journal of Research in Marketing, 40(1), 75-87.
- Hutto, C. J., & Gilbert, E. (2014). VADER: A parsimonious rule-based model
  for sentiment analysis of social media text. Proceedings of the
  International AAAI Conference on Web and Social Media, 8(1), 216-225.
