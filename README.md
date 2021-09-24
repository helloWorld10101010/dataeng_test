# dataeng_test
# Section 1: Data Pipelines
---------------Project Structure----------------
<br />airflow
<br />|---- dags
<br />|      |---- namelist_dag.py
<br />|---- data
<br />|      |---- dataset1.csv
<br />|      |---- dataset2.csv
<br />|---- logs
<br />|---- airflow.cfg


1. Extract
- Setuping schema for database

2. Transform
- Save the DataFrame as CSV to the airflow/data directory
- Break up the pipeline into multiple tasks, or even creating your own custom operators and importing them into your main dag file
<br />i) Split the name field into first_name, and last_name
<br />ii) Remove any zeros prepended to the price field
<br />iii) Delete any rows which do not have a name
<br />iv) Create a new field named above_100, which is true if the price is strictly greater than 100

3. Load
- Designing the schema for the airflow database
<br />CSV(Input) -> CSV(Outpunt)
<br />i) name -> first_name, last name
<br />ii) price -> price, above_100
<br />*truncate the table before loading new datasets to avoid duplicating records when updating tables
<br />*open the dataset csv file, skip the first row (header), and insert each line as a record into the covid_data table

4. Airflow DAG
- Note the value of “0 1 * * *” in our schedule_interval argument which is just CRON language for “run daily at 1am”.
- Append code to the main namelist_dag.py script
<br />-> Pipeline is complete and scheduled to automatically update on a daily basis at 1am.

---------------Key Pointers----------------
1) Airflow scheduling component to automate and manage the tasks
2) DAG (Directed Acyclic Graph) representation
3) Parallelise as much as possible
4) The approach is “set it and forget it“ 
5) Using Airflow, run a web server and access the UI through the browser. The team can schedule jobs to run automatically, besides the server the team also need to run the scheduler. In a production setting, the team will run it on a dedicated server.

---------------Task Notes----------------
1) Script to extract the data from the .csv file
2) Script to extract the metadata and save it to a .csv file (with new fields/data header)
3) Define and initialise the DAG, adding two operators to the DAG.
  <br />a) BashOperator -> run every bash command or script
  <br />b) PythonOperator -> executing python codes
4) DAG Run
  <br />a) Defining the DAG using Context Manager
  <br />b) Define task (e.g t1 = BashOperator)
  <br />c) t1 >> t2. Defining the task dependencies, using a bitshift operator to do that, >>, meaning that t1 runs first and t2 runs second.
5) "Tree View" to view all runs







  
