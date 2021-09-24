# dataeng_test

---------------Key Pointers----------------
1) Airflow scheduling component to automate and manage the tasks
2) DAG (Directed Acyclic Graph) representation
3) Parallelise as much as possible
4) The approach is “set it and forget it“ 
5) Using Airflow, run a web server and access the UI through the browser. The team can schedule jobs to run automatically, besides the server the team also need to run the scheduler. In a production setting, the team will run it on a dedicated server.

---------------Tasks----------------
1) Script to extract the data from the .csv file
2) Script to extract the metadata and save it to a .csv file (with new fields/data header)
3) Define and initialise the DAG, adding two operators to the DAG.
  a) BashOperator -> run every bash command or script
  b) PythonOperator -> executing python codes
4) DAG Run
  a) Defining the DAG using Context Manager
  b) Define task (e.g t1 = BashOperator)
  c) t1 >> t2. Defining the task dependencies, using a bitshift operator to do that, >>, meaning that t1 runs first and t2 runs second.
5) "Tree View" to view all runs







  
