# Dating Profile Analysis - OKCupid: Overview and Objective
This project takes a dataset of users' dating profile information from the fictional online dating webstie OKCupid, and uses various machine learning models to determine the following:
### Can a user's relationship status be predicted using other variables in their dating profile using a machine learning model, and which model performs best?
- Visualise the count of all variables (smoking status, income, relationship status, etc.) grouped by gender (male or female).
- Create various machine learning models to determine which, if any, can most accurately predict a user's relationship status based on the aforementioned other variables.

## Key insights (Summary)
> For full results, visualisations, and detailed discussion, open the Jupyter notebook date-a-scientist.ipynb in this repository.
- Cleaned messy columns, and dropped unneccessary and created useful columns, using ```pandas```.
- Visualised distribution of user variables grouped by gender using distribution plots created using```matplotlib``` and ```seaborn```.
- Created several machine learning models and trained them on the dataset to assess whether they could effectively predict a user's relationship status based on their other information.
  
## Tools and Libraries
| Purpose | Libraries Used |
|----------|----------------|
| Data manipulation | `pandas` |
| Data visualization | `matplotlib`, `seaborn` |
| Machine learning modelling | `sklearn`, `xgboost`, `imblearn` |

## Installation
1. **Clone this repository**
   ```bash
   git clone https://github.com/lloydy-92/OKCupid-Analysis.git
   cd OKCupid-Analysis
2. **(Optional) Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate       # On Windows use: venv\Scripts\activate
3. **Install dependencies**
   ```bash
   pip install pandas matplotlib seaborn sklearn imblearn xgboost jupyter
4. **Launch the notebook**
   ```bash
   jupyter notebook date-a-scientist.ipynb

## Project Structure
```bash
OKCupid-Analysis/
├── date-a-scientist.ipynb        # Main analysis notebook
├── profiles.csv      # Dataset containing user information
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

## Contributing
Contributions, suggestions, and improvements are welcome and encouraged! If you would like the enhance any aspect of the project, such as analysis or visualisations:
1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/improve-analysis
3. Commit your changes
   ```bash
   git commit -m 'Add new visualisation'
4. Push to the branch
   ```bash
   git push origin feature/improve-analysis
5. Open a Pull Request

## Author
**Sam Lloyd**, sammy.lloyd@live.com, *github.com/lloydy-92*

## Acknowledgements
- Codecademy Data Science Path for providing structured guidance on this project, as well as the dataset itself.
- The open-source community for libraries like ```pandas```, ```matplotlib```, and ```seaborn```.
     
