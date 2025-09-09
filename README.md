# [DM2025] Lab 1 – Environment Setup

Hi everyone,

We will have our first lab session (for Q&A) on **September 15 (Monday)** at **9:00 AM** via our [YouTube Stream](https://www.youtube.com/@NTHU_ISA5810_DataMining)/**Classroom**. Please be on time.

The Lab tutorial video will be launched on [YouTube Channel](https://www.youtube.com/@NTHU_ISA5810_DataMining) before **September 15**.

We strongly recommend setting up the environment on your personal laptop before the lab session so that you can follow along smoothly.

This document provides detailed instructions for setting up the environment required for the course.

---

## System Requirements

Please make sure you have the following installed:

* Python 3.11.0 (recommended)
* uv (Python virtual environment manager)
* Git
* GitHub account
* Jupyter Notebook

---

## Setup Instructions

### 1. Install Python 3.11.0 (If you use your own version, you take risk)

Download and install Python 3.11.0 (recommended):
https://www.python.org/downloads/release/python-3110/

During installation, check "**Add Python to PATH**".

Verify installation:

```bash
python --version
```
Expected output:
Python 3.11.0  

### 2. Create a GitHub Account and Install Git
#### Sign up for GitHub: https://github.com/  
#### Install Git:  
##### Windows: https://gitforwindows.org/  
##### Linux:

```bash
sudo apt install git-all
```
##### macOS:


```bash
brew install git
```
#### Verify installation:

```bash
git --version
```
Configure Git (replace with your GitHub username and email):
```bash
git config --global user.name "YOUR_USERNAME"
git config --global user.email "your_email@example.com"
```

![git](img/pic6ann1.png)

### 3. Fork the Repository to your GitHub Account  
Go to: [DM Lab 1](https://github.com/leoson-wu/DM2025-Lab1-Exercise.git) in GitHub,  
Sign in to your GitHub account
Click "Fork" to copy it into your own GitHub account.  
![fork](img/pic9ann1.png)

And it will redirect you to a "copy" of the repository in your own account. Once in your account (check that your name shows up at the top left corner), click the green button "Code", and the clipboard button beside the **link** that pops up. 

![gitpic3](img/gitpic3.png)
### 4. Create a Project Folder and Clone the Repository from your GitHub to your Project Directory   
Choose a location for your labs and create a directory:

Open a "Command Prompt" window in Windows or a "Terminal" window in macOS/Linux. Type the following commands, followed by the Enter key for each line: 

    cd <yourpath>
    mkdir DM2025Labs
    cd DM2025Labs
    git init
    git clone <link you copied in the previous step>
    
Replace \<yourpath\> by the path where you're going to store your documents. 
Below is an example, where I store my Lab in the "new" folder.

![gitpic4](img/gitpic4.png)

### 5. Install uv
In terminal or PowerShell:

```bash
pip install uv
uv --version
```
### 6. Create a Virtual Environment with uv
```bash
cd <your path to the DM2025-Lab1-Exercise>
uv venv
```

This creates a .venv folder inside the project.

### 7. Install the Dependent Libraries

Navigate to directory:  `DM2025-Lab1-Exercise`  
#### Quick install
```bash
uv sync
```
This installs all required Python packages: jupyter numpy pandas matplotlib plotly nltk scikit-learn seaborn pami umap-learn   
#### (Alternative) Manually install Libraries
You may need to add libraries manually if the **step 8** cannot install the required libraries successfully:  
```bash
uv add jupyter numpy pandas matplotlib plotly nltk scikit-learn seaborn pami umap-learn
```
You can also install extra libraries if needed.  
```bash
uv add <library_name>
```
#### (Alternative) If you are using Kaggle or Colab (if not, you can skip)   
Install the library with these commands 
![pip3 install](img/pipinstall.jpg)

### 8. Register Jupyter Kernel
Navigate to directory:  `DM2025-Lab1-Exercise`  
```bash
uv run python -m ipykernel install --user --name=dm2025lab --display-name "Python (dm2025lab)"
```
### 9. Run Notebook  
#### Run in VS Code
If using VS Code:

Open your terminal/PowerShell  
```bash
cd <your path to the DM2025-Lab1-Exercise>
code
```
Open the `DM2025-Lab1-Master.ipynb`  

Then select "Python (dm2025lab)" as the kernel in the top-right corner.  
![vs code select jupyter kernel](img/vs_code.png)  


#### (Alternative) Run Jupyter Notebook in Browser  
Start Jupyter:

```bash
cd <your path to the DM2025-Lab1-Exercise>
uv run jupyter notebook
```
![jupyter notebook](img/pic3ann1.png)

If error occurs:

```bash
python -m notebook
```  
A browser window will open.  
Open the `DM2025-Lab1-Master.ipynb` 

Select **Python (dm2025lab)** as the notebook kernel on the top-right corner.  
![open Jupyter](img/pic4ann1.png)

#### (Alternative) Run in Kaggle
If you cannot set up Python locally:  
Create an account: https://www.kaggle.com/  
Go to: https://www.kaggle.com/kernels → "New Notebook"  
Run the test script.  
For missing libraries (e.g., PAMI), install manually:  

```bash
!pip install pami
```
![kaggle](img/pic8ann1.png)


### 10. Test Your Environment
Open the `DM2025-Lab1-Master.ipynb`

Paste the script below into a notebook cell and run it:

```Python
# test code for environment setup
import pandas as pd
import numpy as np
import nltk
nltk.download('punkt') # download the NLTK datasets
from sklearn.datasets import fetch_20newsgroups
from sklearn.feature_extraction.text import CountVectorizer
import plotly as py
import math
# !pip install PAMI
import PAMI # if it cannot find the module 'PAMI', add a command line: !pip install PAMI before importing it
import umap

categories = ['alt.atheism', 'soc.religion.christian', 'comp.graphics', 'sci.med']
twenty_train = fetch_20newsgroups(subset='train', categories=categories, shuffle=True, random_state=42)
```

![test pic](img/testpic1.png)

If no errors occur, your environment is ready.



### Troubleshooting
Ask classmates or TAs for help before the lab if you encounter installation issues.  
If you prefer a GUI for Git, use GitHub Desktop: https://desktop.github.com/  
Good luck with the setup and see you on Monday, Sept 15!  

Best regards,
The TAs

---
# If everthing is OK, you can start to do the lab ...
---

# Save your Progress by Push 
Remember to save your notebooks. You will also have to "Push" the changes you've made in your computer to the internet. To do this, open a "Command Prompt" window in Windows or a "Terminal" window in macOS/Linux. Type the following commands followed by the Enter key: 

    cd <your path to the DM2025-Lab1-Exercise>
    git add *
    git commit -m "yourmessage"
    git push 
    
You can replace "yourmessage" with something like "Finished Ex1 and Ex2. Added graph for Ex. 6" . You can save and commit as often as you like. Below is an example:

![gitpic7](img/gitpic7.png)

# Hand in your Homework

Go to the [DM Lab 1 Homework](https://github.com/leoson-wu/DM2025-Lab1-Exercise/blob/main/DM2025-Lab1-Homework.ipynb) in Git and follow the same process above.  Make sure to commit and save your changes to your repository __BEFORE the deadline for each phase (September 28th and October 19th, 11:59 pm, Sunday)__. During the second phase, the answers from the first phase will not be considered if they can not be pushed on time. 

Make sure to hand in 2 notebooks, including: 
1. `DM2025-Lab1-Master.ipynb` from [DM Lab 1](https://github.com/leoson-wu/DM2025-Lab1-Exercise/blob/main/DM2025-Lab1-Master.ipynb)
2. `DM2025-Lab1-Homework.ipynb` from [DM Lab 1 Homework](https://github.com/leoson-wu/DM2025-Lab1-Exercise/blob/main/DM2025-Lab1-Homework.ipynb)

![gitpic6](img/gitpic6.png)

When you're done (or at any moment), find your repository link. Open the **\[DM2025\] Homework 1** assignment page on our [NTU COOL platform](https://cool.ntu.edu.tw/login/portal) for each phase. Make a submission and paste the link to your git repository (or the link to your Kaggle kernel).  

You can find your repository link by logging into [Github](https://github.com/), clicking on your profile icon on the upper right corner, selecting "Your repositories", and clicking on the name of your repository. Then copy the link in your browser.  

Again, __we will not consider pushes made after the deadline__. 

![deadline](img/Deadline.png)

That's it! We wish you Good luck!