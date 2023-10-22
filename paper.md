---
title: 'Parcellating the parcellation issue - a proof of concept for reproducible analyses using Neurolibre'
tags:
  - Preprint
  - Jupyter Book
  - Reproducible article
  - Neuroscience
authors:
  - name: Pierre Bellec
    orcid: 0000-0002-9111-0699
    affiliation: "1, 2"
  - name: Saâd Jbabdi
    orcid: 0000-0003-3234-5639
    affiliation: "3"
  - name: R. Cameron Craddock
    orcid: 0000-0002-4950-1303
    affiliation: "4"
affiliations:
 - name: Université de Montréal, Montréal, Canada
   index: 1
 - name: Centre de recherche de l'université de Montréal, Montréal, CA
   index: 2
 - name: University of Oxford, Oxford, UK
   index: 3
 - name: brainhack.org
   index: 4

date: 22 October 2021
bibliography: paper.bib
---

# Summary

Back in 2017, a special issue on the topic of **brain parcellation and segmentation** was published in the journal Neuroimage. We acted as guest editors for this special issue, and wrote an editorial [@Craddock2018-ou] providing an overview of all papers, sorted into categories. The categories were generated using a data-driven parcellation analysis, based on the words contained in the abstract of the articles. This jupyter book will allow interested readers to reproduce this analysis, as a proof of concept for reproducible publications using [jupyter books](https://jupyterbook.org/) and the [Neurolibre](https://neurolibre.org) preprint server.

# Acknowledgements

NeuroLibre is sponsored by the Canadian Open Neuroscience Platform (CONP), Brain Canada, Cancer Computers, the Courtois foundation, the Quebec Bioimaging Network, and Healthy Brains for Healthy Life.

 \awesomebox[red]{2pt}{\faExclamationCircle}{red}{\textbf{NOTE}}

 > **_NOTE:_** The following section in this document repeats the narrative content exactly as                     found in the [corresponding NeuroLibre Reproducible Preprint (NRP)](https://preprint.neurolibre.org/10.55458/neurolibre.00010). The content was                     automatically incorporated into this PDF using the NeuroLibre publication workflow [@Karakuzu2022-nlwf] to                     credit the referenced resources. The submitting author of the preprint has verified and approved the                     inclusion of this section through a GitHub pull request made to the [source repository](https://github.com/pbellec/editorial_parcellation) from which this document was built.                     Please note that the figures and tables have been excluded from this (static) document. **To interactively explore such outputs and re-generate them, please visit the corresponding [NRP](https://preprint.neurolibre.org/10.55458/neurolibre.00010).**                     For more information on integrated research objects (e.g., NRPs) that bundle narrative and executable content for reproducible and transparent publications,                     please refer to @Dupre2022-iro. NeuroLibre is sponsored by the Canadian Open Neuroscience Platform (CONP) [@Harding2023-conp].

Text mining
===========


List of papers
--------------


We first assembled the title, the name of the corresponding author, and the abstract for all the articles into a tabular-separated values (tsv) file, which we publicly archived on [Figshare](https://doi.org/10.6084/m9.figshare.5497468.v2). We use the [Repo2Data](https://github.com/SIMEXP/Repo2Data) tool developped by the NeuroLibre team to collect these data and include them in our reproducible computational environment.


Word features
-------------


For each paper, we used [scikit-learn](http://scikit-learn.org) to extract a bag of words representation for each abstract, picking on the 300 most important terms seen across all articles based on a term frequency-inverse document frequency [(tf-idf) index](http://scikit-learn.org/stable/modules/feature_extraction.html#text-feature-extraction). Following that, a special value decomposition was used to further reduce the dimensionality of the abstracts to 10 components. We ended up with a component matrix of dimension 38 (articles) times 10 (abstract text components). The distribution of each of the 38 articles across the 10 components is represented below. Note how some articles have particular high loadings on specific components, suggesting these may capture particular topics. Rather than visually inspect the component loadings to group paper ourselves, we are going to resort to an automated parcellation (clustering) technique.


Parcellate the papers
---------------------


Now that the content of each paper has been condensed into only 10 (hopefully informative) numbers, we can run these features into a trusted, classic parcellation algorithm: Ward's agglomerative hierarchical clustering, as implemented in the scipy library. We cut the hierarchy to extract 7 "paper parcels", and also use the hierarchy to re-order the papers, such that similar papers are close in order, as illustrated in a dendrogram representation.


Similarity matrix
-----------------


So, to get a better feel of the similarity between papers that was fed into the clustering procedure, we extracted the 38x38 (papers x papers) correlation matrix across features. Papers are re-ordered in the matrix according to the above hierarchy. Each "paper parcel" has been indicated by a white square along the diagonal, which represents the similarity measures between papers falling into the same parcel.


Word cloud
----------


Now, each paper of the special issue has been assigned to one and only one out of 7 possible "paper parcel". For each paper parcel, we can evaluate which words contribute more to the dominant component associated with that parcel.


Categories
----------


Thanks to the word clouds, these simple data-driven categories turned out to be fairly easily interpretable. For example, the word cloud of the category number 4 features prominently words like "white", "matter" and "bundles". If we examine the exact list of papers included in this category, we see that it is composed of four papers, which all considered parcels derived from white matter bundles with diffusion imaging.
We can also check the distribution of component loadings for this category alone. As expected, there is a certain similarity in the component loadings for these papers, in particular along `component 4`:



# References
