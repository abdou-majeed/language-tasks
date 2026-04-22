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
- Benedetto, D., Caglioti, E. and Loreto, V. (2002) ‘Language trees and zipping’, Physical Review Letters, 88(4). [doi:10.1103/physrevlett.88.048702](https://doi.org/10.1103/PhysRevLett.88.048702).
- [Language Identification of Short Text Segments with N-gram Models](https://aclanthology.org/L10-1193/) (Vatanen et al., LREC 2010).
- [The Office of the High Commission for Human Rights (OHCHR)](https://www.ohchr.org/en/human-rights/universal-declaration/universal-declaration-human-rights/about-universal-declaration-human-rights-translation-project).
