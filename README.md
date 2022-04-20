
# Regionalized resources for the Spanish-language

This site shares the regionalized resources presented in the following manuscript:

_A large scale lexical and semantic analysis of Spanish language variations in Twitter._ Eric S. Tellez, Daniela Moctezuma, Sabino Miranda, Mario Graff, and Guillermo Ruiz, https://arxiv.org/abs/2110.06128.

```
@misc{tellez2021large,
      title={A large scale lexical and semantic analysis of Spanish language variations in Twitter}, 
      author={Eric S. Tellez and Daniela Moctezuma and Sabino Miranda and Mario Graff},
      year={2021},
      eprint={2110.06128},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

As part of the INGEOTEC research group from INFOTEC and CentroGEO.

Here you will find regionalized word embeddings and language models resources for Spanish countries, created with Twitter messages from the public stream. Our aim is to provide these resources and tools that help on developing more sophisticated applications and models that can tackle complex NLP tasks that can take advantage of Spanish variants. More is available in the regional models [talk](https://sadit.github.io/regional-spanish-models-talk-2022/) (in Spanish).

If you are visualizing this site from Github repo, perhaps you like more the Github pages site:

- [https://ingeotec.github.io/regional-spanish-models/](https://ingeotec.github.io/regional-spanish-models/)

## Useful short cuts in this site:
- [Regional language models](#regional-language-models)
- [Regional word embeddings](#regional-semantic-models)
- [Corpora sample](#corpora-identifiers)
- [Information about the corpora](#corpora)

# Regional language models
We created eight BERT-based language models, called BILMA (BERT in Latin America). Each model consists on 4 attention heads and outputs 512-dimensional vectors. Each model was created using geotagged Twitter messages from the stream API.

BILMA models require Python 3 and Tensorflow 2.4. It consists of two main pieces, the BILMA Python package and the actual models

- [https://github.com/msubrayada/bilma](https://github.com/msubrayada/bilma)

In this repository you will find the package backend to use the models and some tutorials and examples, for instance:

- <a href="https://github.com/msubrayada/bilma/blob/main/bilma-cls-demo.ipynb">classification example</a>
- <a href="https://github.com/msubrayada/bilma/blob/main/bilma-demo.ipynb">text mining by masking</a>

### Models:
- AR: <a href="bilma_small_AR_epoch-1.h5">model trained on MLM</a> or
      <a href="bilma_small_AR_epoch-1_classification_epochs-17.h5">model trained for predict emoticon.</a>
- CL: <a href="bilma_small_CL_epoch-3.h5">model trained on MLM</a> or
      <a href="bilma_small_CL_epoch-3_classification_epochs-9.h5">model trained for predict emoticon.</a>
- CO: <a href="bilma_small_CO_epoch-1.h5">model trained on MLM</a> or
      <a href="bilma_small_CO_epoch-1_classification_epochs-11.h5">model trained for predict emoticon.</a>
- ES: <a href="bilma_small_ES_epoch-1.h5">model trained on MLM</a> or
      <a href="bilma_small_ES_epoch-1_classification_epochs-9.h5">model trained for predict emoticon.</a>
- MX: <a href="bilma_small_MX_epoch-1.h5">model trained on MLM</a> or
      <a href="bilma_small_MX_epoch-1_classification_epochs-13.h5">model trained for predict emoticon.</a>
- US: <a href="bilma_small_US_epoch-3.h5">model trained on MLM</a> or
      <a href="bilma_small_US_epoch-3_classification_epochs-11.h5">model trained for predict emoticon.</a>
- UY: <a href="bilma_small_UY_epoch-3.h5">model trained on MLM</a> or
      <a href="bilma_small_UY_epoch-3_classification_epochs-13.h5">model trained for predict emoticon.</a>
- VE: <a href="bilma_small_VE_epoch-3.h5">model trained on MLM</a> or
      <a href="bilma_small_VE_epoch-3_classification_epochs-12.h5">model trained for predict emoticon.</a>

Get vocabulary from the following link:  <a href="vocab_file_All.txt">vocabulary file</a>; it is common to all models


# Regional semantic models
We created 26 word-embedding models with [fastText](https://fasttext.cc/), one per country. We learned 300 dimension vectors and use default hyper-parameters. We provide two kinds of models, `bin` which correspond to binary version of the model and `vec` which is the ascii version of the same model; ascii version can be parsed and used without fastText and also are used by the same fastText to create supervised (clasification) models with pretrained word embeddings.

- Argentina (AR) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR.vec)
- Bolivia (BO) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO.vec)  
- Brazil (BR) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR.vec)      
- Canadá (CA) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA.vec)                 
- Chile (CL) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL.vec)
- Colombia (CO) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO.vec)  
- Costa Rica (CR) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR.vec)
- Cuba (CU) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU.vec) 
- República Dominicana (DO) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO.vec)
- Ecuador (EC) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC.vec)
- España (ES) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES.vec) 
- Francia (FR) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR.bin)  - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR.vec)
- Great Britain (GB) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB.vec) 
- Guinea Equatorial (GQ) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ.bin)  - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ.vec)
- Guatemala (GT) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT.bin)- [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT.vec)
- Honduras (HN) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN.bin)  - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN.vec)
- México (MX) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX.bin)   - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX.vec)   
- Nicaragua (NI) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI.bin)   - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI.vec)
- Panamá (PA) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA.vec)
- Perú (PE) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE.bin)   - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE.vec)
- Puerto Rico (PR) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR.vec)
- Paraguay (PY) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY.vec)
- El Salvador (SV) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV.vec)
- United States of America (US) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US.vec) 
- Uruguay (UY) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY.bin)- [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY.vec)
- Venezuela (VE) - [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE.bin) - [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE.vec)                            
                                      
 **LARGE:**   [ALL](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL.bin)

Our _ALL_ model is learned from the entire corpora. 

**Note:** There is previous version of the ALL word embedding with more than 2M tokens [ALL 2M](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-2M.bin)


## Analysis of regional resources

![Geographic visualization of the semantic similarity, similar colors imply semantic similarity](fig-region-emo-colors-clustering-umap-3.png)

# Regional word embeddings (semantic) and vocabularies (lexical)

Regional word embeddings for variations of the Spanish language. For the following UMAP 2D projections we selected a subset of more than 100K tokens that appear in at least 10 regions (see this [notebook](https://github.com/sadit/RegionalSpanish/blob/main/notebooks/common-vocabulary.ipynb) for more details.)

<div style="display: inline-block; width: 32%; vertical-align: top;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-umap-common-voc-ALL.png" width="100%" alt="lexical" />
All regions combined - Spanish language.
</div>
<div style="display: inline-block; width: 32%;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-umap-common-voc-AR.png" width="100%" alt="lexical" />
Argentinean variation of the Spanish language
</div>
<div style="display: inline-block; width: 32%; vertical-align: top;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-umap-common-voc-MX.png" width="100%" alt="lexical" />
Mexican variation of the Spanish language
</div>

Colors are also 3D UMAP projections, and therefore, color clusters are also meaningful. Please note that UMAP projections are quite stable in terms of shapes. The different shapes indicate that different regions contain different definitions of their common tokens. Therefore, tasks having a strong influence of the regional meanings may take advantage of regional resources.

Take a look on this [notebook](https://github.com/sadit/RegionalSpanish/blob/main/notebooks/explore-region-similarities.ipynb). Here you how definitions vary from region to region, for instance see the definition of _iglesia_ (church), where US spanish speakers define as evangeliques and other regions catholics. Another example comes from the _america_ token which referes to geographic terms in almost any region and football soocker teams for the MX region.

# Lexical and semantic comparative between regions
Affinity matrices of the Spanish language regional vocabularies using lexical (left) and semantic models (right.)
<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-common-words-lexical-affinity-matrix.png" width="100%" alt="lexical" />
Lexical comparison (using inverse document frequencies as weights.) It uses the set of common words to reduce the distance values. You can see more details in this <a href="https://github.com/sadit/RegionalSpanish/blob/main/notebooks/visualize-common-voc-lexical.ipynb">notebook</a>.
</div>
<div style="display: inline-block; width: 49%; vertical-align: top;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-common-words-semantic-affinity-matrix.png" width="100%" alt="semantic" />
Semantic comparison. It represents each region as the  <a href="https://en.wikipedia.org/wiki/Nearest_neighbor_graph">all-knn graph</a> using each regional word embeddings as input for the knn. We used k=33 and the cosine distance as weights. The procedure is detailed <a href="https://github.com/sadit/RegionalSpanish/blob/main/src/umap-embeddings-with-common-voc.jl">here</a>.
</div>

## 2D UMAP visualizations
<div style="display: inline-block; width: 32%; vertical-align: top;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-voc-lexical-umap.png" width="100%" alt="lexical" />
2D UMAP projection of regional vocabularies (cosine similarity)
</div>
<div style="display: inline-block; width: 32%; vertical-align: top;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-voc-semantic-umap.png" width="100%" alt="lexical" />
2D UMAP projection of regional word embeddings (cosine similarity)
</div>
<div style="display: inline-block; width: 32%; vertical-align: top;">
<img src="https://raw.githubusercontent.com/sadit/RegionalSpanish/main/figs/fig-emo-umap.png" width="100%" alt="emoji" />
2D UMAP projection of regional emojis (cosine similarity)
</div>

# Corpora identifiers
Our resources were created from geotagged Twitter messages from listening the public stream from 2016 to 2019 on countries with a large number of Spanish-speakers. We share a sample of this corpora to allow researchers and enthusiastic people to fetch and explore the data. In the following URLs you will find 50k message identifiers (per country). You can use a tool like [Twarc](https://github.com/DocNow/twarc) to rehydrate identifiers to full messages.

- [AR](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-AR.tsv.gz)
- [BO](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-BO.tsv.gz)
- [BR](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-BR.tsv.gz)
- [CA](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-CA.tsv.gz)
- [CL](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-CL.tsv.gz)
- [CO](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-CO.tsv.gz)
- [CR](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-CR.tsv.gz)
- [CU](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-CU.tsv.gz)
- [DO](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-DO.tsv.gz)
- [EC](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-EC.tsv.gz)
- [ES](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-ES.tsv.gz)
- [FR](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-FR.tsv.gz)
- [GB](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-GB.tsv.gz)
- [GT](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-GT.tsv.gz)
- [HN](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-HN.tsv.gz)
- [MX](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-MX.tsv.gz)
- [NI](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-NI.tsv.gz)
- [PA](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-PA.tsv.gz)
- [PE](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-PE.tsv.gz)
- [PR](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-PR.tsv.gz)
- [PY](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-PY.tsv.gz)
- [SV](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-SV.tsv.gz)
- [US](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-US.tsv.gz)
- [UY](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-UY.tsv.gz)
- [VE](http://ingeotec.mx/~sadit/regional-spanish-sample/sample-id-VE.tsv.gz)

## More resources

Please clone our github repository:

- <a href="https://github.com/sadit/RegionalSpanish">https://github.com/sadit/RegionalSpanish</a>

there you will find more metadata, resources, and code: regional vocabulary, regional embeddings, knn graphs of concepts (tokens), token comparison among regions, among others.

BILMA language models are availabe at:

- [https://github.com/msubrayada/bilma](https://github.com/msubrayada/bilma)

# Corpora

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
- words, punctuactions, and emojis are tokens

We only consider Twitter as data source; messages with URLs were discarded, retweets and _fourth square_ and other automatic messages were removed. Short messages (less than 7 tokens) were also discarded.


# Contact us

Please contact us if you want to know more about these resources:

- Eric S. Tellez - `eric.tellez@infotec.mx`
