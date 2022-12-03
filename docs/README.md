# Regionalized resources for the Spanish-language


## Lexical and semantic comparative between regions
Affinity matrices of the Spanish language regional vocabularies using lexical (left) and semantic models (right.)
<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-lexical-affinity-matrix.png" width="100%" alt="lexical" />
Lexical affinity matrix uses raw vocabularies as bag of words under the cosine distance (weights are empirical probability of the token occurring in each country in our Twitter corpus.)

You can see more details in this <a href="https://github.com/sadit/RegionalSpanish/blob/main/notebooks/visualize-common-voc-lexical.ipynb">notebook</a>.
</div>
<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-common-words-semantic-affinity-matrix.png" width="100%" alt="semantic" />
Semantic comparison. It represents each region as the  <a href="https://en.wikipedia.org/wiki/Nearest_neighbor_graph">all-knn graph</a> using each regional word embeddings as input for the knn. We used k=33. The procedure is detailed <a href="https://github.com/sadit/RegionalSpanish/blob/main/src/umap-embeddings-with-common-voc.jl">here</a> and <a href="https://github.com/INGEOTEC/regional-spanish-models/blob/main/notebooks/visualize-common-voc-semantic.ipynb">this notebook</a>.
</div>

### Visualization of these affinity matrices
2D UMAP projections (colors are computed using a 3D projections). For these visualizations are based on $k$ nearest neighbor graphs ($k=3$) which capture local features of the affinity matrix.

<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-lexical-umap-4.png" width="100%" alt="lexical 2d projection" />
From lexical affinity matrix. Take a look on this <a href="https://github.com/INGEOTEC/regional-spanish-models/blob/main/notebooks/visualize-voc-lexical.ipynb">notebook</a> for more details and different $knn$ graphs.
</div>
<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-voc-semantic-umap-4.png" width="100%" alt="semantic 2d projection" />
From semantic-based affinity matrix. Take a look on this <a href="https://github.com/INGEOTEC/regional-spanish-models/blob/main/notebooks/https://github.com/INGEOTEC/regional-spanish-models/blob/main/notebooks/visualize-common-voc-semantic.ipynb">notebook</a> for more details and for more details and different $knn$ graphs.
</div>

### Geographic view
<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-colormap-lexical-4.png" width="100%" alt="lexical 2d projection" />
Countries' vocabulary. 
</div>
<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-colormap-common-voc-semantic-4.png" width="100%" alt="semantic 2d projection" />
</div>

Vocabulary and geographical similarity visualization, i.e., similar colors imply similarity (computed from 3D UMAP projetions). 
This [notebook](https://github.com/INGEOTEC/regional-spanish-models/blob/main/notebooks/map_RGB.ipynb) shows more maps for different configurations of UMAP.

## Regional word embeddings (semantic) and vocabularies (lexical)

Regional word embeddings for variations of the Spanish language. For the following UMAP 2D projections we selected a subset of more than 100K tokens that appear in at least five regions (see this [notebook](https://github.com/sadit/RegionalSpanish/blob/main/notebooks/common-vocabulary.ipynb) for more details.)

<div style="display: inline-block; width: 32%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-umap-common-voc-1.7m.k%3D33.png" width="100%" alt="lexical" />
All regions combined - Spanish language.
</div>
<div style="display: inline-block; width: 32%;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-umap-common-voc-tokens.cc%3DAR.k%3D33.png" width="100%" alt="lexical" />
Argentinean variation of the Spanish language
</div>
<div style="display: inline-block; width: 32%; vertical-align: top;">
<img src="https://github.com/INGEOTEC/regional-spanish-models/raw/main/figs/fig-umap-common-voc-tokens.cc%3DMX.k%3D33.png" width="100%" alt="lexical" />
Mexican variation of the Spanish language
</div>

Colors are also 3D UMAP projections; therefore, color clusters are also meaningful. Please note that UMAP projections are pretty stable regarding local shapes, but they can vary from a global perspective. The different forms indicate that other regions have different definitions of common tokens. Therefore, tasks that strongly influence regional meanings may take advantage of regional resources.

Look at this [notebook](https://github.com/sadit/regional-spanish-models/blob/main/notebooks/explore-region-similarities.ipynb) to see some vertices of the graph used to generate the visualizations. Each word is a vertex of the graph that is also connected with other words. Note that definitions vary from region to region. For instance, see the description of _iglesia_ (church), which US Spanish speakers define as Evangeliques and other regions Catholics. Another example comes from the _america_ token, which refers to geographic terms in almost any region and football soccer teams for the MX region.

You can find projections for all Spanish-speaking countries in this [notebook](https://github.com/INGEOTEC/regional-spanish-models/blob/main/notebooks/visualize-voc-semantic-cloud.ipynb).


# Resources
We extracted vocabularies and created BERT language models and word-embedding models with [fastText](https://fasttext.cc/) for 26 countries having the Spanish language as one of their official or _de facto_ languages. We segmented our collection per country such that models could learn regionalisms.
We created nine language models, called BILMA, for eight countries having enough data in our corpus to learn them. The ninth is a larger model using data from all 26 countries. Our BILMA models use the Keras framework; please visit the [BILMA repository](https://github.com/msubrayada/bilma) for more details and usage tutorials. In the case of fastText word embeddings, we learned four different dimensionalities per region using default hyper-parameters. We provide two kinds of models, `bin` and `vec`; the prior is a binary model, and the second is an ASCII version of the same model. The ASCII version can be parsed and used without fastText and also used by the same fastText to create supervised (classification) models with pretrained word embeddings.

| country            | code   | sample | voc | BILMA | FT 300d | FT 32d | FT 16d  | FT 8d |
|:----------         | ------ | ------ | --- | ----- | ----:| ----:| ----:| ----:|
| Argentina  | AR | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-AR.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/AR.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_AR_epoch-1.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-8d.vec) |
| Bolivia  | BO | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-BO.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/BO.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-8d.vec) |
| Brazil  | BR | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-BR.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/BR.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-8d.vec) |
| Canadá  | CA | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-CA.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/CA.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-8d.vec) |
| Chile  | CL | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-CL.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/CL.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_CL_epoch-3.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-8d.vec) |
| Colombia  | CO | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-CO.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/CO.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_CO_epoch-1.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-8d.vec) |
| Costa Rica  | CR | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-CR.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/CR.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-8d.vec) |
| Cuba  | CU | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-CU.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/CU.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-8d.vec) |
| República Dominicana  | DO | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-DO.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/DO.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-8d.vec) |
| Ecuador  | EC | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-EC.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/EC.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-8d.vec) |
| España  | ES | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-ES.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/ES.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_ES_epoch-1.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-8d.vec) |
| Francia  | FR | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-FR.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/FR.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-8d.vec) |
| Great Britain  | GB | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-GB.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/GB.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-8d.vec) |
| Guinea Equatorial  | GQ | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-GQ.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/GQ.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-8d.vec) |
| Guatemala  | GT | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-GT.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/GT.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-8d.vec) |
| Honduras  | HN | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-HN.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/HN.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-8d.vec) |
| México  | MX | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-MX.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/MX.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_MX_epoch-1.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-8d.vec) |
| Nicaragua  | NI | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-NI.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/NI.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-8d.vec) |
| Panamá  | PA | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-PA.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/PA.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-8d.vec) |
| Perú  | PE | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-PE.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/PE.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-8d.vec) |
| Puerto Rico  | PR | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-PR.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/PR.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-8d.vec) |
| Paraguay  | PY | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-PY.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/PY.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-8d.vec) |
| El Salvador  | SV | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-SV.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/SV.tsv.gz) | - | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-8d.vec) |
| United States of America  | US | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-US.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/US.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_US_epoch-3.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-8d.vec) |
| Uruguay  | UY | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-UY.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/UY.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_UY_epoch-3.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-8d.vec) |
| Venezuela  | VE | [id](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/messages/sample/sample-id-VE.tsv.gz) | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/VE.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_VE_epoch-3.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-8d.vec) |
| ALL  | ALL | - | [voc](https://github.com/INGEOTEC/regional-spanish-models/raw/main/data/SpanishLang/voc/ALL.tsv.gz) | [model](http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/bilma_small_ALL_epoch-1.h5) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-32d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-16d.vec) | [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-8d.vec) |



Our _ALL_ model is learned from the entire corpora. 


**Note 1:** All BILMA models use a common <a href="http://geo.ingeotec.mx/~lgruiz/regional-models-bilma/vocab_file_All.txt">vocabulary file</a>. 

**Note 2:** You may need to use _save as_ link instead of just click for downloading models.

## Corpora

We collected Spanish tweets from 2016 to 2019 using the Twitter API (public stream) to create our manuscript and our resources. The final corpora is described below:

| country            | code   | number of users | number of tweets | number of tokens |
|:----------         | ------ |          ------:|          -------:|        ---------:|
| Argentina          | AR | 1,376K | 234.22M | 2,887.92M |
| Bolivia            | BO | 36K    |  1.15M  |    20.99M |
| Chile              | CL | 415K   | 45.29M  |   719.24M |
| Colombia           | CO | 701K   | 61.54M  |   918.51M |
| Costa Rica         | CR | 79K    |  7.51M  |   101.67M |
| Cuba               | CU | 32K    |  0.37M  |     6.30M |
| Dominican Republic | DO | 112K   |  7.65M  |   122.06M |
| Ecuador            | EC | 207K   | 13.76M  |   226.03M |
| El Salvador        | SV | 49K    | 2.71M   |    44.46M |
| Equatorial Guinea  | GQ | 1K     | 8.93K   |     0.14M |
| Guatemala          | GT | 74K    | 5.22M   |    75.79M |
| Honduras           | HN | 35K    | 2.14M   |    31.26M |
| Mexico             | MX | 1,517K | 115.53M | 1,635.69M |
| Nicaragua          | NI | 35K    | 3.34M   |    42.47M |
| Panama             | PA | 83K    | 6.62M   |    108.74M|
| Paraguay           | PY | 106K   |  10.28M |   141.75M |
| Peru               | PE | 271K   | 15.38M  |   241.60M |
| Puerto Rico        | PR | 18K    | 0.58M   |     7.64M |
| Spain              | ES | 1,278K | 121.42M | 1,908.07M |
| Uruguay            | UY | 157K   | 30.83M  |   351.81M |
| Venezuela          | VE | 421K   | 35.48M  |   556.12M |
  | | | | |
 Brazil                   | BR | 1,604K |  27.20M |  142.22M |
 Canada                   | CA | 149K   |  1.55M  |  21.58M  |
 France                   | FR | 292K   |  2.43M  |  27.73M  |
 Great Britain            | GB | 380K   |  2.68M  |  34.62M  |
 United States of America | US | 2,652K | 40.83M  | 501.86M  |
 Total                    |    | 12M   |   795.74M |   10,876.25M |

## Preprocessing

We preprocessed messages as follows:

- lower casing
- diacritic marks removed
- grouped hashtags, users and numbers
- normalize symbol repetitions (max. 2 repeats)
- laughs were normalized to four letters
- words, punctuactions, and emojis are used as tokens

We only consider Twitter as data source; messages with URLs were discarded, retweets and _fourth square_ and other automatic messages were removed. Short messages were also discarded. Please check our manuscript for more details [https://arxiv.org/abs/2110.06128](https://arxiv.org/abs/2110.06128) or contact us.

# More resources
<div>
Clone our <a href="https://github.com/INGEOTEC/regional-spanish-models">github repository</a>
where you can find more metadata, resources, and code: regional vocabulary, regional embeddings, knn graphs of concepts (tokens), token comparison among regions, among others.
</div>

# Citing

If you find these resources useful, please give us a star in the github repository.
Also, if you use them for research purposes, please consider to cite us:

_Regionalized models for Spanish language variations based on Twitter._ Eric S. Tellez, Daniela Moctezuma, Sabino Miranda, Mario Graff, and Guillermo Ruiz. [https://arxiv.org/abs/2110.06128](https://arxiv.org/abs/2110.06128).

```
@misc{tellez2022regionalized,
      title={Regionalized models for Spanish language variations based on Twitter}, 
      author={Eric S. Tellez and Daniela Moctezuma and Sabino Miranda and Mario Graff and Guillermo Ruiz},
      year={2022},
      eprint={2110.06128},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

# Contact us

If you want to know more about these resources, or you need something not shared in this repo/site, please contact us.

- Eric S. Tellez - `eric.tellez@infotec.mx`
- Daniela Moctezuma
- Sabino Miranda
- Mario Graff
- Guillermo Ruiz
