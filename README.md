# datafun-04-eda
Module 4 Project 

## How to Install and Run the Project
### 1. Project Setup  
- Create repo named datafun-04-eda  

- Clone repo to local  
    * `git clone` + URL of repo  

- Create .gitignore file in root project folder  
    * Copy/pasted template from Module 4 example  

- Add requirements.txt in root project folder  
    * Copy/pasted template from Module 4 example  

- Git add-commit-push  
    * `git add .`  
    * `git commit -m "Meaningful comment added"`  
    * `git push`  

- Create Virtual environment  
    * `py -m venv .venv`  

### 2. Repeatable Workflow  
- Pull latest changes from GitHub if necessary  

- Activate Virtual Environment  
    * `.venv\Scripts\activate`  

- Install Dependencies  
    * `py -m pip install --upgrade pip setuptools wheel`  
    * `py -m pip install -r requirements.txt`  

- Set VS Code Interpreter  
    * Open Command Palette: `Ctrl+Shift+P`  
    * Search "Python: Select Interpreter"  
    * Chose local .venv option  

- Create Jupyter Notebook
    * Enter `jupyter lab` in terminal
    * Click Python 3 button under "Notebook" section
    * Right click notebook tab to rename
    * `.ipynb` file type.
    * Make sure the correct kernel is set

- Update README.md  

- Commit changes to git  

## The EDA Project
Start with a Markdown title with the following:  
    * Header cell  
    * Author   
    * Date  
    * Custom opening with purpose of the notebook

1. Imports  
    * `pandas as pd`  
    * `Seaborn as sns`  
    * `matplotlib`  
    * `from matplotlib.axes import Axes` for Axes object  

2. Load Data
    * `iris_df: pd.DataFrame = sns.load_dataset('iris')` to load dataset into pandas DataFrame  
    * `iris_df.columns` to list columns  
    * `iris_df.head()` to inspect the first 5 rows of the data  

3. Initial Data Inspection  
    * `iris_df.head(10)` to specify number of rows to display  
    * `iris_df.shape` to inspect the shape of the DataFrame with shape attribute  
    * `iris_df.dtypes` to inspect the data types fo the columns with dtypes attribute  
    * `iris_df.info()` to inspect the data types of the columns with info() method  
The results will show the type of information entered in the columns of the dataset.

4. Initial Descriptive Statistics
    * `irist_df.describe()` to provide statistical summary of the numberical columns  
Results will show mean, meadian, mode, and standard deviation.

5. Initial Data Distribution for Numerical Columns
    * `iris_df['sepal_length'].hist()` to inspect histogram by one numberical column   
    * `iris_df.hist()` to inspect histograms for all numberical columns   
    * `matplotlib.pyplot.show()` to show all plots  
Results will show a histogram of only the sepal length data.  

5. Initial Data Distribution for Categorical Columns  
    * `iris_df['species'].value_counts()` to inspect value counts by categorical column  
    * `for col in iris_df.select_dtypes(include=['object', 'category']).columns:` to inspect value counts for all categorical columns  
    * `sns.countplot(x=col, data=iris_df)` to display count plot  
    * `matplotlib.pyplot.title(f'Distribution of {col}')`  
    * `matplotlib.pyplot.show()`  
    * `matplotlib.pyplot.show()` to show all plots  
Results will show histograms for all the numerical data.  

6. Initial Data Transformation and Feature Engineering  
    * `iris_df.rename(columns={'sepal_length': 'Sepal Length', 'sepal_width': 'Sepal Width', 'petal_length': 'Petal Length', 'petal_width': 'Petal Width'}, inplace=True)` to rename the columns  
    * `iris_df['Sepal Area'] = iris_df['Sepal Length'] * iris_df['sepal_width']` to add a new column  

7. Initial Visualizations
    * `sns.pairplot(iris_df, hue='species')` to create a pairplot of the Iris dataset  
    * `matplotlib.pyplot.show()` to show all plots  
    * `scatter_plt: Axes = sns.scatterplot(data=iris_df, x="Sepal Length", y="Sepal Area", hue="species")` to scatter plot two numerical values  
    * `scatter_plt.set_xlabel("Sepal Length (mm)")` to set axis labels using the Matplotlib Axes set_xlabel() and set_ylabel() methods  
    * `scatter_plt.set_ylabel("Sepal Area (mm squared)")`  
    * `scatter_plt.set_title("Chart 1. Iris Sepal Length vs. Sepal Area (by Species)")` to set the title using the Matplotlib Axes set_title() method  
    * `matplotlib.pyplot.show()` to show all plots  
Results will show a grid of all data comparisons being made. 

8. Initial Insights
Summarize a clear, compelling, and engaging interpretation based on the facts discovered during the initial exploratory data analysis.

9. Annotate Notebook for Storytelling and Presentation
Craft a narrative around the findings throughout the notebook to make the findings clear and engaging for the audience.