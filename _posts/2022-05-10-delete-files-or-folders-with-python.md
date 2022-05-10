---
toc: true
layout: post
description: steps delete files and folder using python
categories: [Python Hacks]
permalink: /how-to-delete-files-and-folders-with-python/
search_exclude: false
title: How to delete files and folders with python
show_tags: true
---
## Delete files
```python
import os
path = '/file_name'
if os.path.exists(path):
    os.remove(path)
```
## Delete empty folders

```python
import os
path = '/folder_name'
if os.path.exists(pathe):
    os.remdir(path)
```

## Delete folders with files

```python
import shutil
path = '/folder_name'
if os.path.isdir(path):
    shutil.rmtree(path)
```