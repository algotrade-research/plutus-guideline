# Plutus Project Standard Assessment Guide
A series of questions to guide the projects to adhere to open source standards

## 0 Introduction
This guideline is used to assess the open-source conformity of collborated projects in differences ALGOTRADE Training Program, including:
- Algo Researcher
- Internship
- Algorithmic Trading Course
- and collaboated University Thesis Project.

Below listed the requirement of each aspects of an ready-to-publish open-source project. There are current seven (7) aspects:
1. Documentation
2. Coding
3. Data
4. Abstraction
5. Backtesting
6. Optimization
7. Paper Trading


## 1 Documentation
### 1.1 Requirement
- The project should be hosted on [ALGOTRADE Plutus organization in Github](https://github.com/algotrade-research).
- The project should have a `README.md` file
- And a Final Report (or Paper)

in the Github repo.

### 1.2 The README.md
Each Github repository have a `README.md` file contains the overall information of the project. The file is put in the root folder of the project, refers to the repository [`plutus-project-template`](https://github.com/algotrade-research/plutus-project-template) for more information.

The idea of the `README.md` is to provide the reader of the repositoty how to **RUN** and **REPLICATE** the result(s) of this project. Hence, these sections are the focuses of this file:
- `Data`: can be brief, but understandable and clear how to get the data to replicate the results
- `Implementation`: most important, show how to run and replicate the project
- `In-sample Backtesting` to `Paper Trading`: second most important, show how to do the step in development the algorithms and the associated results.

The structure of the specific `README.md` file can deviate from the template presented below depends on the situation. Nevertheless, the file should provide the reader a clear instruction and an accurate overview about the project.

Below is the template of the `README.md`:
- Has a `Abstract` to summarize the project, the motivation, the methods, and the findings in less than 5 sentences.
- Has a `Introduction` section to briefly talk about the project. Content of this section can be:
    - The motivation to do the project (answering the "Why?" question)
    - An overview of the method conducted in this project (answering the "How" question)
    - The goal of the project (answering the "What" question)
    - This section in `README.md` file should be brief. Only 1-2 paragraphs is sufficient. Details are put in the Final Report/Paper.
- Has a (optional) `Related Work` or `Background` section to briefly introduce the prerequisite reading if the audience needs knowledge before exploring the project.
- Has at least sections to briefly discuss from `Step 1: Forming Trading Hypotheses` to `Step 6: Out-of-sample Backtesting` (or `Step 7: Paper Trading`) of the [Nine-Step process](https://hub.algotrade.vn/knowledge-hub/steps-to-develop-a-trading-algorithm/):
    - Should has section to discuss the `Trading (Algorithm) Hypotheses` (Step 1).
    - Should has section to discuss the `Data` (Step 2: Data Collection and Step 3: Data Processing)
    - Should has section to present the `Implementation` (or `How to Run`) of the trading algorithm
    - Should has section to discuss the `In-sample Backtesting` (Step 4)
    - Should has section to discuss the `Optimization` (Step 5)
    - Should has section to discuss the `Out-of-sample Backtesting` (Step 6) 
    - Should has section to discuss the `Paper Trading` (Step 7), if there is
- The `Data` section should has 2 subsections:
    - `Data Collection` to discuss the Step 2
    - `Data Processing` to discuss the Step 3
    - Some questions need to be answered in this sectio:
        - What is the data: Period of data, format, structure, type, etc.?
        - How to input the configuration?
        - How to store the output data?
- The `Implementation` or (`How to run`) should present:
    - How to set up the enviroment to run the source code and required steps to replicate the results
    - Discuss the concrete implementation if there are any essential details
    - How to run each step from `In-sample Backtesting`, Step 4 to `Out-of-sample Backtesting`, Step 6 (or `Paper Trading`, Step 7).
    - How to change the algorithm configurations for different run.
- In each section from the `In-sample Backtesting` to the `Paper Trading`:
    - Specify the standard (or sample) set of parameters, input data, and the corresponding output.
    - There should be a subsection `Result` to present and discuss the results.
- In this `README.md`, the `Result` subsection of each steps:
    - Should only briefly shown the output results, such as tables and images. The link to the report of each step (4-7) should be presented also.
- The complete set of parameters, input data, and output of all the experiments examined in the project should be mentioned in a separate section but not in the README.md file. Preferred these information is put into the **Final Report** or **Paper**.
- Has a (optional) `Conclusion` section.
- Has a `Reference` section to mention the references.
- A link to the Final Report/Paper
    - Show how to compile the document if the it is written in a language like LaTex.
- Be reasonably easy to follow.

### 1.3 The Final Report/Paper
- This document contains all the same sections as the `README.md` file but in more in-depth details. Note that the `Related Work` (or `Backrgound`), and `Conclusion` sections are **NOT** optional in the final report.
- If the final document was written in software such as LaTex, it should be included in the project's GitHub repository and the source to compile it.
- The final document should contain adequate information to understand the project. It should contain documentation reproducing the result up to:
    - Minimally, Step 6: Out-of-sample Backtesting
    - Ideally, Step 7: Paper Trading
    
    of the [Nine-Step process](https://hub.algotrade.vn/knowledge-hub/steps-to-develop-a-trading-algorithm/).


## 2 Coding
### 2.1 Requirement
- There should be unit tests and test cases in essential functions and classes.
- The project should use a version control system, be hosted in a service like GitHub, and be easy to access.
- There should be documentation of the code and docstring in essential functions and classes.
    - The docstring is preferred to follow guidelines such as [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html).
- Code should be structured into proper classes and functions.
- Functions should be short, serve only one purpose, or be simple enough to reuse.
- The code should be easy to understand and extendable.
- The log during runtime (backtest and paper trade) should be concise. Third-party library logs, such as optimization library Optuna, should be suppressed and only show if necessary. The third-party logs can be pushed to debug logging.
### 2.2 Example question to ask (to be revised)
- Is the project accessible through a version control system such as Git and shared through a platform such as GitHub?
- Are there test cases?
- Is there documentation of the code?
- Did objects structure into proper class?
- Did the function serve only one purpose, or was it simple enough to reuse?
- Is the project easy to extend if needed? If yes, what are the good points? If not, what are the shortcomings?
- Is the logging during runtime concise?


## 3 Data
### 3.1 Requirement
- The README.md file should include instructions on how to get the input data and how to store the output data.
- The type of data and the minimum size should be mentioned so that the model makes sense (1 week? 2 months? 3 years?).
- What kind of output data and where it is stored should also be mentioned.
- The expected output, standard input, and standard parameters should be documented.

### 3.2 Example question to ask
- What is the source of the data?
- How does the project access to the data:
    - APIs, streaming, or batch download?
    - Database, external, or Algotrade’s?
- What type of data?
- Data period?
- How does the project manage the output data?
    - Does it store it in a database? In spreadsheet files? Or in binary files? etc.

## 4 Abstraction
Hard to do, so optional at the moment
### 4.1 Requirement
- Use some level of abstraction for basic execution phase objects such as orders, transactions, positions, portfolios, etc.
- Use some level of abstraction for the input data objects
- Use some level of abstraction for the output data objects
- Have a class to unify the evaluation of the algorithm in backtesting, paper trading and real trading
### 4.1.1 Optional
- Use abstraction to separate between bot and algorithm
- Use structure to unify backtest and paper trading

## 4.2 Example question to ask (to be revised)
- Did the project use some abstraction of objects such as order, transaction, position, portfolio, etc.?
- Did the project separate between bot and algorithm?
- Did the project use the same code structure to backtest and paper trade the algorithm?
- Is there a clear method to use to evaluate the algorithm?


## 5 Backtesting
Can use this [form](./report-form/backtesting-report-form.pdf) ([LaTeX source](./report-form/backtesting-report-form-source.zip)) to generate the Backtesting Report
### 5.1 Requirement
- The backtest function should be easy to run (one click).
- The backtest function should make it easy to change the parameters.
- If the backtest report is written in a language like LaTex, it should be easy to reproduce. The code to produce the report should be included in the repository.
- The backtest report should include each dataset's running time and configuration parameters.
- Evaluation methods should be put in a single package or class.
- The output of the backtest and the evaluation metrics should be briefly mentioned in the README.md file.
- There should be a file containing all the parameters and settings of the backtest along with the associated data.

### 5.2 Example question to ask (to be revised)
- Is the backtest function easy to run (e.g., one or two clicks)?
- Is the backtest function easy to change the parameters?
- Can the backtest report be reproduced? Is the production backtest report embedded into the backtest code?
- Is the running time of each dataset and parameter reported?
- Are these evaluation methods put into a single package or functions to easily access the code?
- How does the project handle the data structure for running backtesting?


## 6 Optimization
### 6.1 Requirement
- The optimization functions should be structured into one class or package
- The optimization functions should be easy to understand, implement standard methods, or use a well-known black box library. If new optimization methods are implemented, unit tests and test cases should be used to ensure the correctness of the function. - - - Documentation of the newly invented optimization methods should be written as well.
- The optimization procedure should be clearly described, and the optimized results should be detailed and reported to ensure no overfitting.

### 6.2 Example question to ask (to be revised)
- Is the optimization procedure in a separate package or structured into one class?
- What is the optimization procedure? Is it a well-known method or from a well-known package?
    - If not, is there any documentation to provide rationale and test cases to ensure there will be no overfitting?
- Is the whole optimization process well documented and reported? Are there any flaws in the procedure that could lead to overfitting?


## 7 Paper Trading
Can use this [form](./report-form/papertrading-report-form.pdf) ([LaTeX source](./report-form/papertrading-report-form-source.zip)) to generate the Paper Trading Report
### 7.1 Requirement
- The results of the paper trading should be well documented.
    - The data source.
    - The period
    - The financial instrument(s)
    - The results
- The input and output data of the paper trading should be clearly described:
    - Where to store the output data.
    - The type of the output data.
    - The result and meaning of the output data.
### 7.1.1 Optional
- Backtest and paper trade code should be the same (using the same structure, classes, and methods)

### 7.2 Example question to ask (to be revised)
- How did the project manage the differences between backtest data and live trade data?
- Is the paper trading report production embedded into the code?
- How does the project handle paper trading data? Database? Spreadsheet file? Binary data?
- How does the project handle the data structure for paper trading?