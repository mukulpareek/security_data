# security_data

This repo contains daily files of security news extracted from about 25 security related data files.  Each daily file is a pickle file containing a Pandas dataframe readable in Python.  

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
