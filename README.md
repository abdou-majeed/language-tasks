# Language Identification and Classification Using Compression-Based Distances

**Author:** Abdou
**Based on:** MSc Thesis — *Relative Entropy, Data Compression, and Applications*

This notebook implements compression-based methods for:
1. **Entropy estimation** — estimating the per-character entropy of natural language texts using gzip compression.
2. **Language identification** — recognizing which language a short text snippet belongs to, by using compression to provide a measure of distance to known training corpora.
3. **Language classification** — grouping languages into families using pairwise 'distances' and community detection on graphs.

The key insight (Benedetto et al., 2002) is that the relative entropy between two texts can be approximated by measuring how much better an optimal compressor can compress a snippet when it has access to a reference text in the same language, compared to when it has access to a reference text in a different language.

By optimal compressor, we mean a compressor that compresses a text down to its entropy asymptotically. We use gzip which implements LZ77 + Huffman because LZ77 is known to achieve this lower bound asymptotically.

## Datasets

- **Dataset A (UDHR):** The Universal Declaration of Human Rights translated into 281 languages, from [Aalto University](http://research.ics.aalto.fi/cog/data/udhr/).
- **Dataset B (Kaggle):** A collection of ~10,000 text samples in total, in 17 languages, from [Kaggle](https://www.kaggle.com/datasets/basilb2s/language-detection).
- **Dataset C (Lolita):** The opening paragraph of *Lolita* by Vladimir Nabokov, translated into 17 languages.

## References

<!-- - Benedetto, D., Caglioti, E., & Loreto, V. (2002). Language Trees and Zipping. Physical Review Letters, 88(4). https://doi.org/10.1103/physrevlett.88.048702
- Huffman, D. (1952). A Method for the Construction of Minimum-Redundancy Codes. Proceedings Of The IRE, 40(9), 1098‑1101. https://doi.org/10.1109/jrproc.1952.273898
- Vatanen, T., Väyrynen, J., & Virpioja, S. (2010, 1 mai). Language Identification of Short Text Segments with N-gram Models. ACL Anthology. https://aclanthology.org/L10-1193/
- Ziv, J., & Lempel, A. (1977). A universal algorithm for sequential data compression. IEEE Transactions On Information Theory, 23(3), 337‑343. https://doi.org/10.1109/tit.1977.1055714
 -->
- Benedetto, D., Caglioti, E. and Loreto, V. (2002) ‘Language trees and zipping’, Physical Review Letters, 88(4). doi:[10.1103/physrevlett.88.048702](https://doi.org/10.1103/PhysRevLett.88.048702).
- [Language Identification of Short Text Segments with N-gram Models](https://aclanthology.org/L10-1193/) (Vatanen et al., LREC 2010).
- [About the Universal Declaration of Human Rights Translation Project](https://www.ohchr.org/en/human-rights/universal-declaration/universal-declaration-human-rights/about-universal-declaration-human-rights-translation-project). (s. d.). The Office Of The High Commission For Human Rights (OHCHR).
<!-- - [The Office of the High Commission for Human Rights (OHCHR)](https://www.ohchr.org/en/human-rights/universal-declaration/universal-declaration-human-rights/about-universal-declaration-human-rights-translation-project). -->
- J. Ziv and A. Lempel, "A universal algorithm for sequential data compression," in IEEE Transactions on Information Theory, vol. 23, no. 3, pp. 337-343, May 1977, doi: [10.1109/TIT.1977.1055714](https://doi.org/10.1109/TIT.1977.1055714).
keywords: {Encoding;Symbols;Silicon;Codes;Decoding;Data compression;Compression algorithms;Lower bound;Feeds;Upper bound},
- D. A. Huffman, "A Method for the Construction of Minimum-Redundancy Codes," in Proceedings of the IRE, vol. 40, no. 9, pp. 1098-1101, Sept. 1952, doi: [10.1109/JRPROC.1952.273898](https://doi.org/10.1109/JRPROC.1952.273898).
keywords: {Transmitters},
