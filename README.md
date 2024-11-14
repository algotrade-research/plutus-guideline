# Open Source (Plutus) Project Conformity Assessment Guide
A series of questions to assess the current projects to adhere to open source standards

## 0 Introduction
This guide is used to assess the open-source conformity of collborated projects in differences ALGOTRADE Training Program, including:
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

The idea of the `README.md` is to provide the reader of the repositoty how to **RUN** and **REPLICATE** the result(s) of this project. Hence, The `Experiment` is the most important section in this file (more later).

Below is the requirement of the `README.md`:
- Has a `Abstract` to summarize the project, the motivation, the methods, and the findings in less than 10 sentences.
- Has a `Introduction` section to briefly talk about the project. Content of this section can be:
    - The motivation to do the project (answering the "Why?" question)
    - An overview of the method conducted in this project (answering the "How" question)
    - The goal of the project (answering the "What" question)
- Has a (optional) `Related Work` or `Background` section to introduce the prerequisite reading if the audience needs knowledge before exploring the project.
- Has a `Data` section to briefly talk about the data.
    - What is the data? Format, structure, type, etc.?
    - How to get the input data?
    - How to store the output data?
- Has a `Method` section to briefly discuss about the method and/or implementation of the project.
- Has a `Experiment` section to discuss the concrete implementation of the methods conducted in the project and how to run and replicate them. This is the most important section in the `README.md` file. In this section:
    - Show how to run the project and reproduce the result.
        - Show how to set up the environment for running the project.
        - Show how to change the parameter for different run.
    - Specify the standard set of parameters, input data, and output of each experiment.
- Has a `Result` section to discuss results corresponding to each implemented method
    - The output results, such as tables and images, should be briefly shown in the README.md file.
    - The complete set of parameters, input data, and output of all the experiments examined in the project should be mentioned in a separate section but not in the README.md file. Preferred these information is put into the **Final Report** or **Paper**.
- Has a (optional) `Conclusion` section.
- Has a `Reference` section to mention the references.
- A link to the final report (or paper)
    - Show how to compile the final report (or paper) if the report is written in a language like LaTex.
- Be reasonably easy to follow.

### 1.3 The Final Report (or Paper)
- The final report contains all the same sections as the `README.md` file but in more in-depth details. Note that the `Related Work` (or `Backrgound`), and `Conclusion` sections are **NOT** optional in the final report.
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