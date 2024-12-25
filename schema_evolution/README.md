# How to use schema evolution notebook

## Step 1: Install Spark and Jupyter
Install the latest version of Spark and Jupyter using Homebrew on MacOS or install manually on Windows 

## Step 2: SETUP for Jupyter notebook connect to Spark
Set the following variables in your .bashrc or bash shell. 

```
export PYSPARK_DRIVER_PYTHON='/usr/local/bin/jupyter-notebook --notebook-dir=<YourFolderWhereJupyterNotebooksDeployed>'
export PYSPARK_PYTHON='python3.11'
export PYSPARK_DRIVER_PYTHON_OPTS='/usr/local/bin/jupyter-notebook --no-browser --notebook-dir=<YourFolderWhereJupyterNotebooksDeployed>'
export POETRY_VIRTUALENVS_IN_PROJECT=true
```
## Step 3: Run PySpark from the bash shell
```
pyspark --packages io.delta:delta-core_2.12:2.4.0
--conf "spark.sql.extensions=io.delta.sql.DeltaSparkSessionExtension"
--conf "spark.sql.catalog.spark_catalog=org.apache.spark.sql.delta.catalog.DeltaCatalog"
```

This should launch your Jupyter notebook. If the downloaded notbook is in your Jupyter notebook dir, it should show up in the file list. 

## Step 4: Load and Execute one or more cells from the notebook
Happy Learning! 
