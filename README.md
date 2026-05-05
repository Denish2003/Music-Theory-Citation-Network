# Thematic Communities in a Music Theory Citation Network
## Author: Denish Patel and Liuyang (Zack) Xu

This repository contains the analysis notebook for a COS 520 final project on thematic community structure in the `Music Theory Online` corpus. The project treats music-theory scholarship as a citation and bibliographic-coupling network, then compares graph-learning methods for identifying interpretable scholarly communities.

## Project Overview
The analysis starts from scraped JSON records for `Music Theory Online` articles. Each record contains paper metadata, article text, keywords, author information, and bibliography entries. The notebook builds two graph representations:
- **Directed paper-citation graph:** nodes are corpus papers; directed edges represent matched intra-corpus citations.
- **Undirected bibliographic-coupling graph:** nodes are corpus papers; weighted edges connect papers that share cited references.

The main implemented community-detection methods are:
- **Stochastic Block Model (SBM)**
- **Spectral embedding + KMeans**
- **InfoMap**
- **Greedy Modularity**

```

## Data
The notebook expects a `data/` directory containing one JSON file per paper.
In the original environment, the notebook located this directory in Google Drive:

```text
/content/drive/MyDrive/data
```

For local reproduction, place the JSON files in:
```text
./data/
```

or update the `project_root_candidates` list near the top of `COS_520_Final_Project.ipynb`.

## Python Dependencies
The notebook uses Python 3 and the following main packages:
```text
numpy
pandas
networkx
matplotlib
seaborn
scipy
scikit-learn
```

If using `pip`, a minimal setup is:
```bash
pip install numpy pandas networkx matplotlib seaborn scipy scikit-learn
```

## Running the Analysis
1. Ensure the scraped JSON files are available in `data/`.
2. Open `COS_520_Final_Project.ipynb`.
3. Set `IN_COLAB` appropriately:
   - `True` if running in Google Colab with Drive mounted.
   - `False` or adjusted setup logic if running locally.
4. Run the notebook from top to bottom.

The notebook performs:
- Data loading and cleaning
- Paper/citation table construction
- Internal citation matching by DOI, URL, and title
- Citation graph construction
- Bibliographic-coupling graph construction
- Exploratory data analysis
- SBM model selection and interpretation
- Spectral embedding, eigengap selection, and KMeans clustering
- InfoMap + convergence
- Greedy Modularity
