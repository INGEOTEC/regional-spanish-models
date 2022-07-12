---
author: "Eric S. Tellez"
title: "Regionalized word embeddings for the Spanish-language"
date: "21th April 2016"
---


# Regionalized word embeddings for the Spanish-language

This site shares the regionalized resources presented in the following manuscript:

_A large scale lexical and semantic analysis of Spanish language variations in Twitter._ Eric S. Tellez, Daniela Moctezuma, Sabino Miranda, and Mario Graff. https://arxiv.org/abs/2110.06128.

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

# Semantic models
We created 26 word-embedding models with [fastText](https://fasttext.cc/), one per country. We learned 300 dimension vectors and use default hyper-parameters. We provide two kinds of models, `bin` which correspond to binary version of the model and `vec` which is the ascii version of the same model; ascii version can be parsed and used without fastText and also are used by the same fastText to create supervised (clasification) models with pretrained word embeddings.

- Argentina (AR) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/AR-8d.vec)
- Bolivia (BO) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BO-8d.vec)
- Brazil (BR) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/BR-8d.vec)
- Canadá (CA) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CA-8d.vec)
- Chile (CL) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CL-8d.vec)
- Colombia (CO) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CO-8d.vec)
- Costa Rica (CR) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CR-8d.vec)
- Cuba (CU) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/CU-8d.vec)
- República Dominicana (DO) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/DO-8d.vec)
- Ecuador (EC) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/EC-8d.vec)
- España (ES) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ES-8d.vec)
- Francia (FR) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/FR-8d.vec)
- Great Britain (GB) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GB-8d.vec)
- Guinea Equatorial (GQ) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GQ-8d.vec)
- Guatemala (GT) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/GT-8d.vec)
- Honduras (HN) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/HN-8d.vec)
- México (MX) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/MX-8d.vec)
- Nicaragua (NI) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/NI-8d.vec)
- Panamá (PA) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PA-8d.vec)
- Perú (PE) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PE-8d.vec)
- Puerto Rico (PR) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PR-8d.vec)
- Paraguay (PY) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/PY-8d.vec)
- El Salvador (SV) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/SV-8d.vec)
- United States of America (US) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/US-8d.vec)
- Uruguay (UY) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/UY-8d.vec)
- Venezuela (VE) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/VE-8d.vec)
- ALL (ALL) -- 300d: [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL.vec); 32d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-32d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-32d.vec); 16d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-16d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-16d.vec); 8d [bin](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-8d.bin) [vec](http://geo.ingeotec.mx/~sadit/regional-spanish-models/ALL-8d.vec)



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


# Regional emojis

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

## More resources:
<div>
Please clone our <a href="https://github.com/sadit/RegionalSpanish">github repository</a>
where you can find more metadata, resources, and code: regional vocabulary, regional embeddings, knn graphs of concepts (tokens), token comparison among regions, among others.
</div>


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
- words, punctuactions, and emojis are tokens

We only consider Twitter as data source; messages with URLs were discarded, retweets and _fourth square_ and other automatic messages were removed. Short messages (less than 7 tokens) were also discarded.


# Contact us

Please contact us if you want to know more about these resources:

- Eric S. Tellez - `eric.tellez@infotec.mx`
