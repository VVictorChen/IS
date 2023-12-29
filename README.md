# Stroke
Work in the field of stroke

Our team has developed a machine learning-based model for risk stratification for ischemic stroke, which is now available for download. You can download the [CCRS](https://pypi.org/project/CCRS/) package as well. 

![Figure](https://www.cdc.gov/stroke/images/Stroke-Medical-Illustration.jpg?_=77303)

Example:

```python
import pickle
import scipy.stats as st
import pandas as pd
import numpy as np
import imblearn
import CCRS
loaded_model = pickle.load('./data/IS_RF_lessFea.pkl')
Traindata = pd.read_csv('./data/CIS_age.csv')
X_test = $INPUT_DATA
scores = loaded_model.predict_proba(X_test)
value = scores[:,1]
stroke_risk_group = risk_label(value)
df = pd.DataFrame({'y_pred': scores[:,1],'Age':X_test.Age})
stroke_RRS = RRScore(df,Traindata,mean=51.5,sd=10.8)
result = pd.DataFrame({'stroke risk group': stroke_risk_group,'stroke relative risk rank':stroke_RRS})
```

Features of the CIS model:

![Features](https://github.com/VVictorChen/Stroke/blob/main/Model/CIS%20features.png)

Output:

| stroke risk group | stroke relative risk rank |
| -----------       | -----------               |
| mild              | 56.7%                     |
| mild              | 78.5%                     |
| mild              | 38.9%                     |
| moderate          | 97.0%                     |
| severe            | 63.3%                     |

How to cite:

Chen, B., Ruan, L., Yang, L., Zhang, Y., Lu, Y., Sang, Y., Jin, X., Bai, Y., Zhang, C., and Li, T. (2022). Machine learning improves risk stratification of coronary heart disease and stroke. Ann Transl Med 10, 1156. 10.21037/atm-22-1916
        
        
        
        
        
        .
