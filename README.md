# Parcellating the parcellation issue
[![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg

### Build the book on Neurolibre
This book has been prepared as a submission to the [Neurolibre](https://neurolibre.org) preprint service. The build can be tested with the [roboneuro](https://roboneuro.herokuapp.com/) preview service. 

### Build the book locally
- Clone this repository
- Run `pip install -r requirements.txt` (recommended in a virtual environment).
- For a fresh build, remove the content of `content/_build/`
- Run `jb build content/`

A static version of the book will be generated on `methodes_neurocog/_build/html/`.

### Hosting the book

The html version of the book is hosted on the `gh-pages` branch of this repo. Navigate to your local build and run,
- `ghp-import -n -p -f content/_build/html`

This will automatically push your build to the `gh-pages` branch. More information on this hosting process can be found [here](https://jupyterbook.org/publish/gh-pages.html#manually-host-your-book-with-github-pages).

## Credits

This project is created using the excellent open source [Jupyter Book project](https://jupyterbook.org/) and the [Neurolibre template](https://github.com/neurolibre/template/). Further credits for the book can be found in the book itself.
