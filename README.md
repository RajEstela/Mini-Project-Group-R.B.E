# CS1015 Mini Project
 
This is a group mini project for NTU CS1015 Introduction to Data Science & Artifical Intelligence.
 
## Intoduction & Objectives
The purpose of this project is to analyse the Competetive League of Legend dataset from Oracle Elixir (https://oracleselixir.com/) from Kaggle (https://www.kaggle.com/datasets/barthetur/league-of-legends-2024-competitive-game-dataset). The dataset contains the games information of every single official competitive game of League of Legends in 2024.
 
The objectives of the analyse is to find out the following:
1. Analyze official competitive matches and identify the best champion class combination that will result in a win.
 
2. What is the most optimal and suitable game variable in predicting the total combined gold value? Amongst these variables Total kills, Total minion score, Neutral Objectives and Structures taken down
 
3. Can we accurately predict the outcome of the match? Based on team compositions, total gold earned, kill score, creep scores, neutral objectives score, and structures taken score.
 
## Installation & Setup
### Code and Resource used
Editor - Jupyter Notebook
 
Python Version 12
 
Python Packages:
 
Data Manupluation
- Numpy
- Pandas
 
Data Visualisation:
- Seaborn
- Matplotlib
- IPython.display
- Graphviz
- scipy.stats
 
Machine Learning:
- Sklearn
 
Graphvix requires additional setup, refer to (https://graphviz.org/download/)
for specific OS.
 
Steps for windows are specified above link, but we will go through them here:
1. Download the package file from (https://gitlab.com/api/v4/projects/4207231/packages/generic/graphviz-releases/10.0.1/windows_10_msbuild_Release_graphviz-10.0.1-win32.zip).
2. Extract the file to a driectory you prefer
3. Search for "Edit the system environment variables" in search bar and click it
4. Click on "Environment Variables.."
5. Under "System Variables", click on "path", make sure it is highlighted, and click "edit"
6. Add < Your preferred path >\Graphviz\bin & < Your preferred path >\Graphviz\bin\dot.exe and click "OK"
7. Click "OK" on the "Environment Variables" window
8. Lastly, click "OK" on the "System Properties" window
 
## Data
### Source Data
The dataset is  Competitive League of Legend dataset from Oracle Elixir (https://oracleselixir.com/) from Kaggle (https://www.kaggle.com/datasets/barthetur/league-of-legends-2024-competitive-game-dataset).
 
The dataset contains the games information of every single official competitive game of League of Legends in 2024.
 
The data from Kaggle comes in a zip file with 1 excel file & 3 csv files:
1. 2024_LoL_esports_match_data_from_OraclesElixir.xlsx
2. 2024_LoL_esports_match_data_from_OraclesElixir_gamedata.csv
3. 2024_LoL_esports_match_data_from_OraclesElixir1.csv
 
For our project, we just requires the 2nd file which contains the game data.
 
Additionally we also require the Champion information data from here (https://www.kaggle.com/datasets/uskeche/leauge-of-legends-champions-dataset/data). This contains the Champion info like SN, Champion Names, Class & Skills etc.
 
## File Structure
    .Mini-Project-Group-R.B.E/
    ├── datasets/
    │   ├── 2024_LoL_esports_match_data_from_OraclesElixir_gamedata.csv
    │   ├── cleaned_dataset.csv
    │   ├── cleaned_dataset_gold.csv
    │   ├── cleaned_dataset_matchWinner.csv
    │   └── LoL-Champions.csv
    ├── .gitignore
    ├── 1-problem-definition.ipynb
    ├── 2-data-preparation-and-cleaning.ipynb
    ├── 3-exploratory-data-analysis.ipynb
    ├── Data Science Mini Project_v2.pptx
    ├── Mini_Proj_R1.0_v2.ipynb
    └── README.md
 
## Results & Evaluation
1. Analyze official competitive matches and identify the best champion class combination that will result in a win.
 
The approach we used for the EDA to visuaise the Champion Class Combination and determine the best Combination.
 
Based on the results, the best team combination is Warrior for Top position, Warrior for Jungle position, Mage for Mid position, Masksman for bot position & Support for support position
 
2. What is the most optimal and suitable game variable in predicting the total combined gold value? Amongst these variables Total kills, Total minion score, Neutral Objectives and Structures taken down
 
To find the most optimal & suitable game variable in prodicting total combine gold:
-  Visualise the distrubution of each variable with Boxplot, Histogram & Violin plot
- Comapre the game variables with gold earned with joint plot and pair plot
- Putting the game variables into a correlation matrix
- Train Regression Models on game variables with Gold
- Using goodness of fit, explained variance & mean square error to determine the best game variable to predict most gold earned
 
Based on the info, we conclude the Total CS is the best variable to predict total combine gold
 
3. Can we accurately predict the outcome of the match? Based on team compositions, total gold earned, kill score, creep scores, neutral objectives score, and structures taken score.
 
Prediction of outcome of match:
- At first we used Linear regression to predict the outcome, the model gives us a negative explain variance
- We learned that in order to use linear regression, the dataset should have a linear relationship. Checking the response & predictors, they are not in a linear relationship
- We decided to use Random Tree Classifier to predict and train the outcome since the Predictor is a binary with Win / loss outcome
- To evualate the model, we decide to use Grid Search Metrics - Acccuracy, Precision & Recall
- The initial Random Tree Classifer gives a 96% accuracy
- To train the model, we use Hyper Paramater Tuning
- Using Random Search, it determine the best max_depth would be 18, and best n_estimators be 181
 
We get the following result afte tuning the model:
- Accuracy - 97% means that approximately 96.58% of the predictions made by the model were correct
- Precision - 94% means that approximately 94.12% of the instances predicted as positive by the model were actually positive
- Recall - 100% means that the model correctly identified all positive instances in the data
 
## Team Members
| Name | GitHub | Contribution |
|-|-|-|
| ESTELA YAR RAJ ALMENDRAS | https://github.com/RajEstela | Jupyter Notebook (Problem Definition #1 & #2 Data Preparation and Cleaning , Problem Definition #1 & #2 EDA, Problem Definition #3 Random Foreset Tree Classifier, Code clean up and markdowns, Presentation Slides, Video Editing) 
| BRANDON VOON YEN SENG | https://github.com/vysky | Jupyter Notebook (Problem Definition #1 & #2 Data Preparation and Cleaning, Problem Definition #1 & #2 EDA, Problem Definition #1 & #2 Linear Regression, PandasAI, Code clean up and markdowns, Presentation Slides, Video Editing)
| ELIAS CHANG RUI YUAN | https://github.com/elias-chang-ry | Jupyter Notebook (Problem Definition #1 & #2 Linear Regression Fix, README.md )
 
## Reference
- https://github.com/RajEstela/Mini-Project-Group-R.B.E
- https://oracleselixir.com/
- https://www.kaggle.com/datasets/barthetur/league-of-legends-2024-competitive-game-dataset
- https://www.kaggle.com/datasets/uskeche/leauge-of-legends-champions-dataset
- https://graphviz.org/