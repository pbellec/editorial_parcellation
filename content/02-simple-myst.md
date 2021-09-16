---
jupytext:
  text_representation:
    format_name: myst
kernelspec:
  display_name: Python 3
  name: python3
repository:
  url: https://github.com/neurolibre/template
---

## What is MyST Markdown? 

In addition to Jupyter Notebooks, Jupyter Book also supports a special flavour of Markdown called MyST (or Markedly Structured Text). It is designed to make it easier to create publishable computational documents written with Markdown notation.

The following sections present the same content in the Jupyter Book (`01-simple_notebook.ipynb`) in MyST format.

## How to make a code cell collapsible in the Jupyter Book? 

In MyST, a code cell is defined as follows: 

```{code-cell} python3

print("This is a code cell using Python3 kernel.")

```

To hide a code cell, you can simply add `:tags: [hide-cell]` expression to the beginning of a code cell: 

```{code-cell} python3
:tags: [hide-cell]

print("This code cell will be hidden in the Jupyter Book.")

```

Please visit [Jupyter Book documentation](https://jupyterbook.org/content/index.html) for more information about the [MyST Markdown](https://jupyterbook.org/content/myst.html).

## How to render interactive figures?

The code cell below uses `Plotly` to generate a simple interactive figure. When the Jupyter Book is built, the example figure will be rendered.

```{code-cell} python3

import plotly.express as px
from plotly.offline import plot

# Example dataset 
df = px.data.gapminder()

# Scatter plot with slider
fig = px.scatter(df.query("year==2007"), x="gdpPercap", y="lifeExp", size="pop", color="continent",
           hover_name="country", log_x=True, size_max=60)

# fig.show() # You can use this command for inline rendering as you are developing your notebook.

plot(fig, filename = 'example_figure.html')
display(HTML('example_figure.html'))

```