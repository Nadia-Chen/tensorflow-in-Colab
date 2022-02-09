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
- How to connect colab with jupyter notebook in local?
  - step1: 
  
  Change to base source (or any other source which already have jupyter notebook)
  - step2:
  
  Install and enable the jupyter_http_over_ws jupyter extension
  ```pip install jupyter_http_over_ws
  jupyter serverextension enable --py jupyter_http_over_ws 
  ```
  - step3:
  
  Start the server and authenticate
  The new notebook server starts as normal, but you need to set a flag to explicitly trust WebSocket connections from the Colaboratory frontend.
  ```
  jupyter notebook \
  --NotebookApp.allow_origin='https://colab.research.google.com' \
  --port=8888 \
  --NotebookApp.port_retries=0
  ```
  Once the server starts, it will output a message with the initial backend URL to authenticate with. Make a note of this URL, you will need to provide this        information in the next step.
  - step4:
  
    In Colaboratory, click the "Connect" button and select "Connect to native code executor...". Enter the URL from the previous step in the dialog that appears, then click the "Connect" button. After doing this, you should already be connected to the local runtime.
  
