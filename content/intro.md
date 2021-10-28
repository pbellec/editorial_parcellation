---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/pbellec">
        <img src="https://avatars.githubusercontent.com/u/1670887?v=4?s=100" width="100px;" alt=""/>
        <br /><sub><b>Pierre bellec</b></sub>
      </a>
      <br />
        <a title="Contenu">🤔</a>
        <a title="Code">💻</a>
        <a title="Révision du texte">👀</a>
    </td>
    <td align="center">
      <a href="https://users.fmrib.ox.ac.uk/~saad/">
        <img src="https://users.fmrib.ox.ac.uk/~saad/Saad2013.jpg" width="100px;" alt=""/>
        <br /><sub><b>Saâd Jbabdi</b></sub>
      </a>
      <br />
        <a title="Révision du texte">👀</a>
    </td>
    <td align="center">
      <a href="https://github.com/ccraddock">
        <img src="https://avatars.githubusercontent.com/u/1725272?v=4?s=100" width="100px;" alt=""/>
        <br /><sub><b>R. Cameron Craddock</b></sub>
      </a>
      <br />
        <a title="Révision du texte">👀</a>
    </td>    
  </tr>
</table>

# Introduction

Back in 2017, we were invited as guest editors for the journal "neuroimage", and organized a special issue on the topic of **brain parcellation and segmentation**. After months of receiving submissions and going through the stages of peer review for all articles, there were 38 papers accepted for publication. We were left with the difficult task of writing a short editorial summarizing concisely this fairly large snapshot of a vibrant area of neuroimaging research. Quickly we realized that we needed to group the papers into more specific categories than the general umbrella of parcellation and segmentation.


Parcellation, segmentation (or clustering and community detection) are just different names for generic techniques aimed at finding broad categories in the data, while abstracting away less relevant finer-grained information. So when facing the problem of drawing categories of papers for the editorial, it was only natural to apply a parcellation analysis. In other words, we decided to **parcellate the parcellation (special) issue**. This jupyter book will allow interested readers to reproduce the short analysis that went into building the categories. You can read the final editorial [here](https://doi.org/10.1016/j.neuroimage.2017.11.063) (sadly behind a paywall).

This reproducible analysis is possible thanks to the following projects:
 * The [python](https://www.python.org/) programming language.
 * [Jupyter book](https://jupyterbook.org) is used to generate the html pages, and is itself based on [sphynx](https://www.sphinx-doc.org).
 * The [NeuroLibre](https://neurolibre.org) is hosting this jupyter book.
 * The [scipy](https://www.scipy.org/) scientific library.
 * The [seaborn](https://seaborn.pydata.org/) visualization library.
 * The [wordcloud](https://amueller.github.io/word_cloud/) library.
