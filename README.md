## Preprint template

Template repository for NeuroLibre preprint submissions.

### Step 1: Click `Use this template button` and give a name to your new repository

### Step 2: Do the following changes in [_config.yml](content/_config.yml)

```yaml
title                       : "NeuroLibre preprint template"  # Add your title
author                      : John Doe, Jane Doe  # Add author names
```
```yaml
repository:
  url: https://github.com/neurolibre/template  # The URL to your new repository
```
> At this stage, you are ready to use [RoboNeuro preview service](https://roboneuro.herokuapp.com/) to get your first book build.
---
### Step 3: Add your executable content under the `content` directory

* ✅ You can add a mixture of `Jupyter Notebooks`, `MyST` formatted markdown and plain text markdown files.
* ✅ You can organize your content in subfolders.
* ❌ We don't accept (non-executable) plain text markdown files alone.

### Step 4: Edit [_toc.yml](content/_toc.yml) according to your new content 

### Step 5: Define your execution environment under the `binder` directory

You can use any [BinderHub configuration files](https://mybinder.readthedocs.io/en/latest/using/config_files.html) that you need.
