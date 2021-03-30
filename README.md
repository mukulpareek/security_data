# security_data

This repo contains daily files of security news extracted from about 25 security related data files.  Each daily file is a pickle file containing a Pandas dataframe readable in Python.  

Basically, 
```python
import joblib
joblib.load('filename')
```
should give you the data in each individual file.

To use, clone/download the repo and run the code below to get `final_df` which will have a giant dataframe combining the information from all the files.  Or use the code in https://github.com/mukulpareek/notebooks/blob/master/Step%202%20-%20Combine%20Files.ipynb

```python

import os
import pandas as pd
import joblib
from tqdm import tqdm
import datetime
from datetime import datetime
from bs4 import BeautifulSoup

a = pd.DataFrame({'filename1': os.listdir()})
b = a.filename1.str.startswith("security")
files = list(a[b].filename1)
final_df = pd.DataFrame()

for file in tqdm(files):
    df = joblib.load(file)
    if final_df.empty:
        final_df = df
    else:
        final_df = pd.concat([df, final_df])
```
