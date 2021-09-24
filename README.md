# dataeng_test

---------------Setup----------------

Define and initialise the DAG, adding two operators to the DAG.
1) BashOperator -> run every bash command or script, 
2) PythonOperator -> executing python codes.

---------------Key pointers----------------
1) DAGs representation
2) Parallelise as much as possible
3) The approach is “set it and forget it“ 

--------------Notes----------------
- Defining the DAG using Context Manager
- define task (e.g t1 = BashOperator)
- t1 >> t2 (Defining the task dependencies)
  
