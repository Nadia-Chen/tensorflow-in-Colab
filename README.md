# tensorflow-in-Colab
It is too troublesome to configure tensorflow through conda on macOS. After many trials, I decided to give up the local environment and turned to Google's colab
## ATTENTION: 
Only a copy is saved in github. If you need to modify it, you need to go back to colab to make modifications, and back up the copy to github again.
## Tips：
- How to upload local files to colab without using Google Drive?
```
# step1:
from google.colab import files
uploaded = files.upload() # choose the local file
# step2:
import io
data = io.BytesIO(uploaded['bankruptcy_balance.csv'])
# step3:
import pandas as pd # using pandas or so on to get your file.
df = pd.read_csv(data)
```
